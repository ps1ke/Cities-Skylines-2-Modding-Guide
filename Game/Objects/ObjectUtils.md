# Game.Objects.ObjectUtils

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ObjectUtils
{
    public static const System.Single MAX_SPAWN_LOCATION_CONNECTION_DISTANCE;
    public static const System.Single MIN_TREE_WOOD_RESOURCE;
    public static const System.Single MAX_TREE_AGE;
    public static const System.Single TREE_AGE_PHASE_CHILD;
    public static const System.Single TREE_AGE_PHASE_TEEN;
    public static const System.Single TREE_AGE_PHASE_ADULT;
    public static const System.Single TREE_AGE_PHASE_ELDERLY;
    public static const System.Single TREE_AGE_PHASE_DEAD;
    public static const System.Single TREE_WOOD_GROWTH_CHILD;
    public static const System.Single TREE_WOOD_GROWTH_TEEN;
    public static const System.Single TREE_WOOD_GROWTH_ADULT;

    public static Game.Objects.Transform AdjustPosition(Game.Objects.Transform transform, Game.Objects.Elevation& elevation, Unity.Entities.Entity prefab, System.Boolean& angledSample, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PlaceableObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& placeableObjectDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryDatas);
    private static System.Void ApplyRootMotion(Game.Objects.Transform& transform, Game.Objects.TransformFrame& newFrameData, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationMotion> motions, Game.Rendering.BlendWeights weights, Unity.Mathematics.int2 motionRange, Unity.Mathematics.float3 deltaRange);
    private static System.Void ApplyRootMotion(Game.Objects.Transform& transform, Unity.Mathematics.float3& targetPosition, Unity.Mathematics.float3& targetDirection, Unity.Mathematics.float3 rootOffset, Unity.Mathematics.quaternion rootRotation);
    public static Colossal.Mathematics.Quad3 CalculateBaseCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Colossal.Mathematics.Bounds3 bounds);
    public static Colossal.Mathematics.Quad3 CalculateBaseCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float2 size);
    public static Colossal.Mathematics.Bounds3 CalculateBounds(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Prefabs.ObjectGeometryData geometryData);
    public static Colossal.Mathematics.Bounds3 CalculateBounds(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Objects.Stack stack, Game.Prefabs.ObjectGeometryData geometryData, Game.Prefabs.StackData stackData);
    public static Colossal.Mathematics.Bounds3 CalculateBounds(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Colossal.Mathematics.Bounds3 bounds);
    public static Colossal.Mathematics.Bounds3 CalculateBounds(Colossal.Mathematics.Line3+Segment positionRange, Unity.Mathematics.quaternion rotation, Colossal.Mathematics.Bounds3 bounds);
    public static System.Single CalculateGrowthRate(Game.Objects.Tree tree, Game.Objects.Plant plant, Game.Prefabs.TreeData treeData);
    public static Unity.Mathematics.float3 CalculateMomentOfInertia(Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 size);
    public static Unity.Mathematics.float3 CalculatePointVelocity(Unity.Mathematics.float3 offset, Game.Objects.Moving moving);
    public static System.Single CalculateWoodAmount(Game.Objects.Tree tree, Game.Objects.Plant plant, Game.Objects.Damaged damaged, Game.Prefabs.TreeData treeData);
    public static Game.Objects.Transform GetActivityStartPosition(Unity.Entities.Entity prefab, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Game.Objects.Transform activityTransform, Game.Objects.TransformState state, Game.Prefabs.ActivityType activityType, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityCondition conditions, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers, Game.Objects.ObjectUtils+ActivityStartPositionCache& cache);
    public static Colossal.Mathematics.Bounds3 GetBounds(Game.Prefabs.ObjectGeometryData geometryData);
    public static Colossal.Mathematics.Bounds3 GetBounds(Game.Objects.Stack stack, Game.Prefabs.ObjectGeometryData geometryData, Game.Prefabs.StackData stackData);
    public static Game.Common.CollisionMask GetCollisionMask(Game.Prefabs.ObjectGeometryData geometryData, Game.Objects.Elevation elevation, System.Boolean ignoreMarkers);
    public static Game.Common.CollisionMask GetCollisionMask(Game.Prefabs.ObjectGeometryData geometryData, System.Boolean ignoreMarkers);
    public static System.Int32 GetContructionCost(System.Int32 constructionCost, Game.Objects.Tree tree, Game.Prefabs.EconomyParameterData& economyParameterData);
    private static System.Byte GetParentActivity(System.Byte activity);
    public static System.Int32 GetRebuildCost(System.Int32 constructionCost);
    public static System.Int32 GetRebuildCost(System.Int32 constructionCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData);
    public static System.Int32 GetRefundAmount(Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData);
    public static System.Int32 GetRelocationCost(System.Int32 constructionCost, Game.Prefabs.EconomyParameterData economyParameterData);
    public static System.Int32 GetRelocationCost(System.Int32 constructionCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData);
    public static System.UInt32 GetRemainingConstructionFrames(Game.Objects.UnderConstruction underConstruction);
    public static System.Void GetRootMotion(Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationMotion> motions, Unity.Mathematics.int2 range, Game.Rendering.BlendWeights weights, System.Single t, Unity.Mathematics.float3& rootOffset, Unity.Mathematics.float3& rootVelocity, Unity.Mathematics.quaternion& rootRotation);
    private static System.Void GetRootMotion(Game.Prefabs.AnimationMotion motion, System.Single t, Unity.Mathematics.float3& rootOffset, Unity.Mathematics.float3& rootVelocity, Unity.Mathematics.quaternion& rootRotation);
    public static Unity.Mathematics.float3 GetSize(Colossal.Mathematics.Bounds3 bounds);
    public static System.Boolean GetStandingLegCount(Game.Prefabs.ObjectGeometryData objectGeometryData, System.Int32& legCount);
    public static Unity.Mathematics.float3 GetStandingLegOffset(Game.Prefabs.ObjectGeometryData objectGeometryData, System.Int32 legIndex);
    public static Unity.Mathematics.float3 GetStandingLegPosition(Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Objects.Transform transform, System.Int32 legIndex);
    private static System.Single GetStateDuration(Unity.Entities.Entity prefab, Game.Objects.TransformState state, System.Byte activity, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityCondition conditions, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Game.Prefabs.CharacterElement& characterElement, Game.Prefabs.AnimationClip& animationClip, System.Boolean& crossFade);
    public static System.Int32 GetSubParentMesh(Game.Objects.ElevationFlags elevationFlags);
    public static System.Single GetTerrainSmoothingWidth(Game.Prefabs.ObjectGeometryData objectGeometryData);
    public static System.Single GetTerrainSmoothingWidth(Unity.Mathematics.float2 size);
    public static System.Single GetTotalDamage(Game.Objects.Damaged damaged);
    public static System.UInt32 GetTripDelayFrames(Game.Objects.UnderConstruction underConstruction, Game.Pathfind.PathInformation pathInformation);
    public static System.Int32 GetUpgradeCost(System.Int32 constructionCost, System.Int32 originalCost);
    public static System.Int32 GetUpgradeCost(System.Int32 constructionCost, System.Int32 originalCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData);
    public static Game.Objects.Tree InitializeTreeState(System.Single age);
    public static Game.Objects.Transform InverseTransform(Game.Objects.Transform transform);
    public static Unity.Mathematics.float3 LocalToWorld(Game.Objects.Transform transform, Unity.Mathematics.float3 position);
    public static Unity.Mathematics.float3 LocalToWorld(Unity.Mathematics.float3 transformPosition, Unity.Mathematics.quaternion transformRotation, Unity.Mathematics.float3 position);
    public static Colossal.Mathematics.Bezier4x3 LocalToWorld(Unity.Mathematics.float3 transformPosition, Unity.Mathematics.quaternion transformRotation, Colossal.Mathematics.Bezier4x3 curve);
    public static Game.Objects.Transform LocalToWorld(Game.Objects.Transform transform, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation);
    public static Game.Rendering.InterpolatedTransform LocalToWorld(Game.Rendering.InterpolatedTransform transform, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation);
    public static Game.Objects.Transform LocalToWorld(Game.Objects.Transform parentTransform, Game.Objects.Transform transform);
    public static System.Void UpdateAnimation(Unity.Entities.Entity prefab, System.Single timeStep, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers, Game.Rendering.AnimatedPropID oldPropID, Game.Rendering.AnimatedPropID newPropID, Game.Prefabs.ActivityCondition conditions, System.Single& maxSpeed, System.Byte& activity, Unity.Mathematics.float3& targetPosition, Unity.Mathematics.float3& targetDirection, Game.Objects.Transform& transform, Game.Objects.TransformFrame& oldFrameData, Game.Objects.TransformFrame& newFrameData);
    public static System.Void UpdateResourcesDamage(Unity.Entities.Entity entity, System.Single totalDamage, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterData, Unity.Entities.BufferLookup`1[[Game.Economy.Resources, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourcesData);
    public static Game.Objects.Transform WorldToLocal(Game.Objects.Transform inverseParentTransform, Game.Objects.Transform transform);
    public static Unity.Mathematics.float3 WorldToLocal(Game.Objects.Transform inverseParentTransform, Unity.Mathematics.float3 position);
}
```


## Fields

- `public static const System.Single MAX_SPAWN_LOCATION_CONNECTION_DISTANCE`  

```csharp
public static const System.Single MAX_SPAWN_LOCATION_CONNECTION_DISTANCE;
```

- `public static const System.Single MIN_TREE_WOOD_RESOURCE`  

```csharp
public static const System.Single MIN_TREE_WOOD_RESOURCE;
```

- `public static const System.Single MAX_TREE_AGE`  

```csharp
public static const System.Single MAX_TREE_AGE;
```

- `public static const System.Single TREE_AGE_PHASE_CHILD`  

```csharp
public static const System.Single TREE_AGE_PHASE_CHILD;
```

- `public static const System.Single TREE_AGE_PHASE_TEEN`  

```csharp
public static const System.Single TREE_AGE_PHASE_TEEN;
```

- `public static const System.Single TREE_AGE_PHASE_ADULT`  

```csharp
public static const System.Single TREE_AGE_PHASE_ADULT;
```

- `public static const System.Single TREE_AGE_PHASE_ELDERLY`  

```csharp
public static const System.Single TREE_AGE_PHASE_ELDERLY;
```

- `public static const System.Single TREE_AGE_PHASE_DEAD`  

```csharp
public static const System.Single TREE_AGE_PHASE_DEAD;
```

- `public static const System.Single TREE_WOOD_GROWTH_CHILD`  

```csharp
public static const System.Single TREE_WOOD_GROWTH_CHILD;
```

- `public static const System.Single TREE_WOOD_GROWTH_TEEN`  

```csharp
public static const System.Single TREE_WOOD_GROWTH_TEEN;
```

- `public static const System.Single TREE_WOOD_GROWTH_ADULT`  

```csharp
public static const System.Single TREE_WOOD_GROWTH_ADULT;
```


## Methods

- `public static AdjustPosition(Game.Objects.Transform transform, Game.Objects.Elevation& elevation, Unity.Entities.Entity prefab, System.Boolean& angledSample, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PlaceableObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& placeableObjectDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryDatas) : Game.Objects.Transform`  

```csharp
public static Transform AdjustPosition(Transform transform, ref Elevation elevation, Entity prefab, out bool angledSample, ref TerrainHeightData terrainHeightData, ref WaterSurfaceData waterSurfaceData, ref ComponentLookup<PlaceableObjectData> placeableObjectDatas, ref ComponentLookup<ObjectGeometryData> objectGeometryDatas)
	{
		Transform result = transform;
		float num = 0f;
		float num2 = 0f;
		angledSample = true;
		if (placeableObjectDatas.TryGetComponent(prefab, out var componentData))
		{
			if ((componentData.m_Flags & PlacementFlags.Hovering) != PlacementFlags.None)
			{
				result.m_Position.y = WaterUtils.SampleHeight(ref waterSurfaceData, ref terrainHeightData, transform.m_Position);
				result.m_Position.y += componentData.m_PlacementOffset.y;
				angledSample = false;
			}
			else if ((componentData.m_Flags & (PlacementFlags.Shoreline | PlacementFlags.Floating)) != PlacementFlags.None)
			{
				WaterUtils.SampleHeight(ref waterSurfaceData, ref terrainHeightData, transform.m_Position, out result.m_Position.y, out var waterHeight, out var waterDepth);
				if (waterDepth >= 0.2f)
				{
					float y = result.m_Position.y;
					result.m_Position.y = math.max(result.m_Position.y, waterHeight + componentData.m_PlacementOffset.y);
					if ((componentData.m_Flags & PlacementFlags.Floating) != PlacementFlags.None)
					{
						num2 = math.max(0f, result.m_Position.y - y);
					}
				}
				angledSample = false;
			}
			else
			{
				num = componentData.m_PlacementOffset.y;
			}
		}
		if (angledSample)
		{
			if (objectGeometryDatas.TryGetComponent(prefab, out var componentData2) && (componentData2.m_Flags & (GeometryFlags.Standing | GeometryFlags.HasBase)) != GeometryFlags.Standing)
			{
				float3 x = math.forward(transform.m_Rotation);
				x.y = 0f;
				x = math.normalizesafe(x, math.forward());
				float3 @float = new float3
				{
					xz = MathUtils.Right(x.xz)
				};
				float4 x2 = default(float4);
				x2.x = TerrainUtils.SampleHeight(ref terrainHeightData, transform.m_Position + @float * componentData2.m_Bounds.min.x + x * componentData2.m_Bounds.min.z);
				x2.y = TerrainUtils.SampleHeight(ref terrainHeightData, transform.m_Position + @float * componentData2.m_Bounds.min.x + x * componentData2.m_Bounds.max.z);
				x2.z = TerrainUtils.SampleHeight(ref terrainHeightData, transform.m_Position + @float * componentData2.m_Bounds.max.x + x * componentData2.m_Bounds.max.z);
				x2.w = TerrainUtils.SampleHeight(ref terrainHeightData, transform.m_Position + @float * componentData2.m_Bounds.max.x + x * componentData2.m_Bounds.min.z);
				if ((componentData2.m_Flags & GeometryFlags.HasBase) != GeometryFlags.None)
				{
					result.m_Position.y = math.cmax(x2);
				}
				else
				{
					float4 float2 = x2.wzyz - x2.xyxw;
					float2.xy = (float2.xz + float2.yw) / (2f * math.max(0.01f, MathUtils.Size(componentData2.m_Bounds.xz)));
					@float.y = float2.x;
					x.y = float2.y;
					x = math.normalizesafe(x, math.forward());
					float3 up = math.normalizesafe(math.cross(x, @float), math.up());
					result.m_Rotation = quaternion.LookRotationSafe(x, up);
					result.m_Position.y = math.csum(x2) * 0.25f;
				}
			}
			else
			{
				result.m_Position.y = TerrainUtils.SampleHeight(ref terrainHeightData, transform.m_Position);
				angledSample = false;
			}
			result.m_Position.y += num;
		}
		result.m_Position.y += elevation.m_Elevation;
		elevation.m_Elevation += num2;
		return result;
	}
```

- `private static ApplyRootMotion(Game.Objects.Transform& transform, Game.Objects.TransformFrame& newFrameData, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationMotion> motions, Game.Rendering.BlendWeights weights, Unity.Mathematics.int2 motionRange, Unity.Mathematics.float3 deltaRange) : System.Void`  

```csharp
private static void ApplyRootMotion(ref Transform transform, ref float3 targetPosition, ref float3 targetDirection, float3 rootOffset, quaternion rootRotation)
	{
		if (!rootOffset.Equals(default(float3)))
		{
			rootOffset = math.mul(transform.m_Rotation, rootOffset);
			transform.m_Position += rootOffset;
			targetPosition = transform.m_Position;
		}
		if (!rootRotation.Equals(default(quaternion)))
		{
			transform.m_Rotation = math.mul(transform.m_Rotation, rootRotation);
			targetDirection = math.forward(transform.m_Rotation);
		}
	}
```

- `private static ApplyRootMotion(Game.Objects.Transform& transform, Unity.Mathematics.float3& targetPosition, Unity.Mathematics.float3& targetDirection, Unity.Mathematics.float3 rootOffset, Unity.Mathematics.quaternion rootRotation) : System.Void`  

```csharp
private static void ApplyRootMotion(ref Transform transform, ref float3 targetPosition, ref float3 targetDirection, float3 rootOffset, quaternion rootRotation)
	{
		if (!rootOffset.Equals(default(float3)))
		{
			rootOffset = math.mul(transform.m_Rotation, rootOffset);
			transform.m_Position += rootOffset;
			targetPosition = transform.m_Position;
		}
		if (!rootRotation.Equals(default(quaternion)))
		{
			transform.m_Rotation = math.mul(transform.m_Rotation, rootRotation);
			targetDirection = math.forward(transform.m_Rotation);
		}
	}
```

- `public static CalculateBaseCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Colossal.Mathematics.Bounds3 bounds) : Colossal.Mathematics.Quad3`  

```csharp
public static Quad3 CalculateBaseCorners(float3 position, quaternion rotation, float2 size)
	{
		size *= 0.5f;
		float3 @float = math.mul(rotation, new float3(0f, 0f, 1f)) * size.y;
		float3 float2 = math.mul(rotation, new float3(1f, 0f, 0f)) * size.x;
		float3 float3 = position + @float;
		float3 float4 = position - @float;
		return new Quad3(float3 - float2, float3 + float2, float4 + float2, float4 - float2);
	}
```

- `public static CalculateBaseCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float2 size) : Colossal.Mathematics.Quad3`  

```csharp
public static Quad3 CalculateBaseCorners(float3 position, quaternion rotation, float2 size)
	{
		size *= 0.5f;
		float3 @float = math.mul(rotation, new float3(0f, 0f, 1f)) * size.y;
		float3 float2 = math.mul(rotation, new float3(1f, 0f, 0f)) * size.x;
		float3 float3 = position + @float;
		float3 float4 = position - @float;
		return new Quad3(float3 - float2, float3 + float2, float4 + float2, float4 - float2);
	}
```

- `public static CalculateBounds(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Prefabs.ObjectGeometryData geometryData) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 CalculateBounds(Line3.Segment positionRange, quaternion rotation, Bounds3 bounds)
	{
		float3 @float = math.mul(rotation, new float3(1f, 0f, 0f));
		float3 float2 = math.mul(rotation, new float3(0f, 1f, 0f));
		float3 float3 = math.mul(rotation, new float3(0f, 0f, 1f));
		float3 x = @float * bounds.min.x;
		float3 y = @float * bounds.max.x;
		float3 x2 = float2 * bounds.min.y;
		float3 y2 = float2 * bounds.max.y;
		float3 x3 = float3 * bounds.min.z;
		float3 y3 = float3 * bounds.max.z;
		return new Bounds3
		{
			min = MathUtils.Min(positionRange) + math.min(x, y) + math.min(x2, y2) + math.min(x3, y3),
			max = MathUtils.Max(positionRange) + math.max(x, y) + math.max(x2, y2) + math.max(x3, y3)
		};
	}
```

- `public static CalculateBounds(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Objects.Stack stack, Game.Prefabs.ObjectGeometryData geometryData, Game.Prefabs.StackData stackData) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 CalculateBounds(Line3.Segment positionRange, quaternion rotation, Bounds3 bounds)
	{
		float3 @float = math.mul(rotation, new float3(1f, 0f, 0f));
		float3 float2 = math.mul(rotation, new float3(0f, 1f, 0f));
		float3 float3 = math.mul(rotation, new float3(0f, 0f, 1f));
		float3 x = @float * bounds.min.x;
		float3 y = @float * bounds.max.x;
		float3 x2 = float2 * bounds.min.y;
		float3 y2 = float2 * bounds.max.y;
		float3 x3 = float3 * bounds.min.z;
		float3 y3 = float3 * bounds.max.z;
		return new Bounds3
		{
			min = MathUtils.Min(positionRange) + math.min(x, y) + math.min(x2, y2) + math.min(x3, y3),
			max = MathUtils.Max(positionRange) + math.max(x, y) + math.max(x2, y2) + math.max(x3, y3)
		};
	}
```

- `public static CalculateBounds(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Colossal.Mathematics.Bounds3 bounds) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 CalculateBounds(Line3.Segment positionRange, quaternion rotation, Bounds3 bounds)
	{
		float3 @float = math.mul(rotation, new float3(1f, 0f, 0f));
		float3 float2 = math.mul(rotation, new float3(0f, 1f, 0f));
		float3 float3 = math.mul(rotation, new float3(0f, 0f, 1f));
		float3 x = @float * bounds.min.x;
		float3 y = @float * bounds.max.x;
		float3 x2 = float2 * bounds.min.y;
		float3 y2 = float2 * bounds.max.y;
		float3 x3 = float3 * bounds.min.z;
		float3 y3 = float3 * bounds.max.z;
		return new Bounds3
		{
			min = MathUtils.Min(positionRange) + math.min(x, y) + math.min(x2, y2) + math.min(x3, y3),
			max = MathUtils.Max(positionRange) + math.max(x, y) + math.max(x2, y2) + math.max(x3, y3)
		};
	}
```

- `public static CalculateBounds(Colossal.Mathematics.Line3+Segment positionRange, Unity.Mathematics.quaternion rotation, Colossal.Mathematics.Bounds3 bounds) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 CalculateBounds(Line3.Segment positionRange, quaternion rotation, Bounds3 bounds)
	{
		float3 @float = math.mul(rotation, new float3(1f, 0f, 0f));
		float3 float2 = math.mul(rotation, new float3(0f, 1f, 0f));
		float3 float3 = math.mul(rotation, new float3(0f, 0f, 1f));
		float3 x = @float * bounds.min.x;
		float3 y = @float * bounds.max.x;
		float3 x2 = float2 * bounds.min.y;
		float3 y2 = float2 * bounds.max.y;
		float3 x3 = float3 * bounds.min.z;
		float3 y3 = float3 * bounds.max.z;
		return new Bounds3
		{
			min = MathUtils.Min(positionRange) + math.min(x, y) + math.min(x2, y2) + math.min(x3, y3),
			max = MathUtils.Max(positionRange) + math.max(x, y) + math.max(x2, y2) + math.max(x3, y3)
		};
	}
```

- `public static CalculateGrowthRate(Game.Objects.Tree tree, Game.Objects.Plant plant, Game.Prefabs.TreeData treeData) : System.Single`  

```csharp
public static float CalculateGrowthRate(Tree tree, Plant plant, TreeData treeData)
	{
		float num = 0f;
		switch (tree.m_State & (TreeState.Teen | TreeState.Adult | TreeState.Elderly | TreeState.Dead | TreeState.Stump))
		{
		case TreeState.Teen:
			num = 0.025f * treeData.m_WoodAmount;
			break;
		case TreeState.Adult:
			num = 3f / 140f * treeData.m_WoodAmount;
			break;
		case TreeState.Elderly:
		case TreeState.Dead:
		case TreeState.Stump:
			return 0f;
		default:
			num = 0.05f * treeData.m_WoodAmount;
			break;
		}
		return num * (1f - plant.m_Pollution);
	}
```

- `public static CalculateMomentOfInertia(Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 size) : Unity.Mathematics.float3`  

```csharp
public static float3 CalculateMomentOfInertia(quaternion rotation, float3 size)
	{
		size *= 0.5f;
		size *= size;
		float3 @float = math.abs(math.rotate(rotation, new float3(size.x, 0f, 0f)));
		float3 float2 = math.abs(math.rotate(rotation, new float3(0f, size.y, 0f)));
		float3 float3 = math.abs(math.rotate(rotation, new float3(0f, 0f, size.z)));
		float3 float4 = @float + float2 + float3;
		return float4.yzx + float4.zxy;
	}
```

- `public static CalculatePointVelocity(Unity.Mathematics.float3 offset, Game.Objects.Moving moving) : Unity.Mathematics.float3`  

```csharp
public static float3 CalculatePointVelocity(float3 offset, Moving moving)
	{
		return moving.m_Velocity + math.cross(moving.m_AngularVelocity, offset);
	}
```

- `public static CalculateWoodAmount(Game.Objects.Tree tree, Game.Objects.Plant plant, Game.Objects.Damaged damaged, Game.Prefabs.TreeData treeData) : System.Single`  

```csharp
public static float CalculateWoodAmount(Tree tree, Plant plant, Damaged damaged, TreeData treeData)
	{
		float num = 0f;
		switch (tree.m_State & (TreeState.Teen | TreeState.Adult | TreeState.Elderly | TreeState.Dead | TreeState.Stump))
		{
		case TreeState.Teen:
			num = math.lerp(0.2f, 0.7f, (float)(int)tree.m_Growth * 0.00390625f) * treeData.m_WoodAmount;
			break;
		case TreeState.Adult:
			num = math.lerp(0.7f, 1f, (float)(int)tree.m_Growth * 0.00390625f) * treeData.m_WoodAmount;
			break;
		case TreeState.Elderly:
			num = treeData.m_WoodAmount;
			break;
		case TreeState.Dead:
		case TreeState.Stump:
			return 0f;
		default:
			num = math.lerp(0f, 0.2f, (float)(int)tree.m_Growth * 0.00390625f) * treeData.m_WoodAmount;
			break;
		}
		return num * (1f - plant.m_Pollution) * (1f - GetTotalDamage(damaged));
	}
```

- `public static GetActivityStartPosition(Unity.Entities.Entity prefab, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Game.Objects.Transform activityTransform, Game.Objects.TransformState state, Game.Prefabs.ActivityType activityType, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityCondition conditions, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers, Game.Objects.ObjectUtils+ActivityStartPositionCache& cache) : Game.Objects.Transform`  

```csharp
public static Transform GetActivityStartPosition(Entity prefab, DynamicBuffer<MeshGroup> meshGroups, Transform activityTransform, TransformState state, ActivityType activityType, AnimatedPropID propID, ActivityCondition conditions, ref BufferLookup<SubMeshGroup> subMeshGroupBuffers, ref BufferLookup<CharacterElement> characterElementBuffers, ref BufferLookup<SubMesh> subMeshBuffers, ref BufferLookup<Game.Prefabs.AnimationClip> animationClipBuffers, ref BufferLookup<AnimationMotion> animationMotionBuffers, ref ActivityStartPositionCache cache)
	{
		if (activityType != cache.m_ActivityType)
		{
			cache.m_ActivityType = activityType;
			CharacterElement characterElement;
			Game.Prefabs.AnimationClip animationClip;
			bool crossFade;
			float stateDuration = GetStateDuration(prefab, state, (byte)activityType, propID, conditions, meshGroups, ref subMeshGroupBuffers, ref characterElementBuffers, ref subMeshBuffers, ref animationClipBuffers, out characterElement, out animationClip, out crossFade);
			if (animationClip.m_MotionRange.y != animationClip.m_MotionRange.x && stateDuration > 0f)
			{
				DynamicBuffer<AnimationMotion> motions = animationMotionBuffers[characterElement.m_Style];
				GetRootMotion(motions, animationClip.m_MotionRange, characterElement.m_ShapeWeights, 0f, out var rootOffset, out var rootVelocity, out var rootRotation);
				GetRootMotion(motions, animationClip.m_MotionRange, characterElement.m_ShapeWeights, 1f, out var rootOffset2, out rootVelocity, out var rootRotation2);
				cache.m_RotationOffset = math.inverse(rootRotation2);
				cache.m_PositionOffset = math.mul(cache.m_RotationOffset, rootOffset - rootOffset2);
				cache.m_RotationOffset = math.mul(cache.m_RotationOffset, rootRotation);
			}
			else
			{
				cache.m_PositionOffset = default(float3);
				cache.m_RotationOffset = quaternion.identity;
			}
		}
		if (cache.m_ActivityType != ActivityType.None)
		{
			return LocalToWorld(activityTransform, cache.m_PositionOffset, cache.m_RotationOffset);
		}
		return activityTransform;
	}
```

- `public static GetBounds(Game.Prefabs.ObjectGeometryData geometryData) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 GetBounds(Stack stack, ObjectGeometryData geometryData, StackData stackData)
	{
		Bounds3 bounds = GetBounds(geometryData);
		switch (stackData.m_Direction)
		{
		case StackDirection.Right:
			bounds.x = stack.m_Range;
			break;
		case StackDirection.Up:
			bounds.y = stack.m_Range;
			break;
		case StackDirection.Forward:
			bounds.z = stack.m_Range;
			break;
		}
		return bounds;
	}
```

- `public static GetBounds(Game.Objects.Stack stack, Game.Prefabs.ObjectGeometryData geometryData, Game.Prefabs.StackData stackData) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 GetBounds(Stack stack, ObjectGeometryData geometryData, StackData stackData)
	{
		Bounds3 bounds = GetBounds(geometryData);
		switch (stackData.m_Direction)
		{
		case StackDirection.Right:
			bounds.x = stack.m_Range;
			break;
		case StackDirection.Up:
			bounds.y = stack.m_Range;
			break;
		case StackDirection.Forward:
			bounds.z = stack.m_Range;
			break;
		}
		return bounds;
	}
```

- `public static GetCollisionMask(Game.Prefabs.ObjectGeometryData geometryData, Game.Objects.Elevation elevation, System.Boolean ignoreMarkers) : Game.Common.CollisionMask`  

```csharp
public static CollisionMask GetCollisionMask(ObjectGeometryData geometryData, bool ignoreMarkers)
	{
		if ((geometryData.m_Flags & GeometryFlags.Marker) != 0 && ignoreMarkers)
		{
			return (CollisionMask)0;
		}
		CollisionMask collisionMask = (CollisionMask)0;
		if ((geometryData.m_Flags & (GeometryFlags.ExclusiveGround | GeometryFlags.BaseCollision)) != GeometryFlags.None)
		{
			collisionMask |= CollisionMask.ExclusiveGround;
		}
		return collisionMask | (CollisionMask.OnGround | CollisionMask.Overground);
	}
```

- `public static GetCollisionMask(Game.Prefabs.ObjectGeometryData geometryData, System.Boolean ignoreMarkers) : Game.Common.CollisionMask`  

```csharp
public static CollisionMask GetCollisionMask(ObjectGeometryData geometryData, bool ignoreMarkers)
	{
		if ((geometryData.m_Flags & GeometryFlags.Marker) != 0 && ignoreMarkers)
		{
			return (CollisionMask)0;
		}
		CollisionMask collisionMask = (CollisionMask)0;
		if ((geometryData.m_Flags & (GeometryFlags.ExclusiveGround | GeometryFlags.BaseCollision)) != GeometryFlags.None)
		{
			collisionMask |= CollisionMask.ExclusiveGround;
		}
		return collisionMask | (CollisionMask.OnGround | CollisionMask.Overground);
	}
```

- `public static GetContructionCost(System.Int32 constructionCost, Game.Objects.Tree tree, Game.Prefabs.EconomyParameterData& economyParameterData) : System.Int32`  

```csharp
public static int GetContructionCost(int constructionCost, Tree tree, in EconomyParameterData economyParameterData)
	{
		return (tree.m_State & (TreeState.Teen | TreeState.Adult | TreeState.Elderly | TreeState.Dead | TreeState.Stump)) switch
		{
			TreeState.Teen => constructionCost * economyParameterData.m_TreeCostMultipliers.x, 
			TreeState.Adult => constructionCost * economyParameterData.m_TreeCostMultipliers.y, 
			TreeState.Elderly => constructionCost * economyParameterData.m_TreeCostMultipliers.z, 
			_ => constructionCost, 
		};
	}
```

- `private static GetParentActivity(System.Byte activity) : System.Byte`  

```csharp
private static byte GetParentActivity(byte activity)
	{
		if (activity == 6)
		{
			return 5;
		}
		return 0;
	}
```

- `public static GetRebuildCost(System.Int32 constructionCost) : System.Int32`  

```csharp
public static int GetRebuildCost(int constructionCost, Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		int refundAmount = GetRefundAmount(recent, simulationFrame, economyParameterData);
		constructionCost = math.max(constructionCost / 4, constructionCost - refundAmount);
		return GetRebuildCost(constructionCost);
	}
```

- `public static GetRebuildCost(System.Int32 constructionCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  

```csharp
public static int GetRebuildCost(int constructionCost, Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		int refundAmount = GetRefundAmount(recent, simulationFrame, economyParameterData);
		constructionCost = math.max(constructionCost / 4, constructionCost - refundAmount);
		return GetRebuildCost(constructionCost);
	}
```

- `public static GetRefundAmount(Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  

```csharp
public static int GetRefundAmount(Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		if ((float)simulationFrame < (float)recent.m_ModificationFrame + 262144f * economyParameterData.m_BuildRefundTimeRange.x)
		{
			return (int)((float)recent.m_ModificationCost * economyParameterData.m_BuildRefundPercentage.x);
		}
		if ((float)simulationFrame < (float)recent.m_ModificationFrame + 262144f * economyParameterData.m_BuildRefundTimeRange.y)
		{
			return (int)((float)recent.m_ModificationCost * economyParameterData.m_BuildRefundPercentage.y);
		}
		if ((float)simulationFrame < (float)recent.m_ModificationFrame + 262144f * economyParameterData.m_BuildRefundTimeRange.z)
		{
			return (int)((float)recent.m_ModificationCost * economyParameterData.m_BuildRefundPercentage.z);
		}
		return 0;
	}
```

- `public static GetRelocationCost(System.Int32 constructionCost, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  

```csharp
public static int GetRelocationCost(int constructionCost, Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		int refundAmount = GetRefundAmount(recent, simulationFrame, economyParameterData);
		constructionCost = math.max(constructionCost / 4, constructionCost - refundAmount);
		return GetRelocationCost(constructionCost, economyParameterData);
	}
```

- `public static GetRelocationCost(System.Int32 constructionCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  

```csharp
public static int GetRelocationCost(int constructionCost, Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		int refundAmount = GetRefundAmount(recent, simulationFrame, economyParameterData);
		constructionCost = math.max(constructionCost / 4, constructionCost - refundAmount);
		return GetRelocationCost(constructionCost, economyParameterData);
	}
```

- `public static GetRemainingConstructionFrames(Game.Objects.UnderConstruction underConstruction) : System.UInt32`  

```csharp
public static uint GetRemainingConstructionFrames(UnderConstruction underConstruction)
	{
		return (uint)(math.clamp(100 - underConstruction.m_Progress, 0, 100) * (int)(8192u / (uint)math.max(1, underConstruction.m_Speed)) + 64);
	}
```

- `public static GetRootMotion(Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationMotion> motions, Unity.Mathematics.int2 range, Game.Rendering.BlendWeights weights, System.Single t, Unity.Mathematics.float3& rootOffset, Unity.Mathematics.float3& rootVelocity, Unity.Mathematics.quaternion& rootRotation) : System.Void`  

```csharp
private static void GetRootMotion(AnimationMotion motion, float t, out float3 rootOffset, out float3 rootVelocity, out quaternion rootRotation)
	{
		Bezier4x3 curve = new Bezier4x3(motion.m_StartOffset, motion.m_StartOffset, motion.m_EndOffset, motion.m_EndOffset);
		rootOffset = MathUtils.Position(curve, t);
		rootVelocity = MathUtils.Tangent(curve, t);
		rootRotation = math.slerp(motion.m_StartRotation, motion.m_EndRotation, t);
	}
```

- `private static GetRootMotion(Game.Prefabs.AnimationMotion motion, System.Single t, Unity.Mathematics.float3& rootOffset, Unity.Mathematics.float3& rootVelocity, Unity.Mathematics.quaternion& rootRotation) : System.Void`  

```csharp
private static void GetRootMotion(AnimationMotion motion, float t, out float3 rootOffset, out float3 rootVelocity, out quaternion rootRotation)
	{
		Bezier4x3 curve = new Bezier4x3(motion.m_StartOffset, motion.m_StartOffset, motion.m_EndOffset, motion.m_EndOffset);
		rootOffset = MathUtils.Position(curve, t);
		rootVelocity = MathUtils.Tangent(curve, t);
		rootRotation = math.slerp(motion.m_StartRotation, motion.m_EndRotation, t);
	}
```

- `public static GetSize(Colossal.Mathematics.Bounds3 bounds) : Unity.Mathematics.float3`  

```csharp
public static float3 GetSize(Bounds3 bounds)
	{
		return new float3
		{
			xz = math.max(-bounds.min, bounds.max).xz * 2f,
			y = bounds.max.y
		};
	}
```

- `public static GetStandingLegCount(Game.Prefabs.ObjectGeometryData objectGeometryData, System.Int32& legCount) : System.Boolean`  

```csharp
public static bool GetStandingLegCount(ObjectGeometryData objectGeometryData, out int legCount)
	{
		bool3 test = new bool3
		{
			x = ((objectGeometryData.m_Flags & GeometryFlags.Standing) != 0),
			yz = (objectGeometryData.m_LegOffset != 0f)
		};
		int3 @int = math.select((int3)0, (int3)1, test);
		legCount = @int.x << math.csum(@int.yz);
		return test.x;
	}
```

- `public static GetStandingLegOffset(Game.Prefabs.ObjectGeometryData objectGeometryData, System.Int32 legIndex) : Unity.Mathematics.float3`  

```csharp
public static float3 GetStandingLegOffset(ObjectGeometryData objectGeometryData, int legIndex)
	{
		float3 result = default(float3);
		bool2 test = (new int2(legIndex, math.select(legIndex, legIndex >> 1, objectGeometryData.m_LegOffset.x != 0f)) & 1) != 0;
		result.xz = math.select(-objectGeometryData.m_LegOffset, objectGeometryData.m_LegOffset, test);
		return result;
	}
```

- `public static GetStandingLegPosition(Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Objects.Transform transform, System.Int32 legIndex) : Unity.Mathematics.float3`  

```csharp
public static float3 GetStandingLegPosition(ObjectGeometryData objectGeometryData, Transform transform, int legIndex)
	{
		return transform.m_Position + math.mul(v: GetStandingLegOffset(objectGeometryData, legIndex), q: transform.m_Rotation);
	}
```

- `private static GetStateDuration(Unity.Entities.Entity prefab, Game.Objects.TransformState state, System.Byte activity, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityCondition conditions, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Game.Prefabs.CharacterElement& characterElement, Game.Prefabs.AnimationClip& animationClip, System.Boolean& crossFade) : System.Single`  

```csharp
private static float GetStateDuration(Entity prefab, TransformState state, byte activity, AnimatedPropID propID, ActivityCondition conditions, DynamicBuffer<MeshGroup> meshGroups, ref BufferLookup<SubMeshGroup> subMeshGroupBuffers, ref BufferLookup<CharacterElement> characterElementBuffers, ref BufferLookup<SubMesh> subMeshBuffers, ref BufferLookup<Game.Prefabs.AnimationClip> animationClipBuffers, out CharacterElement characterElement, out Game.Prefabs.AnimationClip animationClip, out bool crossFade)
	{
		characterElement = default(CharacterElement);
		animationClip = default(Game.Prefabs.AnimationClip);
		crossFade = false;
		AnimationType animationType;
		switch (state)
		{
		case TransformState.Idle:
			animationType = AnimationType.Idle;
			break;
		case TransformState.Start:
			animationType = AnimationType.Start;
			break;
		case TransformState.End:
			animationType = AnimationType.End;
			break;
		case TransformState.Action:
			animationType = AnimationType.Action;
			break;
		case TransformState.Done:
			animationType = AnimationType.Action;
			break;
		default:
			return 0f;
		}
		float num = 0f;
		int num2 = 0;
		DynamicBuffer<CharacterElement> bufferData = default(DynamicBuffer<CharacterElement>);
		DynamicBuffer<SubMesh> dynamicBuffer = default(DynamicBuffer<SubMesh>);
		if (subMeshGroupBuffers.TryGetBuffer(prefab, out var bufferData2))
		{
			if (meshGroups.IsCreated)
			{
				num2 = meshGroups.Length;
			}
			crossFade = characterElementBuffers.TryGetBuffer(prefab, out bufferData);
		}
		else
		{
			dynamicBuffer = subMeshBuffers[prefab];
			num2 = dynamicBuffer.Length;
		}
		for (int i = 0; i < num2; i++)
		{
			CharacterElement characterElement2 = default(CharacterElement);
			if (bufferData.IsCreated)
			{
				CollectionUtils.TryGet(meshGroups, i, out var value);
				characterElement2 = bufferData[value.m_SubMeshGroup];
			}
			else
			{
				int index = i;
				if (bufferData2.IsCreated)
				{
					CollectionUtils.TryGet(meshGroups, i, out var value2);
					index = bufferData2[value2.m_SubMeshGroup].m_SubMeshRange.x;
				}
				characterElement2.m_Style = dynamicBuffer[index].m_SubMesh;
			}
			if (!animationClipBuffers.TryGetBuffer(characterElement2.m_Style, out var bufferData3))
			{
				continue;
			}
			int num3 = int.MaxValue;
			float y = 0f;
			for (int j = 0; j < bufferData3.Length; j++)
			{
				Game.Prefabs.AnimationClip animationClip2 = bufferData3[j];
				if (animationClip2.m_Type == animationType && animationClip2.m_Activity == (ActivityType)activity && animationClip2.m_Layer == AnimationLayer.Body && animationClip2.m_PropID == propID)
				{
					ActivityCondition activityCondition = animationClip2.m_Conditions ^ conditions;
					if (activityCondition == (ActivityCondition)0u)
					{
						y = animationClip2.m_AnimationLength;
						characterElement = characterElement2;
						animationClip = animationClip2;
						break;
					}
					int num4 = math.countbits((uint)activityCondition);
					if (num4 < num3)
					{
						num3 = num4;
						y = animationClip2.m_AnimationLength;
						characterElement = characterElement2;
						animationClip = animationClip2;
					}
				}
			}
			num = math.max(num, y);
		}
		return num;
	}
```

- `public static GetSubParentMesh(Game.Objects.ElevationFlags elevationFlags) : System.Int32`  

```csharp
public static int GetSubParentMesh(ElevationFlags elevationFlags)
	{
		return (elevationFlags & (ElevationFlags.Stacked | ElevationFlags.OnGround)) switch
		{
			ElevationFlags.OnGround => -2, 
			ElevationFlags.Stacked => 1000, 
			ElevationFlags.Stacked | ElevationFlags.OnGround => -1001, 
			_ => 0, 
		};
	}
```

- `public static GetTerrainSmoothingWidth(Game.Prefabs.ObjectGeometryData objectGeometryData) : System.Single`  

```csharp
public static float GetTerrainSmoothingWidth(float2 size)
	{
		return math.max(8f, math.length(size) * (1f / 12f));
	}
```

- `public static GetTerrainSmoothingWidth(Unity.Mathematics.float2 size) : System.Single`  

```csharp
public static float GetTerrainSmoothingWidth(float2 size)
	{
		return math.max(8f, math.length(size) * (1f / 12f));
	}
```

- `public static GetTotalDamage(Game.Objects.Damaged damaged) : System.Single`  

```csharp
public static float GetTotalDamage(Damaged damaged)
	{
		float3 damage = damaged.m_Damage;
		damage.z = math.max(0f, damage.z - math.min(0.5f, math.csum(damage.xy)));
		return math.min(1f, math.csum(damage));
	}
```

- `public static GetTripDelayFrames(Game.Objects.UnderConstruction underConstruction, Game.Pathfind.PathInformation pathInformation) : System.UInt32`  

```csharp
public static uint GetTripDelayFrames(UnderConstruction underConstruction, PathInformation pathInformation)
	{
		uint remainingConstructionFrames = GetRemainingConstructionFrames(underConstruction);
		uint num = (uint)(pathInformation.m_Duration * 60f + 0.5f);
		return math.select(remainingConstructionFrames - num, 0u, num > remainingConstructionFrames);
	}
```

- `public static GetUpgradeCost(System.Int32 constructionCost, System.Int32 originalCost) : System.Int32`  

```csharp
public static int GetUpgradeCost(int constructionCost, int originalCost, Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		if (constructionCost >= originalCost)
		{
			return GetUpgradeCost(constructionCost, originalCost);
		}
		recent.m_ModificationCost = math.min(recent.m_ModificationCost, originalCost - constructionCost);
		return -GetRefundAmount(recent, simulationFrame, economyParameterData);
	}
```

- `public static GetUpgradeCost(System.Int32 constructionCost, System.Int32 originalCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  

```csharp
public static int GetUpgradeCost(int constructionCost, int originalCost, Recent recent, uint simulationFrame, EconomyParameterData economyParameterData)
	{
		if (constructionCost >= originalCost)
		{
			return GetUpgradeCost(constructionCost, originalCost);
		}
		recent.m_ModificationCost = math.min(recent.m_ModificationCost, originalCost - constructionCost);
		return -GetRefundAmount(recent, simulationFrame, economyParameterData);
	}
```

- `public static InitializeTreeState(System.Single age) : Game.Objects.Tree`  

```csharp
public static Tree InitializeTreeState(float age)
	{
		Tree result = default(Tree);
		if (age < 0.1f)
		{
			result.m_Growth = (byte)math.clamp(Mathf.FloorToInt(age * 2560f), 0, 255);
		}
		else if (age < 0.25f)
		{
			result.m_State = TreeState.Teen;
			result.m_Growth = (byte)math.clamp(Mathf.FloorToInt((age - 0.1f) * 1706.6666f), 0, 255);
		}
		else if (age < 0.6f)
		{
			result.m_State = TreeState.Adult;
			result.m_Growth = (byte)math.clamp(Mathf.FloorToInt((age - 0.25f) * 731.4286f), 0, 255);
		}
		else if (age < 0.95000005f)
		{
			result.m_State = TreeState.Elderly;
			result.m_Growth = (byte)math.clamp(Mathf.FloorToInt((age - 0.6f) * 731.4286f), 0, 255);
		}
		else
		{
			result.m_State = TreeState.Dead;
			result.m_Growth = (byte)math.clamp(Mathf.FloorToInt((age - 0.95f) * 5120f), 0, 255);
		}
		return result;
	}
```

- `public static InverseTransform(Game.Objects.Transform transform) : Game.Objects.Transform`  

```csharp
public static Transform InverseTransform(Transform transform)
	{
		Transform result = default(Transform);
		result.m_Position = -transform.m_Position;
		result.m_Rotation = math.inverse(transform.m_Rotation);
		return result;
	}
```

- `public static LocalToWorld(Game.Objects.Transform transform, Unity.Mathematics.float3 position) : Unity.Mathematics.float3`  

```csharp
public static Transform LocalToWorld(Transform parentTransform, Transform transform)
	{
		Transform result = default(Transform);
		result.m_Position = parentTransform.m_Position + math.mul(parentTransform.m_Rotation, transform.m_Position);
		result.m_Rotation = math.mul(parentTransform.m_Rotation, transform.m_Rotation);
		return result;
	}
```

- `public static LocalToWorld(Unity.Mathematics.float3 transformPosition, Unity.Mathematics.quaternion transformRotation, Unity.Mathematics.float3 position) : Unity.Mathematics.float3`  

```csharp
public static Transform LocalToWorld(Transform parentTransform, Transform transform)
	{
		Transform result = default(Transform);
		result.m_Position = parentTransform.m_Position + math.mul(parentTransform.m_Rotation, transform.m_Position);
		result.m_Rotation = math.mul(parentTransform.m_Rotation, transform.m_Rotation);
		return result;
	}
```

- `public static LocalToWorld(Unity.Mathematics.float3 transformPosition, Unity.Mathematics.quaternion transformRotation, Colossal.Mathematics.Bezier4x3 curve) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Transform LocalToWorld(Transform parentTransform, Transform transform)
	{
		Transform result = default(Transform);
		result.m_Position = parentTransform.m_Position + math.mul(parentTransform.m_Rotation, transform.m_Position);
		result.m_Rotation = math.mul(parentTransform.m_Rotation, transform.m_Rotation);
		return result;
	}
```

- `public static LocalToWorld(Game.Objects.Transform transform, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation) : Game.Objects.Transform`  

```csharp
public static Transform LocalToWorld(Transform parentTransform, Transform transform)
	{
		Transform result = default(Transform);
		result.m_Position = parentTransform.m_Position + math.mul(parentTransform.m_Rotation, transform.m_Position);
		result.m_Rotation = math.mul(parentTransform.m_Rotation, transform.m_Rotation);
		return result;
	}
```

- `public static LocalToWorld(Game.Rendering.InterpolatedTransform transform, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation) : Game.Rendering.InterpolatedTransform`  

```csharp
public static Transform LocalToWorld(Transform parentTransform, Transform transform)
	{
		Transform result = default(Transform);
		result.m_Position = parentTransform.m_Position + math.mul(parentTransform.m_Rotation, transform.m_Position);
		result.m_Rotation = math.mul(parentTransform.m_Rotation, transform.m_Rotation);
		return result;
	}
```

- `public static LocalToWorld(Game.Objects.Transform parentTransform, Game.Objects.Transform transform) : Game.Objects.Transform`  

```csharp
public static Transform LocalToWorld(Transform parentTransform, Transform transform)
	{
		Transform result = default(Transform);
		result.m_Position = parentTransform.m_Position + math.mul(parentTransform.m_Rotation, transform.m_Position);
		result.m_Rotation = math.mul(parentTransform.m_Rotation, transform.m_Rotation);
		return result;
	}
```

- `public static UpdateAnimation(Unity.Entities.Entity prefab, System.Single timeStep, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers, Game.Rendering.AnimatedPropID oldPropID, Game.Rendering.AnimatedPropID newPropID, Game.Prefabs.ActivityCondition conditions, System.Single& maxSpeed, System.Byte& activity, Unity.Mathematics.float3& targetPosition, Unity.Mathematics.float3& targetDirection, Game.Objects.Transform& transform, Game.Objects.TransformFrame& oldFrameData, Game.Objects.TransformFrame& newFrameData) : System.Void`  

```csharp
public static void UpdateAnimation(Entity prefab, float timeStep, DynamicBuffer<MeshGroup> meshGroups, ref BufferLookup<SubMeshGroup> subMeshGroupBuffers, ref BufferLookup<CharacterElement> characterElementBuffers, ref BufferLookup<SubMesh> subMeshBuffers, ref BufferLookup<Game.Prefabs.AnimationClip> animationClipBuffers, ref BufferLookup<AnimationMotion> animationMotionBuffers, AnimatedPropID oldPropID, AnimatedPropID newPropID, ActivityCondition conditions, ref float maxSpeed, ref byte activity, ref float3 targetPosition, ref float3 targetDirection, ref Transform transform, ref TransformFrame oldFrameData, ref TransformFrame newFrameData)
	{
		bool flag = newFrameData.m_Activity == 0;
		bool flag2 = oldFrameData.m_Activity == 0;
		if (oldFrameData.m_Activity != newFrameData.m_Activity)
		{
			byte parentActivity = GetParentActivity(oldFrameData.m_Activity);
			byte parentActivity2 = GetParentActivity(newFrameData.m_Activity);
			if (parentActivity != 0)
			{
				if (parentActivity != newFrameData.m_Activity)
				{
					newFrameData.m_Activity = parentActivity;
				}
				else
				{
					flag = true;
				}
			}
			else if (parentActivity2 != 0)
			{
				if (parentActivity2 != oldFrameData.m_Activity)
				{
					newFrameData.m_Activity = parentActivity2;
				}
				else
				{
					flag2 = true;
				}
			}
		}
		CharacterElement characterElement;
		Game.Prefabs.AnimationClip animationClip;
		bool crossFade;
		float stateDuration;
		switch (oldFrameData.m_State)
		{
		case TransformState.Default:
			flag2 = true;
			break;
		case TransformState.Idle:
			if (newFrameData.m_State == TransformState.Idle && newFrameData.m_Activity == oldFrameData.m_Activity)
			{
				newFrameData.m_StateTimer = (ushort)(oldFrameData.m_StateTimer + 1);
				return;
			}
			stateDuration = GetStateDuration(prefab, TransformState.Idle, oldFrameData.m_Activity, oldPropID, conditions, meshGroups, ref subMeshGroupBuffers, ref characterElementBuffers, ref subMeshBuffers, ref animationClipBuffers, out characterElement, out animationClip, out crossFade);
			if (animationClip.m_Playback != AnimationPlayback.RandomLoop && stateDuration > 0f)
			{
				float2 @float = default(float2);
				@float.x = (float)(int)oldFrameData.m_StateTimer * timeStep;
				@float.y = @float.x + timeStep;
				@float = math.floor(@float / math.select(stateDuration, stateDuration * 0.5f, animationClip.m_Playback == AnimationPlayback.HalfLoop));
				if (@float.x > @float.y - 0.5f)
				{
					newFrameData.m_State = TransformState.Idle;
					newFrameData.m_Activity = oldFrameData.m_Activity;
					newFrameData.m_StateTimer = (ushort)(oldFrameData.m_StateTimer + 1);
					maxSpeed = 0f;
					return;
				}
			}
			break;
		case TransformState.Move:
			if (newFrameData.m_State == TransformState.Move)
			{
				newFrameData.m_StateTimer = (ushort)(oldFrameData.m_StateTimer + 1);
				return;
			}
			break;
		case TransformState.Start:
		{
			stateDuration = GetStateDuration(prefab, TransformState.Start, oldFrameData.m_Activity, oldPropID, conditions, meshGroups, ref subMeshGroupBuffers, ref characterElementBuffers, ref subMeshBuffers, ref animationClipBuffers, out characterElement, out animationClip, out crossFade);
			float2 x3 = default(float2);
			x3.x = (float)(int)oldFrameData.m_StateTimer * timeStep;
			x3.y = x3.x + timeStep;
			x3 = math.min(x3, stateDuration);
			if (animationClip.m_MotionRange.y != animationClip.m_MotionRange.x && x3.y > x3.x && stateDuration > 0f)
			{
				DynamicBuffer<AnimationMotion> motions3 = animationMotionBuffers[characterElement.m_Style];
				ApplyRootMotion(ref transform, ref newFrameData, motions3, characterElement.m_ShapeWeights, animationClip.m_MotionRange, new float3(x3, 1f) / stateDuration);
				targetPosition = transform.m_Position;
				targetDirection = math.forward(transform.m_Rotation);
			}
			if (x3.y < stateDuration)
			{
				newFrameData.m_State = TransformState.Start;
				newFrameData.m_Activity = oldFrameData.m_Activity;
				newFrameData.m_StateTimer = (ushort)(oldFrameData.m_StateTimer + 1);
				maxSpeed = 0f;
				return;
			}
			if (animationClip.m_MotionRange.y == animationClip.m_MotionRange.x)
			{
				ApplyRootMotion(ref transform, ref targetPosition, ref targetDirection, animationClip.m_RootOffset, animationClip.m_RootRotation);
			}
			if (newFrameData.m_Activity == oldFrameData.m_Activity)
			{
				return;
			}
			break;
		}
		case TransformState.End:
		{
			stateDuration = GetStateDuration(prefab, TransformState.End, oldFrameData.m_Activity, oldPropID, conditions, meshGroups, ref subMeshGroupBuffers, ref characterElementBuffers, ref subMeshBuffers, ref animationClipBuffers, out characterElement, out animationClip, out crossFade);
			float2 x2 = default(float2);
			x2.x = (float)(int)oldFrameData.m_StateTimer * timeStep;
			x2.y = x2.x + timeStep;
			x2 = math.min(x2, stateDuration);
			if (animationClip.m_MotionRange.y != animationClip.m_MotionRange.x && x2.y > x2.x && stateDuration > 0f)
			{
				DynamicBuffer<AnimationMotion> motions2 = animationMotionBuffers[characterElement.m_Style];
				ApplyRootMotion(ref transform, ref newFrameData, motions2, characterElement.m_ShapeWeights, animationClip.m_MotionRange, new float3(x2, 1f) / stateDuration);
				targetPosition = transform.m_Position;
				targetDirection = math.forward(transform.m_Rotation);
			}
			if (x2.y < stateDuration)
			{
				newFrameData.m_State = TransformState.End;
				newFrameData.m_Activity = oldFrameData.m_Activity;
				newFrameData.m_StateTimer = (ushort)(oldFrameData.m_StateTimer + 1);
				maxSpeed = 0f;
				return;
			}
			if (animationClip.m_MotionRange.y == animationClip.m_MotionRange.x)
			{
				ApplyRootMotion(ref transform, ref targetPosition, ref targetDirection, animationClip.m_RootOffset, animationClip.m_RootRotation);
			}
			flag2 = true;
			break;
		}
		case TransformState.Action:
		case TransformState.Done:
		{
			stateDuration = GetStateDuration(prefab, TransformState.Action, oldFrameData.m_Activity, oldPropID, conditions, meshGroups, ref subMeshGroupBuffers, ref characterElementBuffers, ref subMeshBuffers, ref animationClipBuffers, out characterElement, out animationClip, out crossFade);
			float2 x = default(float2);
			x.x = (float)(int)oldFrameData.m_StateTimer * timeStep;
			x.y = x.x + timeStep;
			x = math.min(x, stateDuration);
			if (animationClip.m_MotionRange.y != animationClip.m_MotionRange.x && x.y > x.x && stateDuration > 0f)
			{
				DynamicBuffer<AnimationMotion> motions = animationMotionBuffers[characterElement.m_Style];
				ApplyRootMotion(ref transform, ref newFrameData, motions, characterElement.m_ShapeWeights, animationClip.m_MotionRange, new float3(x, 1f) / stateDuration);
				if (animationClip.m_Playback != AnimationPlayback.OptionalOnce)
				{
					targetPosition = transform.m_Position;
					targetDirection = math.forward(transform.m_Rotation);
				}
			}
			if (animationClip.m_Playback != AnimationPlayback.OptionalOnce || maxSpeed < 0.1f)
			{
				if (x.y < stateDuration)
				{
					newFrameData.m_State = TransformState.Action;
					newFrameData.m_Activity = oldFrameData.m_Activity;
					newFrameData.m_StateTimer = (ushort)(oldFrameData.m_StateTimer + 1);
					maxSpeed = 0f;
					return;
				}
				if (newFrameData.m_Activity == oldFrameData.m_Activity && newFrameData.m_Activity == 10)
				{
					newFrameData.m_State = TransformState.Done;
					newFrameData.m_Activity = oldFrameData.m_Activity;
					newFrameData.m_StateTimer = (ushort)math.min(65535, oldFrameData.m_StateTimer + 1);
					maxSpeed = 0f;
					return;
				}
			}
			if (newFrameData.m_Activity == oldFrameData.m_Activity)
			{
				targetDirection = default(float3);
				activity = 0;
				newFrameData.m_Activity = activity;
			}
			if (animationClip.m_MotionRange.y == animationClip.m_MotionRange.x)
			{
				ApplyRootMotion(ref transform, ref targetPosition, ref targetDirection, animationClip.m_RootOffset, animationClip.m_RootRotation);
			}
			flag2 = true;
			break;
		}
		}
		if (!flag2 && (stateDuration = GetStateDuration(prefab, TransformState.End, oldFrameData.m_Activity, oldPropID, conditions, meshGroups, ref subMeshGroupBuffers, ref characterElementBuffers, ref subMeshBuffers, ref animationClipBuffers, out characterElement, out animationClip, out var crossFade2)) > 0f)
		{
			newFrameData.m_State = TransformState.End;
			newFrameData.m_Activity = oldFrameData.m_Activity;
		}
		else if (!flag && (stateDuration = GetStateDuration(prefab, TransformState.Start, newFrameData.m_Activity, newPropID, conditions, meshGroups, ref subMeshGroupBuffers, ref characterElementBuffers, ref subMeshBuffers, ref animationClipBuffers, out characterElement, out animationClip, out crossFade2)) > 0f)
		{
			newFrameData.m_State = TransformState.Start;
		}
		else
		{
			if (!((stateDuration = GetStateDuration(prefab, TransformState.Action, newFrameData.m_Activity, newPropID, conditions, meshGroups, ref subMeshGroupBuffers, ref characterElementBuffers, ref subMeshBuffers, ref animationClipBuffers, out characterElement, out animationClip, out crossFade2)) > 0f))
			{
				return;
			}
			newFrameData.m_State = TransformState.Action;
		}
		newFrameData.m_StateTimer = (ushort)math.select(0, 1, crossFade2);
		maxSpeed = 0f;
		if (crossFade2 && animationClip.m_MotionRange.y != animationClip.m_MotionRange.x && stateDuration > 0f)
		{
			DynamicBuffer<AnimationMotion> motions4 = animationMotionBuffers[characterElement.m_Style];
			ApplyRootMotion(ref transform, ref newFrameData, motions4, characterElement.m_ShapeWeights, animationClip.m_MotionRange, new float3(0f, timeStep, 1f) / stateDuration);
			if (newFrameData.m_State != TransformState.Action || animationClip.m_Playback != AnimationPlayback.OptionalOnce)
			{
				targetPosition = transform.m_Position;
				targetDirection = math.forward(transform.m_Rotation);
			}
		}
	}
```

- `public static UpdateResourcesDamage(Unity.Entities.Entity entity, System.Single totalDamage, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterData, Unity.Entities.BufferLookup`1[[Game.Economy.Resources, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourcesData) : System.Void`  

```csharp
public static void UpdateResourcesDamage(Entity entity, float totalDamage, ref BufferLookup<Renter> renterData, ref BufferLookup<Game.Economy.Resources> resourcesData)
	{
		if (!renterData.TryGetBuffer(entity, out var bufferData))
		{
			return;
		}
		for (int i = 0; i < bufferData.Length; i++)
		{
			if (!resourcesData.TryGetBuffer(bufferData[i].m_Renter, out var bufferData2))
			{
				continue;
			}
			for (int j = 0; j < bufferData2.Length; j++)
			{
				Game.Economy.Resources value = bufferData2[j];
				if (value.m_Resource != Resource.Money)
				{
					value.m_Amount = (int)((float)value.m_Amount * (1f - totalDamage));
				}
				bufferData2[j] = value;
			}
		}
	}
```

- `public static WorldToLocal(Game.Objects.Transform inverseParentTransform, Game.Objects.Transform transform) : Game.Objects.Transform`  

```csharp
public static float3 WorldToLocal(Transform inverseParentTransform, float3 position)
	{
		return math.mul(inverseParentTransform.m_Rotation, position + inverseParentTransform.m_Position);
	}
```

- `public static WorldToLocal(Game.Objects.Transform inverseParentTransform, Unity.Mathematics.float3 position) : Unity.Mathematics.float3`  

```csharp
public static float3 WorldToLocal(Transform inverseParentTransform, float3 position)
	{
		return math.mul(inverseParentTransform.m_Rotation, position + inverseParentTransform.m_Position);
	}
```


## Nested types

- `Game.Objects.ObjectUtils+ActivityStartPositionCache`  

