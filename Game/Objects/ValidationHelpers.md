# Game.Objects.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    public static const System.Single COLLISION_TOLERANCE;

    private static System.Void CheckSurface(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Common.CollisionMask collisionMask, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    private static System.Boolean ExceedRange(Unity.Mathematics.float3 position, Unity.Mathematics.float3 forward, System.Single width, System.Single length, System.Single roundness, System.Boolean circular, Unity.Mathematics.float2 checkPosition);
    private static Unity.Entities.Entity GetOwner(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Tools.ValidationSystem+EntityData data, Game.Net.Edge& tempNodes, Game.Net.Edge& ownerNodes, Unity.Entities.Entity& attachedParent, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edgeOwner, Unity.Entities.Entity& nodeOwner);
    public static System.Boolean Intersect(Colossal.Mathematics.Cylinder3 cylinder1, Colossal.Mathematics.Cylinder3 cylinder2, Unity.Mathematics.float3& pos);
    public static System.Void ValidateNetObject(Unity.Entities.Entity entity, Game.Objects.NetObject netObject, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateObject(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, System.Boolean isOutsideConnection, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> objectList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> instanceCounts, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateOutsideConnection(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateSubPlacement(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateWaterSource(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.WaterSourceData waterSourceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateWorldBounds(Unity.Entities.Entity entity, Game.Common.Owner owner, Colossal.Mathematics.Bounds3 bounds, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Fields

- `public static const System.Single COLLISION_TOLERANCE`  

```csharp
public static const System.Single COLLISION_TOLERANCE;
```


## Methods

- `private static CheckSurface(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Common.CollisionMask collisionMask, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
private static void CheckSurface(Entity entity, Transform transform, CollisionMask collisionMask, ObjectGeometryData prefabObjectGeometryData, PlaceableObjectData placeableObjectData, ValidationSystem.EntityData data, WaterSurfaceData waterSurfaceData, TerrainHeightData terrainHeightData, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		float sampleInterval = WaterUtils.GetSampleInterval(ref waterSurfaceData);
		int2 @int = (int2)math.ceil((prefabObjectGeometryData.m_Bounds.max.xz - prefabObjectGeometryData.m_Bounds.min.xz) / sampleInterval);
		Quad3 quad = ObjectUtils.CalculateBaseCorners(transform.m_Position, transform.m_Rotation, prefabObjectGeometryData.m_Bounds);
		Bounds3 bounds = default(Bounds3);
		bounds.min = float.MaxValue;
		bounds.max = float.MinValue;
		Bounds3 bounds2 = default(Bounds3);
		bounds2.min = float.MaxValue;
		bounds2.max = float.MinValue;
		bool flag = false;
		bool flag2 = false;
		for (int i = 0; i < @int.x; i++)
		{
			float t = ((float)i + 0.5f) / (float)@int.x;
			float3 @float = math.lerp(quad.a, quad.b, t);
			float3 float2 = math.lerp(quad.d, quad.c, t);
			if ((placeableObjectData.m_Flags & PlacementFlags.Shoreline) != PlacementFlags.None)
			{
				float num = WaterUtils.SampleDepth(ref waterSurfaceData, @float);
				float num2 = WaterUtils.SampleDepth(ref waterSurfaceData, float2);
				if (num >= 0.2f)
				{
					bounds |= @float;
					flag = (placeableObjectData.m_Flags & PlacementFlags.Floating) == 0;
				}
				if (num2 < 0.2f)
				{
					bounds2 |= float2;
					flag2 = true;
				}
			}
			else if ((placeableObjectData.m_Flags & (PlacementFlags.Floating | PlacementFlags.Underwater)) != PlacementFlags.None)
			{
				if ((placeableObjectData.m_Flags & PlacementFlags.OnGround) != PlacementFlags.None)
				{
					continue;
				}
				for (int j = 0; j < @int.y; j++)
				{
					float t2 = ((float)j + 0.5f) / (float)@int.y;
					float3 float3 = math.lerp(@float, float2, t2);
					if (WaterUtils.SampleDepth(ref waterSurfaceData, float3) < 0.2f)
					{
						bounds2 |= float3;
						flag2 = true;
					}
				}
			}
			else
			{
				if ((prefabObjectGeometryData.m_Flags & GeometryFlags.CanSubmerge) != GeometryFlags.None)
				{
					continue;
				}
				for (int k = 0; k < @int.y; k++)
				{
					float t3 = ((float)k + 0.5f) / (float)@int.y;
					float3 float4 = math.lerp(@float, float2, t3);
					float waterDepth;
					if ((collisionMask & CollisionMask.ExclusiveGround) != 0)
					{
						waterDepth = WaterUtils.SampleDepth(ref waterSurfaceData, float4);
					}
					else
					{
						float num3 = WaterUtils.SampleHeight(ref waterSurfaceData, ref terrainHeightData, float4, out waterDepth);
						waterDepth = math.min(waterDepth, num3 - transform.m_Position.y);
					}
					if (waterDepth >= 0.2f)
					{
						bounds |= float4;
						flag = true;
					}
				}
			}
		}
		if (flag)
		{
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorType = ErrorType.InWater,
				m_ErrorSeverity = ErrorSeverity.Error,
				m_TempEntity = entity,
				m_Position = MathUtils.Center(bounds)
			});
		}
		if (flag2)
		{
			ErrorData value = default(ErrorData);
			if ((placeableObjectData.m_Flags & (PlacementFlags.OnGround | PlacementFlags.Shoreline)) == (PlacementFlags.OnGround | PlacementFlags.Shoreline))
			{
				value.m_ErrorType = ErrorType.NotOnShoreline;
			}
			else
			{
				value.m_ErrorType = ErrorType.NoWater;
			}
			if ((placeableObjectData.m_Flags & PlacementFlags.OnGround) == 0)
			{
				value.m_ErrorSeverity = ErrorSeverity.Error;
			}
			else
			{
				value.m_ErrorSeverity = ErrorSeverity.Warning;
			}
			value.m_TempEntity = entity;
			value.m_Position = MathUtils.Center(bounds2);
			errorQueue.Enqueue(value);
		}
	}
```

- `private static ExceedRange(Unity.Mathematics.float3 position, Unity.Mathematics.float3 forward, System.Single width, System.Single length, System.Single roundness, System.Boolean circular, Unity.Mathematics.float2 checkPosition) : System.Boolean`  

```csharp
private static bool ExceedRange(float3 position, float3 forward, float width, float length, float roundness, bool circular, float2 checkPosition)
	{
		float2 x = checkPosition - position.xz;
		if (!circular)
		{
			roundness -= 8f;
			x = math.abs(new float2(math.dot(x, MathUtils.Right(forward.xz)), math.dot(x, forward.xz)));
			x = math.max(0f, x - new float2(width * 0.5f, length * 0.5f) + roundness);
		}
		return math.length(x) > roundness;
	}
```

- `private static GetOwner(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Tools.ValidationSystem+EntityData data, Game.Net.Edge& tempNodes, Game.Net.Edge& ownerNodes, Unity.Entities.Entity& attachedParent, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edgeOwner, Unity.Entities.Entity& nodeOwner) : Unity.Entities.Entity`  

```csharp
private static Entity GetOwner(Entity entity, Temp temp, ValidationSystem.EntityData data, out Edge tempNodes, out Edge ownerNodes, out Entity attachedParent, out Entity assetStamp, out Entity edgeOwner, out Entity nodeOwner)
	{
		tempNodes = default(Edge);
		ownerNodes = default(Edge);
		attachedParent = Entity.Null;
		assetStamp = Entity.Null;
		edgeOwner = Entity.Null;
		nodeOwner = Entity.Null;
		if (!data.m_Owner.TryGetComponent(entity, out var componentData) || data.m_Building.HasComponent(entity))
		{
			entity = temp.m_Original;
		}
		else
		{
			do
			{
				if (data.m_AssetStamp.HasComponent(componentData.m_Owner))
				{
					assetStamp = componentData.m_Owner;
					break;
				}
				entity = componentData.m_Owner;
				if (data.m_Edge.TryGetComponent(entity, out var componentData2))
				{
					edgeOwner = entity;
					ownerNodes = componentData2;
					if (data.m_Temp.TryGetComponent(edgeOwner, out var componentData3))
					{
						edgeOwner = componentData3.m_Original;
					}
					if (data.m_Temp.TryGetComponent(ownerNodes.m_Start, out temp))
					{
						tempNodes.m_Start = ownerNodes.m_Start;
						ownerNodes.m_Start = temp.m_Original;
					}
					if (data.m_Temp.TryGetComponent(ownerNodes.m_End, out temp))
					{
						tempNodes.m_End = ownerNodes.m_End;
						ownerNodes.m_End = temp.m_Original;
					}
				}
				else if (data.m_Node.HasComponent(entity))
				{
					nodeOwner = entity;
					if (data.m_Temp.TryGetComponent(nodeOwner, out var componentData4))
					{
						nodeOwner = componentData4.m_Original;
					}
				}
				if (data.m_Temp.TryGetComponent(entity, out temp))
				{
					entity = temp.m_Original;
				}
				if (data.m_Attached.TryGetComponent(entity, out var componentData5))
				{
					attachedParent = componentData5.m_Parent;
				}
			}
			while (data.m_Owner.TryGetComponent(entity, out componentData) && !data.m_Building.HasComponent(entity));
		}
		return entity;
	}
```

- `public static Intersect(Colossal.Mathematics.Cylinder3 cylinder1, Colossal.Mathematics.Cylinder3 cylinder2, Unity.Mathematics.float3& pos) : System.Boolean`  

```csharp
public static bool Intersect(Cylinder3 cylinder1, Cylinder3 cylinder2, ref float3 pos)
	{
		quaternion q = math.mul(cylinder2.rotation, math.inverse(cylinder1.rotation));
		cylinder2.circle.position = math.mul(q, new float3(cylinder2.circle.position.x, 0f, cylinder2.circle.position.y)).xz;
		cylinder2.height.min = math.mul(q, new float3(0f, cylinder2.height.min, 0f)).y;
		cylinder2.height.max = math.mul(q, new float3(0f, cylinder2.height.max, 0f)).y;
		float2 value = cylinder1.circle.position - cylinder2.circle.position;
		float num = cylinder1.circle.radius + cylinder2.circle.radius;
		if (math.lengthsq(value) < num * num && MathUtils.Intersect(cylinder1.height, cylinder2.height))
		{
			MathUtils.TryNormalize(ref value);
			float2 start = cylinder1.circle.position + value * cylinder1.circle.radius;
			float2 end = cylinder2.circle.position - value * cylinder2.circle.radius;
			pos.y = MathUtils.Center(cylinder1.height & cylinder2.height);
			pos.xz = math.lerp(start, end, 0.5f);
			pos = math.mul(cylinder1.rotation, pos);
			return true;
		}
		return false;
	}
```

- `public static ValidateNetObject(Unity.Entities.Entity entity, Game.Objects.NetObject netObject, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateNetObject(Entity entity, NetObject netObject, Transform transform, PrefabRef prefabRef, Attached attached, ValidationSystem.EntityData data, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		RoadTypes roadTypes = RoadTypes.None;
		if (data.m_PrefabNetObject.TryGetComponent(prefabRef.m_Prefab, out var componentData) && componentData.m_RequireRoad != RoadTypes.None)
		{
			roadTypes = componentData.m_RequireRoad;
			if (data.m_Lanes.TryGetBuffer(attached.m_Parent, out var bufferData))
			{
				for (int i = 0; i < bufferData.Length; i++)
				{
					Game.Net.SubLane subLane = bufferData[i];
					if (!data.m_CarLane.HasComponent(subLane.m_SubLane))
					{
						continue;
					}
					PrefabRef prefabRef2 = data.m_PrefabRef[subLane.m_SubLane];
					if (data.m_CarLaneData.TryGetComponent(prefabRef2.m_Prefab, out var componentData2))
					{
						roadTypes = (RoadTypes)((uint)roadTypes & (uint)(byte)(~(int)componentData2.m_RoadTypes));
						if (roadTypes == RoadTypes.None)
						{
							break;
						}
					}
				}
			}
			if (roadTypes == RoadTypes.Watercraft && componentData.m_RequireRoad == (RoadTypes.Car | RoadTypes.Watercraft))
			{
				roadTypes = RoadTypes.None;
			}
		}
		if (roadTypes != RoadTypes.None)
		{
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorType = ((roadTypes == (RoadTypes.Car | RoadTypes.Watercraft)) ? ErrorType.NoPortAccess : ErrorType.NoRoadAccess),
				m_ErrorSeverity = ErrorSeverity.Error,
				m_TempEntity = entity,
				m_Position = transform.m_Position
			});
		}
		else if ((netObject.m_Flags & (NetObjectFlags.IsClear | NetObjectFlags.TrackPassThrough)) == 0)
		{
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorType = ErrorType.OverlapExisting,
				m_ErrorSeverity = ErrorSeverity.Error,
				m_TempEntity = entity,
				m_Position = transform.m_Position
			});
		}
	}
```

- `public static ValidateObject(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, System.Boolean isOutsideConnection, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> objectList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> instanceCounts, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateObject(Entity entity, Temp temp, Owner owner, Transform transform, PrefabRef prefabRef, Attached attached, bool isOutsideConnection, bool editorMode, ValidationSystem.EntityData data, NativeList<ValidationSystem.BoundsData> edgeList, NativeList<ValidationSystem.BoundsData> objectList, NativeQuadTree<Entity, QuadTreeBoundsXZ> objectSearchTree, NativeQuadTree<Entity, QuadTreeBoundsXZ> netSearchTree, NativeQuadTree<AreaSearchItem, QuadTreeBoundsXZ> areaSearchTree, NativeParallelHashMap<Entity, int> instanceCounts, WaterSurfaceData waterSurfaceData, TerrainHeightData terrainHeightData, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		if (!data.m_PrefabObjectGeometry.TryGetComponent(prefabRef.m_Prefab, out var componentData) || ((componentData.m_Flags & GeometryFlags.IgnoreSecondaryCollision) != GeometryFlags.None && data.m_Secondary.HasComponent(entity)))
		{
			return;
		}
		StackData componentData2 = default(StackData);
		Stack componentData3;
		Bounds3 bounds = ((!data.m_Stack.TryGetComponent(entity, out componentData3) || !data.m_PrefabStackData.TryGetComponent(prefabRef.m_Prefab, out componentData2)) ? ObjectUtils.CalculateBounds(transform.m_Position, transform.m_Rotation, componentData) : ObjectUtils.CalculateBounds(transform.m_Position, transform.m_Rotation, componentData3, componentData, componentData2));
		data.m_PlaceableObject.TryGetComponent(prefabRef.m_Prefab, out var componentData4);
		bool flag = false;
		if ((componentData.m_Flags & (GeometryFlags.Overridable | GeometryFlags.DeleteOverridden)) == GeometryFlags.Overridable)
		{
			flag = (temp.m_Flags & TempFlags.Essential) == 0;
		}
		CollisionMask collisionMask;
		bool flag2;
		if (data.m_ObjectElevation.TryGetComponent(entity, out var componentData5))
		{
			collisionMask = ObjectUtils.GetCollisionMask(componentData, componentData5, !editorMode || owner.m_Owner != Entity.Null);
			flag2 = (componentData5.m_Flags & ElevationFlags.OnGround) != 0 && flag;
			Owner componentData6 = owner;
			while (flag && !flag2 && componentData6.m_Owner != Entity.Null)
			{
				PrefabRef prefabRef2 = data.m_PrefabRef[componentData6.m_Owner];
				if (!data.m_PrefabObjectGeometry.TryGetComponent(prefabRef2.m_Prefab, out var componentData7) || (componentData7.m_Flags & (GeometryFlags.Overridable | GeometryFlags.DeleteOverridden)) != GeometryFlags.Overridable || !data.m_Temp.TryGetComponent(componentData6.m_Owner, out var componentData8) || (componentData8.m_Flags & TempFlags.Essential) != 0)
				{
					break;
				}
				if (!data.m_ObjectElevation.TryGetComponent(componentData6.m_Owner, out componentData5) || (componentData5.m_Flags & ElevationFlags.OnGround) != 0)
				{
					flag2 = true;
					break;
				}
				if (!data.m_Owner.TryGetComponent(componentData6.m_Owner, out componentData6))
				{
					break;
				}
			}
		}
		else
		{
			collisionMask = ObjectUtils.GetCollisionMask(componentData, !editorMode || owner.m_Owner != Entity.Null);
			flag2 = flag;
		}
		Entity entity2 = Entity.Null;
		Entity ignoreNode = Entity.Null;
		if ((componentData4.m_Flags & PlacementFlags.RoadNode) != PlacementFlags.None)
		{
			if (data.m_Node.HasComponent(attached.m_Parent))
			{
				entity2 = attached.m_Parent;
			}
			if (data.m_Temp.HasComponent(attached.m_Parent))
			{
				Entity original = data.m_Temp[attached.m_Parent].m_Original;
				if (data.m_Node.HasComponent(original))
				{
					ignoreNode = original;
				}
			}
			else
			{
				ignoreNode = entity2;
				entity2 = Entity.Null;
			}
		}
		if (temp.m_Original == Entity.Null && (componentData4.m_Flags & PlacementFlags.Unique) != PlacementFlags.None && instanceCounts.ContainsKey(prefabRef.m_Prefab))
		{
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorType = ErrorType.AlreadyExists,
				m_ErrorSeverity = ErrorSeverity.Error,
				m_TempEntity = entity,
				m_Position = float.NaN
			});
		}
		ObjectIterator iterator = default(ObjectIterator);
		Entity attachedParent = default(Entity);
		Edge tempNodes = default(Edge);
		Edge ownerNodes = default(Edge);
		Entity edgeOwner = default(Entity);
		Entity nodeOwner = default(Entity);
		if ((temp.m_Flags & TempFlags.Delete) == 0)
		{
			Entity assetStamp;
			Entity owner2 = GetOwner(entity, temp, data, out tempNodes, out ownerNodes, out attachedParent, out assetStamp, out edgeOwner, out nodeOwner);
			iterator = new ObjectIterator
			{
				m_ObjectEntity = entity,
				m_TopLevelEntity = owner2,
				m_AssetStampEntity = assetStamp,
				m_ObjectBounds = bounds,
				m_Transform = transform,
				m_ObjectStack = componentData3,
				m_CollisionMask = collisionMask,
				m_PrefabObjectGeometryData = componentData,
				m_ObjectStackData = componentData2,
				m_CanOverride = flag,
				m_Optional = ((temp.m_Flags & TempFlags.Optional) != 0),
				m_EditorMode = editorMode,
				m_Data = data,
				m_ErrorQueue = errorQueue
			};
			objectSearchTree.Iterate(ref iterator);
		}
		NetIterator iterator2 = default(NetIterator);
		if ((temp.m_Flags & TempFlags.Delete) == 0)
		{
			iterator2 = new NetIterator
			{
				m_ObjectEntity = entity,
				m_AttachedParent = attachedParent,
				m_TopLevelEntity = iterator.m_TopLevelEntity,
				m_EdgeEntity = edgeOwner,
				m_NodeEntity = nodeOwner,
				m_IgnoreNode = ignoreNode,
				m_OwnerNodes = ownerNodes,
				m_ObjectBounds = bounds,
				m_Transform = transform,
				m_ObjectStack = componentData3,
				m_CollisionMask = collisionMask,
				m_PrefabObjectGeometryData = componentData,
				m_ObjectStackData = componentData2,
				m_Optional = flag,
				m_EditorMode = editorMode,
				m_Data = data,
				m_ErrorQueue = errorQueue
			};
			netSearchTree.Iterate(ref iterator2);
		}
		AreaIterator iterator3 = new AreaIterator
		{
			m_ObjectEntity = entity,
			m_ObjectBounds = bounds,
			m_IgnoreCollisions = ((temp.m_Flags & TempFlags.Delete) != 0),
			m_IgnoreProtectedAreas = ((temp.m_Flags & (TempFlags.Create | TempFlags.Delete | TempFlags.Modify | TempFlags.Replace | TempFlags.Upgrade)) == 0),
			m_Optional = flag,
			m_EditorMode = editorMode,
			m_TransformData = transform,
			m_CollisionMask = collisionMask,
			m_PrefabObjectGeometryData = componentData,
			m_Data = data,
			m_ErrorQueue = errorQueue
		};
		areaSearchTree.Iterate(ref iterator3);
		if ((temp.m_Flags & TempFlags.Delete) == 0 && (edgeList.Length != 0 || objectList.Length != 0))
		{
			Entity entity3 = entity;
			Entity entity4 = Entity.Null;
			Entity entity5 = Entity.Null;
			attachedParent = Entity.Null;
			if (owner.m_Owner != Entity.Null && !data.m_Building.HasComponent(entity))
			{
				if (data.m_Node.HasComponent(owner.m_Owner))
				{
					entity5 = owner.m_Owner;
				}
				if (data.m_AssetStamp.HasComponent(owner.m_Owner))
				{
					entity4 = owner.m_Owner;
				}
				else
				{
					if (data.m_Attached.TryGetComponent(owner.m_Owner, out var componentData9))
					{
						attachedParent = componentData9.m_Parent;
					}
					entity3 = owner.m_Owner;
					Owner componentData10;
					while (data.m_Owner.TryGetComponent(entity3, out componentData10) && !data.m_Building.HasComponent(entity3))
					{
						Entity owner3 = componentData10.m_Owner;
						if (data.m_Node.HasComponent(owner3))
						{
							entity5 = owner3;
						}
						if (data.m_AssetStamp.HasComponent(owner3))
						{
							entity4 = owner3;
							break;
						}
						if (data.m_Attached.TryGetComponent(componentData10.m_Owner, out componentData9))
						{
							attachedParent = componentData9.m_Parent;
						}
						entity3 = owner3;
					}
				}
			}
			DynamicBuffer<ConnectedEdge> dynamicBuffer = default(DynamicBuffer<ConnectedEdge>);
			DynamicBuffer<ConnectedNode> dynamicBuffer2 = default(DynamicBuffer<ConnectedNode>);
			Edge edge = default(Edge);
			if (data.m_ConnectedEdges.HasBuffer(entity3))
			{
				dynamicBuffer = data.m_ConnectedEdges[entity3];
			}
			else if (data.m_ConnectedNodes.HasBuffer(entity3))
			{
				dynamicBuffer2 = data.m_ConnectedNodes[entity3];
				edge = data.m_Edge[entity3];
			}
			bool flag3 = false;
			if ((componentData4.m_Flags & PlacementFlags.RoadNode) != PlacementFlags.None && data.m_PrefabNetObject.TryGetComponent(prefabRef.m_Prefab, out var componentData11) && (componentData11.m_CompositionFlags.m_General & CompositionFlags.General.FixedNodeSize) != 0)
			{
				flag3 = true;
			}
			iterator2.m_TopLevelEntity = entity3;
			if (edgeList.Length != 0)
			{
				float3 @float = edgeList[edgeList.Length - 1].m_Bounds.max - edgeList[0].m_Bounds.min;
				bool flag4 = @float.z > @float.x;
				for (int i = 0; i < edgeList.Length; i++)
				{
					ValidationSystem.BoundsData boundsData = edgeList[i];
					bool2 @bool = boundsData.m_Bounds.min.xz > bounds.max.xz;
					if (flag4 ? @bool.y : @bool.x)
					{
						break;
					}
					if ((collisionMask & CollisionMask.OnGround) != 0)
					{
						if (!MathUtils.Intersect(bounds.xz, boundsData.m_Bounds.xz))
						{
							continue;
						}
					}
					else if (!MathUtils.Intersect(bounds, boundsData.m_Bounds))
					{
						continue;
					}
					Entity entity6 = boundsData.m_Entity;
					Entity owner4;
					if (data.m_Owner.TryGetComponent(boundsData.m_Entity, out var componentData12))
					{
						owner4 = componentData12.m_Owner;
						if (data.m_AssetStamp.HasComponent(owner4))
						{
							if (owner4 == entity)
							{
								continue;
							}
						}
						else
						{
							entity6 = owner4;
							while (data.m_Owner.HasComponent(entity6) && !data.m_Building.HasComponent(entity6))
							{
								owner4 = data.m_Owner[entity6].m_Owner;
								if (!data.m_AssetStamp.HasComponent(owner4))
								{
									entity6 = owner4;
									continue;
								}
								goto IL_086e;
							}
						}
						goto IL_08a1;
					}
					goto IL_08de;
					IL_086e:
					if (owner4 == entity)
					{
						continue;
					}
					goto IL_08a1;
					IL_08a1:
					if (data.m_Edge.TryGetComponent(componentData12.m_Owner, out var componentData13) && (entity5 == componentData13.m_Start || entity5 == componentData13.m_End))
					{
						continue;
					}
					goto IL_08de;
					IL_08de:
					if (entity3 == entity6)
					{
						continue;
					}
					Edge edgeData = data.m_Edge[boundsData.m_Entity];
					if (boundsData.m_Entity == attachedParent || edgeData.m_Start == attachedParent || edgeData.m_End == attachedParent)
					{
						continue;
					}
					Entity entity7 = edgeData.m_Start;
					Entity entity8 = edgeData.m_End;
					Edge edge2 = default(Edge);
					Edge edge3 = default(Edge);
					while (true)
					{
						if (data.m_Owner.TryGetComponent(entity7, out var componentData14) && !data.m_Building.HasComponent(entity7))
						{
							Entity owner5 = componentData14.m_Owner;
							if (!data.m_AssetStamp.HasComponent(owner5))
							{
								if (data.m_Edge.TryGetComponent(owner5, out var componentData15))
								{
									edge2 = componentData15;
								}
								entity7 = owner5;
								continue;
							}
							if (owner5 == entity)
							{
								break;
							}
						}
						while (true)
						{
							if (data.m_Owner.TryGetComponent(entity8, out var componentData16) && !data.m_Building.HasComponent(entity8))
							{
								Entity owner6 = componentData16.m_Owner;
								if (!data.m_AssetStamp.HasComponent(owner6))
								{
									if (data.m_Edge.TryGetComponent(owner6, out var componentData17))
									{
										edge3 = componentData17;
									}
									entity8 = owner6;
									continue;
								}
								if (owner6 == entity)
								{
									break;
								}
							}
							Composition compositionData = data.m_Composition[boundsData.m_Entity];
							if (flag3)
							{
								if (owner.m_Owner == edgeData.m_Start && (data.m_PrefabComposition[compositionData.m_StartNode].m_Flags.m_General & CompositionFlags.General.FixedNodeSize) == 0)
								{
									edgeData.m_Start = boundsData.m_Entity;
									entity7 = boundsData.m_Entity;
								}
								if (owner.m_Owner == edgeData.m_End && (data.m_PrefabComposition[compositionData.m_EndNode].m_Flags.m_General & CompositionFlags.General.FixedNodeSize) == 0)
								{
									edgeData.m_End = boundsData.m_Entity;
									entity8 = boundsData.m_Entity;
								}
							}
							if (owner.m_Owner != Entity.Null)
							{
								Entity owner7 = owner.m_Owner;
								while (!(owner7 == edgeData.m_Start) && !(owner7 == edgeData.m_End) && !(owner7 == edge2.m_Start) && !(owner7 == edge2.m_End) && !(owner7 == edge3.m_Start) && !(owner7 == edge3.m_End))
								{
									if (data.m_Owner.TryGetComponent(owner7, out var componentData18))
									{
										owner7 = componentData18.m_Owner;
										continue;
									}
									goto IL_0b93;
								}
								break;
							}
							goto IL_0b93;
							IL_0b93:
							EdgeGeometry edgeGeometryData = data.m_EdgeGeometry[boundsData.m_Entity];
							StartNodeGeometry startNodeGeometryData = data.m_StartNodeGeometry[boundsData.m_Entity];
							EndNodeGeometry endNodeGeometryData = data.m_EndNodeGeometry[boundsData.m_Entity];
							bool flag5 = entity7 != entity3 && edgeData.m_Start != tempNodes.m_Start && edgeData.m_Start != tempNodes.m_End;
							bool flag6 = entity8 != entity3 && edgeData.m_End != tempNodes.m_Start && edgeData.m_End != tempNodes.m_End;
							if (flag5 && edgeData.m_Start == entity2)
							{
								flag5 &= (data.m_PrefabComposition[compositionData.m_StartNode].m_Flags.m_General & CompositionFlags.General.Roundabout) == 0;
							}
							if (flag6 && edgeData.m_End == entity2)
							{
								flag6 &= (data.m_PrefabComposition[compositionData.m_EndNode].m_Flags.m_General & CompositionFlags.General.Roundabout) == 0;
							}
							edgeData.m_Start = entity7;
							edgeData.m_End = entity8;
							Temp temp2 = data.m_Temp[boundsData.m_Entity];
							iterator2.CheckOverlap(entity6, boundsData.m_Entity, boundsData.m_Bounds, edgeData, compositionData, edgeGeometryData, startNodeGeometryData, endNodeGeometryData, transform.m_Position, flag5, flag6, (temp2.m_Flags & TempFlags.Essential) != 0, componentData12.m_Owner != Entity.Null);
							break;
						}
						break;
					}
				}
			}
			if (objectList.Length != 0)
			{
				float3 float2 = objectList[objectList.Length - 1].m_Bounds.max - objectList[0].m_Bounds.min;
				bool flag7 = float2.z > float2.x;
				int num = 0;
				int num2 = objectList.Length;
				while (num < num2)
				{
					int num3 = num + num2 >> 1;
					bool2 bool2 = objectList[num3].m_Bounds.min.xz < bounds.min.xz;
					if (flag7 ? bool2.y : bool2.x)
					{
						num = num3 + 1;
					}
					else
					{
						num2 = num3;
					}
				}
				for (int j = num; j < objectList.Length; j++)
				{
					ValidationSystem.BoundsData boundsData2 = objectList[j];
					bool2 bool3 = boundsData2.m_Bounds.min.xz > bounds.max.xz;
					if (flag7 ? bool3.y : bool3.x)
					{
						break;
					}
					if ((collisionMask & CollisionMask.OnGround) != 0)
					{
						if (!MathUtils.Intersect(bounds.xz, boundsData2.m_Bounds.xz))
						{
							continue;
						}
					}
					else if (!MathUtils.Intersect(bounds, boundsData2.m_Bounds))
					{
						continue;
					}
					if (boundsData2.m_Entity == entity || boundsData2.m_Entity == entity4 || (boundsData2.m_Bounds.min.x == bounds.min.x && boundsData2.m_Entity.Index < entity.Index))
					{
						continue;
					}
					Entity entity9 = boundsData2.m_Entity;
					Entity owner8;
					if (data.m_Owner.TryGetComponent(boundsData2.m_Entity, out var componentData19) && !data.m_Building.HasComponent(entity9))
					{
						owner8 = componentData19.m_Owner;
						if (data.m_AssetStamp.HasComponent(owner8))
						{
							if (owner8 == entity)
							{
								continue;
							}
						}
						else
						{
							entity9 = owner8;
							while (data.m_Owner.HasComponent(entity9) && !data.m_Building.HasComponent(entity9))
							{
								owner8 = data.m_Owner[entity9].m_Owner;
								if (!data.m_AssetStamp.HasComponent(owner8))
								{
									entity9 = owner8;
									continue;
								}
								goto IL_0f6f;
							}
						}
					}
					goto IL_0fa2;
					IL_0fa2:
					if (entity3 == entity9)
					{
						continue;
					}
					if (dynamicBuffer.IsCreated)
					{
						int num4 = 0;
						while (num4 < dynamicBuffer.Length)
						{
							if (!(dynamicBuffer[num4].m_Edge == entity9))
							{
								num4++;
								continue;
							}
							goto IL_10ce;
						}
					}
					else if (dynamicBuffer2.IsCreated)
					{
						int num5 = 0;
						while (num5 < dynamicBuffer2.Length)
						{
							if (!(dynamicBuffer2[num5].m_Node == entity9))
							{
								num5++;
								continue;
							}
							goto IL_10ce;
						}
						if (edge.m_Start == entity9 || edge.m_End == entity9)
						{
							continue;
						}
					}
					if (!(attached.m_Parent == boundsData2.m_Entity) && (!data.m_Attached.TryGetComponent(boundsData2.m_Entity, out var componentData20) || !(componentData20.m_Parent == entity)))
					{
						Temp temp3 = data.m_Temp[boundsData2.m_Entity];
						iterator.CheckOverlap(entity9, boundsData2.m_Entity, boundsData2.m_Bounds, (temp3.m_Flags & TempFlags.Essential) != 0, componentData19.m_Owner != Entity.Null);
					}
					continue;
					IL_0f6f:
					if (owner8 == entity)
					{
						continue;
					}
					goto IL_0fa2;
					IL_10ce:;
				}
			}
		}
		if ((temp.m_Flags & (TempFlags.Create | TempFlags.Modify)) != 0 && componentData4.m_Flags != PlacementFlags.None && !flag2)
		{
			CheckSurface(entity, transform, collisionMask, componentData, componentData4, data, waterSurfaceData, terrainHeightData, errorQueue);
		}
		if ((temp.m_Flags & TempFlags.Essential) != 0 && (temp.m_Flags & (TempFlags.Create | TempFlags.Modify)) != 0 && owner.m_Owner != Entity.Null)
		{
			ValidateSubPlacement(entity, owner, transform, prefabRef, componentData, data, errorQueue);
		}
		if ((temp.m_Flags & (TempFlags.Create | TempFlags.Modify | TempFlags.Replace | TempFlags.Upgrade)) != 0 && !isOutsideConnection)
		{
			ValidateWorldBounds(entity, owner, bounds, data, terrainHeightData, errorQueue);
		}
	}
```

- `public static ValidateOutsideConnection(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateOutsideConnection(Entity entity, Transform transform, TerrainHeightData terrainHeightData, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		Bounds3 bounds = TerrainUtils.GetBounds(ref terrainHeightData);
		if (MathUtils.Intersect(MathUtils.Expand(bounds, -0.1f).xz, transform.m_Position.xz))
		{
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorType = ErrorType.NotOnBorder,
				m_ErrorSeverity = ErrorSeverity.Error,
				m_TempEntity = entity,
				m_Position = transform.m_Position
			});
		}
	}
```

- `public static ValidateSubPlacement(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateSubPlacement(Entity entity, Owner owner, Transform transform, PrefabRef prefabRef, ObjectGeometryData prefabObjectGeometryData, ValidationSystem.EntityData data, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		if (!data.m_Building.HasComponent(owner.m_Owner))
		{
			return;
		}
		Transform transform2 = data.m_Transform[owner.m_Owner];
		PrefabRef prefabRef2 = data.m_PrefabRef[owner.m_Owner];
		BuildingData ownerBuildingData = data.m_PrefabBuilding[prefabRef2.m_Prefab];
		if (data.m_Building.HasComponent(entity))
		{
			if (data.m_PrefabBuilding.TryGetComponent(prefabRef.m_Prefab, out var componentData) && data.m_ServiceUpgradeData.TryGetComponent(prefabRef.m_Prefab, out var componentData2) && componentData2.m_MaxPlacementDistance != 0f)
			{
				BuildingUtils.CalculateUpgradeRangeValues(transform2.m_Rotation, ownerBuildingData, componentData, componentData2, out var forward, out var width, out var length, out var roundness, out var circular);
				float2 halfLotSize = (float2)componentData.m_LotSize * 4f - 0.4f;
				Quad3 quad = BuildingUtils.CalculateCorners(transform.m_Position, transform.m_Rotation, halfLotSize);
				float4 @float = default(float4);
				if (ExceedRange(transform2.m_Position, forward, width, length, roundness, circular, quad.a.xz))
				{
					@float += new float4(quad.a, 1f);
				}
				if (ExceedRange(transform2.m_Position, forward, width, length, roundness, circular, quad.b.xz))
				{
					@float += new float4(quad.b, 1f);
				}
				if (ExceedRange(transform2.m_Position, forward, width, length, roundness, circular, quad.c.xz))
				{
					@float += new float4(quad.c, 1f);
				}
				if (ExceedRange(transform2.m_Position, forward, width, length, roundness, circular, quad.d.xz))
				{
					@float += new float4(quad.d, 1f);
				}
				if (@float.w != 0f)
				{
					errorQueue.Enqueue(new ErrorData
					{
						m_ErrorType = ErrorType.LongDistance,
						m_ErrorSeverity = ErrorSeverity.Error,
						m_TempEntity = entity,
						m_PermanentEntity = owner.m_Owner,
						m_Position = @float.xyz / @float.w
					});
				}
			}
		}
		else
		{
			float2 float2 = ownerBuildingData.m_LotSize;
			float2 *= 4f;
			Bounds2 bounds = new Bounds2(-float2, float2);
			Transform transform3 = ObjectUtils.WorldToLocal(ObjectUtils.InverseTransform(transform2), transform);
			Bounds3 bounds2 = ObjectUtils.CalculateBounds(transform3.m_Position, transform3.m_Rotation, prefabObjectGeometryData);
			if (!bounds2.xz.Equals(bounds2.xz & bounds))
			{
				float3 position = new float3
				{
					xz = (math.select(bounds2.min.xz, bounds.max, (bounds2.min.xz >= bounds.min) & (bounds2.max.xz > bounds.max)) + math.select(bounds2.max.xz, bounds.min, (bounds2.max.xz <= bounds.max) & (bounds2.min.xz < bounds.min))) * 0.5f,
					y = MathUtils.Center(bounds2.y)
				};
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorType = ErrorType.ExceedsLotLimits,
					m_ErrorSeverity = ErrorSeverity.Warning,
					m_TempEntity = entity,
					m_Position = ObjectUtils.LocalToWorld(transform2, position)
				});
			}
		}
	}
```

- `public static ValidateWaterSource(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.WaterSourceData waterSourceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateWaterSource(Entity entity, Transform transform, Game.Simulation.WaterSourceData waterSourceData, TerrainHeightData terrainHeightData, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		Bounds3 bounds = TerrainUtils.GetBounds(ref terrainHeightData);
		Bounds3 bounds2 = MathUtils.Expand(bounds, 0f - waterSourceData.m_Radius);
		Bounds3 bounds3 = MathUtils.Expand(bounds, waterSourceData.m_Radius);
		if (waterSourceData.m_ConstantDepth < 2)
		{
			if (!MathUtils.Intersect(bounds2.xz, transform.m_Position.xz))
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorType = ErrorType.ExceedsCityLimits,
					m_ErrorSeverity = ErrorSeverity.Error,
					m_TempEntity = entity,
					m_Position = transform.m_Position
				});
			}
		}
		else if (!MathUtils.Intersect(bounds3.xz, transform.m_Position.xz) || MathUtils.Intersect(bounds2.xz, transform.m_Position.xz))
		{
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorType = ErrorType.NotOnBorder,
				m_ErrorSeverity = ErrorSeverity.Error,
				m_TempEntity = entity,
				m_Position = transform.m_Position
			});
		}
	}
```

- `public static ValidateWorldBounds(Unity.Entities.Entity entity, Game.Common.Owner owner, Colossal.Mathematics.Bounds3 bounds, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateWorldBounds(Entity entity, Owner owner, Bounds3 bounds, ValidationSystem.EntityData data, TerrainHeightData terrainHeightData, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		Bounds3 bounds2 = MathUtils.Expand(TerrainUtils.GetBounds(ref terrainHeightData), 0.1f);
		if (bounds.xz.Equals(bounds.xz & bounds2.xz))
		{
			return;
		}
		while (owner.m_Owner != Entity.Null)
		{
			if (data.m_Node.HasComponent(owner.m_Owner) || data.m_Edge.HasComponent(owner.m_Owner))
			{
				return;
			}
			data.m_Owner.TryGetComponent(owner.m_Owner, out var componentData);
			owner = componentData;
		}
		Bounds3 bounds3 = bounds;
		bounds3.min.xz = math.select(bounds.min.xz, bounds2.max.xz, (bounds2.max.xz > bounds.min.xz) & (bounds.min.xz >= bounds2.min.xz) & (bounds.max.xz > bounds2.max.xz));
		bounds3.max.xz = math.select(bounds.max.xz, bounds2.min.xz, (bounds2.min.xz < bounds.max.xz) & (bounds.max.xz <= bounds2.max.xz) & (bounds.min.xz < bounds2.min.xz));
		errorQueue.Enqueue(new ErrorData
		{
			m_Position = MathUtils.Center(bounds3),
			m_ErrorType = ErrorType.ExceedsCityLimits,
			m_ErrorSeverity = ErrorSeverity.Error,
			m_TempEntity = entity
		});
	}
```


## Nested types

- `Game.Objects.ValidationHelpers+ObjectIterator`  
- `Game.Objects.ValidationHelpers+NetIterator`  
- `Game.Objects.ValidationHelpers+AreaIterator`  

