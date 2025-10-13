# Game.Simulation.CreatureCollisionIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct CreatureCollisionIterator : Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>
{
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
    public Unity.Entities.ComponentLookup<Game.Creatures.GroupMember> m_GroupMemberData;
    public Unity.Entities.ComponentLookup<Game.Routes.Waypoint> m_WaypointData;
    public Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> m_TaxiStandData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.AreaLane> m_AreaLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
    public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticObjectSearchTree;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingObjectSearchTree;
    public Unity.Entities.Entity m_Entity;
    public Unity.Entities.Entity m_Leader;
    public Unity.Entities.Entity m_CurrentLane;
    public Unity.Entities.Entity m_CurrentVehicle;
    public System.Single m_CurvePosition;
    public System.Single m_TimeStep;
    public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
    public Colossal.Mathematics.Bounds1 m_SpeedRange;
    public Unity.Mathematics.float3 m_CurrentPosition;
    public Unity.Mathematics.float3 m_CurrentDirection;
    public Unity.Mathematics.float3 m_CurrentVelocity;
    public System.Single m_TargetDistance;
    public Game.Pathfind.PathOwner m_PathOwner;
    public Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> m_PathElements;
    public System.Single m_MinSpeed;
    public Unity.Mathematics.float3 m_TargetPosition;
    public System.Single m_MaxSpeed;
    public System.Single m_LanePosition;
    public Unity.Entities.Entity m_Blocker;
    public Game.Vehicles.BlockerType m_BlockerType;
    public Unity.Entities.Entity m_QueueEntity;
    public Colossal.Mathematics.Sphere3 m_QueueArea;
    public Unity.Entities.DynamicBuffer<Game.Creatures.Queue> m_Queues;
    private Colossal.Mathematics.Line3+Segment m_TargetLine;
    private System.Single m_PushFactor;
    private Colossal.Mathematics.Bounds3 m_Bounds;
    private System.Single m_Size;

    private System.Void CalculateTargetLine(Unity.Entities.Entity targetLane, Unity.Mathematics.float3 targetPosition, System.Boolean isBackward);
    private System.Void CalculateTargetLine(Unity.Entities.Entity targetLane, System.Single targetOffset);
    private System.Void CheckCollision(Unity.Entities.Entity other);
    private System.Boolean CheckQueue(Unity.Entities.Entity other, Unity.Entities.Entity& queueEntity, Colossal.Mathematics.Sphere3& queueArea);
    private Unity.Mathematics.float3 GetTargetPosition(System.Int32 elementIndex, Unity.Entities.Entity targetElement, System.Single curvePos);
    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity item);
    public System.Void IterateBlocker(Game.Prefabs.HumanData prefabHumanData, Unity.Entities.Entity other);
    public System.Void IterateBlocker(Game.Prefabs.AnimalData prefabAnimalData, Unity.Entities.Entity other);
    public System.Boolean IterateFirstLane(Unity.Entities.Entity currentLane, Unity.Mathematics.float2 currentOffset, System.Boolean isBackward);
    public System.Boolean IterateFirstLane(Unity.Entities.Entity currentLane, Unity.Entities.Entity targetLane, Unity.Mathematics.float2 currentOffset, Unity.Mathematics.float2 targetOffset, System.Boolean isBackward);
    public System.Boolean IterateNextLane(Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextOffset);
    private System.Boolean ShouldQueue(Unity.Entities.Entity entity, Colossal.Mathematics.Sphere3 area, Colossal.Mathematics.Sphere3& queueArea);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
```

- `public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
```

- `public Unity.Entities.ComponentLookup<Game.Creatures.GroupMember> m_GroupMemberData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Creatures.GroupMember> m_GroupMemberData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.Waypoint> m_WaypointData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.Waypoint> m_WaypointData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> m_TaxiStandData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> m_TaxiStandData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.AreaLane> m_AreaLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.AreaLane> m_AreaLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
```

- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticObjectSearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticObjectSearchTree;
```

- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingObjectSearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingObjectSearchTree;
```

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Unity.Entities.Entity m_Leader`  

```csharp
public Unity.Entities.Entity m_Leader;
```

- `public Unity.Entities.Entity m_CurrentLane`  

```csharp
public Unity.Entities.Entity m_CurrentLane;
```

- `public Unity.Entities.Entity m_CurrentVehicle`  

```csharp
public Unity.Entities.Entity m_CurrentVehicle;
```

- `public System.Single m_CurvePosition`  

```csharp
public System.Single m_CurvePosition;
```

- `public System.Single m_TimeStep`  

```csharp
public System.Single m_TimeStep;
```

- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  

```csharp
public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
```

- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_SpeedRange;
```

- `public Unity.Mathematics.float3 m_CurrentPosition`  

```csharp
public Unity.Mathematics.float3 m_CurrentPosition;
```

- `public Unity.Mathematics.float3 m_CurrentDirection`  

```csharp
public Unity.Mathematics.float3 m_CurrentDirection;
```

- `public Unity.Mathematics.float3 m_CurrentVelocity`  

```csharp
public Unity.Mathematics.float3 m_CurrentVelocity;
```

- `public System.Single m_TargetDistance`  

```csharp
public System.Single m_TargetDistance;
```

- `public Game.Pathfind.PathOwner m_PathOwner`  

```csharp
public Game.Pathfind.PathOwner m_PathOwner;
```

- `public Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> m_PathElements`  

```csharp
public Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> m_PathElements;
```

- `public System.Single m_MinSpeed`  

```csharp
public System.Single m_MinSpeed;
```

- `public Unity.Mathematics.float3 m_TargetPosition`  

```csharp
public Unity.Mathematics.float3 m_TargetPosition;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public System.Single m_LanePosition`  

```csharp
public System.Single m_LanePosition;
```

- `public Unity.Entities.Entity m_Blocker`  

```csharp
public Unity.Entities.Entity m_Blocker;
```

- `public Game.Vehicles.BlockerType m_BlockerType`  

```csharp
public Game.Vehicles.BlockerType m_BlockerType;
```

- `public Unity.Entities.Entity m_QueueEntity`  

```csharp
public Unity.Entities.Entity m_QueueEntity;
```

- `public Colossal.Mathematics.Sphere3 m_QueueArea`  

```csharp
public Colossal.Mathematics.Sphere3 m_QueueArea;
```

- `public Unity.Entities.DynamicBuffer<Game.Creatures.Queue> m_Queues`  

```csharp
public Unity.Entities.DynamicBuffer<Game.Creatures.Queue> m_Queues;
```

- `private Colossal.Mathematics.Line3+Segment m_TargetLine`  

```csharp
private Colossal.Mathematics.Line3+Segment m_TargetLine;
```

- `private System.Single m_PushFactor`  

```csharp
private System.Single m_PushFactor;
```

- `private Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
private Colossal.Mathematics.Bounds3 m_Bounds;
```

- `private System.Single m_Size`  

```csharp
private System.Single m_Size;
```


## Methods

- `private CalculateTargetLine(Unity.Entities.Entity targetLane, Unity.Mathematics.float3 targetPosition, System.Boolean isBackward) : System.Void`  

```csharp
private void CalculateTargetLine(Entity targetLane, float targetOffset)
	{
		Curve curve = m_CurveData[targetLane];
		PrefabRef prefabRef = m_PrefabRefData[targetLane];
		float num = math.max(0f, m_PrefabLaneData[prefabRef.m_Prefab].m_Width * 0.5f - m_Size);
		float3 @float = MathUtils.Position(curve.m_Bezier, targetOffset);
		float2 float2 = MathUtils.Right(math.normalizesafe(MathUtils.Tangent(curve.m_Bezier, targetOffset).xz)) * num;
		m_TargetLine = new Line3.Segment(@float, @float);
		m_TargetLine.a.xz -= float2;
		m_TargetLine.b.xz += float2;
		float t;
		float num2 = MathUtils.Distance(m_TargetLine, m_CurrentPosition, out t);
		if (num2 > m_TargetDistance)
		{
			m_TargetLine += (m_CurrentPosition - MathUtils.Position(m_TargetLine, t)) * (1f - m_TargetDistance / num2);
		}
		m_Bounds = MathUtils.Expand(MathUtils.Bounds(m_TargetLine) | m_CurrentPosition, m_Size);
	}
```

- `private CalculateTargetLine(Unity.Entities.Entity targetLane, System.Single targetOffset) : System.Void`  

```csharp
private void CalculateTargetLine(Entity targetLane, float targetOffset)
	{
		Curve curve = m_CurveData[targetLane];
		PrefabRef prefabRef = m_PrefabRefData[targetLane];
		float num = math.max(0f, m_PrefabLaneData[prefabRef.m_Prefab].m_Width * 0.5f - m_Size);
		float3 @float = MathUtils.Position(curve.m_Bezier, targetOffset);
		float2 float2 = MathUtils.Right(math.normalizesafe(MathUtils.Tangent(curve.m_Bezier, targetOffset).xz)) * num;
		m_TargetLine = new Line3.Segment(@float, @float);
		m_TargetLine.a.xz -= float2;
		m_TargetLine.b.xz += float2;
		float t;
		float num2 = MathUtils.Distance(m_TargetLine, m_CurrentPosition, out t);
		if (num2 > m_TargetDistance)
		{
			m_TargetLine += (m_CurrentPosition - MathUtils.Position(m_TargetLine, t)) * (1f - m_TargetDistance / num2);
		}
		m_Bounds = MathUtils.Expand(MathUtils.Bounds(m_TargetLine) | m_CurrentPosition, m_Size);
	}
```

- `private CheckCollision(Unity.Entities.Entity other) : System.Void`  

```csharp
private void CheckCollision(Entity other)
	{
		if (!m_TransformData.TryGetComponent(other, out var componentData))
		{
			return;
		}
		PrefabRef prefabRef = m_PrefabRefData[other];
		ObjectGeometryData objectGeometryData = m_PrefabObjectGeometryData[prefabRef.m_Prefab];
		if ((objectGeometryData.m_Flags & Game.Objects.GeometryFlags.WalkThrough) != Game.Objects.GeometryFlags.None)
		{
			return;
		}
		if (m_MovingData.TryGetComponent(other, out var componentData2))
		{
			float num = (objectGeometryData.m_Bounds.max.x - objectGeometryData.m_Bounds.min.x) * 0.5f;
			float num2 = m_Size + num + 0.5f;
			Line3.Segment segment = new Line3.Segment(m_CurrentPosition, m_TargetPosition);
			Line3.Segment segment2 = new Line3.Segment(componentData.m_Position, componentData.m_Position + componentData2.m_Velocity);
			if (math.dot(segment2.a + componentData2.m_Velocity * (m_TimeStep * 2f) - segment.a - m_CurrentVelocity * m_TimeStep, m_TargetPosition - m_CurrentPosition) < 0f)
			{
				return;
			}
			float2 t;
			float num3 = MathUtils.Distance(segment, segment2, out t);
			if (!(num3 < num2))
			{
				return;
			}
			float3 @float = MathUtils.Position(segment, t.x * 0.99f);
			float3 float2 = MathUtils.Position(segment2, t.y);
			Bounds1 bounds = @float.y + m_PrefabObjectGeometry.m_Bounds.y;
			Bounds1 bounds2 = float2.y + objectGeometryData.m_Bounds.y;
			if (!MathUtils.Intersect(bounds, bounds2))
			{
				return;
			}
			float3 float3 = math.normalizesafe(m_TargetPosition - m_CurrentPosition);
			float3 x = @float - float2;
			x -= float3 * math.dot(x, float3);
			x = math.normalizesafe(x);
			float3 position = m_TargetPosition + x * ((num2 - num3) * m_PushFactor);
			m_PushFactor /= 2f;
			if (m_TargetLine.a.Equals(m_TargetLine.b))
			{
				m_TargetPosition = m_TargetLine.a;
			}
			else
			{
				MathUtils.Distance(m_TargetLine, position, out m_LanePosition);
				m_TargetPosition = MathUtils.Position(m_TargetLine, m_LanePosition);
				m_LanePosition -= 0.5f;
			}
			float num4 = math.min(1f, 0.7f + 0.3f * math.dot(float3, math.normalizesafe(componentData2.m_Velocity)) + num3 / num2);
			num4 *= m_SpeedRange.max;
			x = componentData.m_Position - m_CurrentPosition;
			float num5 = math.length(x);
			float num6 = math.dot(x, float3);
			Entity queueEntity = Entity.Null;
			Sphere3 queueArea = default(Sphere3);
			BlockerType blockerType = BlockerType.Crossing;
			if (num5 < num2 && num6 > 0f)
			{
				blockerType = BlockerType.Continuing;
				if (CheckQueue(other, out queueEntity, out queueArea))
				{
					if (num5 > 0.01f)
					{
						float num7 = num6 * (num2 - num5) / (num2 * num5);
						num4 = math.min(num4, math.max(0f, math.max(1f, math.lerp(math.dot(float3, componentData2.m_Velocity), m_SpeedRange.max, num3 / num2)) - num7));
					}
					else
					{
						num4 = 0f;
					}
				}
				else if (num5 > 0.01f && ((objectGeometryData.m_Flags & ~m_PrefabObjectGeometry.m_Flags & Game.Objects.GeometryFlags.LowCollisionPriority) == 0 || math.dot(componentData2.m_Velocity, x) < 0f))
				{
					float num8 = num6 * (num2 - num5) / (num2 * num5);
					num4 = math.min(num4, math.max(m_MinSpeed, math.max(1f, math.lerp(math.dot(float3, componentData2.m_Velocity), m_SpeedRange.max, num3 / num2)) - num8));
				}
			}
			num4 = MathUtils.Clamp(num4, m_SpeedRange);
			if (num4 < m_MaxSpeed)
			{
				m_MaxSpeed = num4;
				m_Blocker = other;
				m_BlockerType = blockerType;
				CreatureUtils.SetQueue(ref m_QueueEntity, ref m_QueueArea, queueEntity, queueArea);
			}
			return;
		}
		float num9 = (((objectGeometryData.m_Flags & Game.Objects.GeometryFlags.Standing) == 0) ? (math.cmax(objectGeometryData.m_Bounds.max.xz - objectGeometryData.m_Bounds.min.xz) * 0.5f) : math.cmax(objectGeometryData.m_LegSize.xz + objectGeometryData.m_LegOffset * 2f));
		float num10 = m_Size + num9 + 0.25f;
		Line3.Segment line = new Line3.Segment(m_CurrentPosition, m_TargetPosition);
		float t2;
		float num11 = MathUtils.Distance(line, componentData.m_Position, out t2);
		if (!(num11 < num10))
		{
			return;
		}
		float3 float4 = MathUtils.Position(line, t2 * 0.99f);
		Bounds1 bounds3 = float4.y + m_PrefabObjectGeometry.m_Bounds.y;
		Bounds1 bounds4 = componentData.m_Position.y + objectGeometryData.m_Bounds.y;
		if (MathUtils.Intersect(bounds3, bounds4))
		{
			float3 float5 = math.normalizesafe(m_TargetPosition - m_CurrentPosition);
			float3 x2 = float4 - componentData.m_Position;
			x2 -= float5 * math.dot(x2, float5);
			x2 = math.normalizesafe(x2);
			float3 position2 = m_TargetPosition + x2 * ((num10 - num11) * m_PushFactor);
			m_PushFactor /= 2f;
			if (m_TargetLine.a.Equals(m_TargetLine.b))
			{
				m_TargetPosition = m_TargetLine.a;
			}
			else
			{
				MathUtils.Distance(m_TargetLine, position2, out m_LanePosition);
				m_TargetPosition = MathUtils.Position(m_TargetLine, m_LanePosition);
				m_LanePosition -= 0.5f;
			}
			float num12 = math.min(1f, 0.7f + num11 / num10);
			num12 *= m_SpeedRange.max;
			x2 = componentData.m_Position - m_CurrentPosition;
			float num13 = math.length(x2);
			float num14 = math.dot(x2, float5);
			if (num13 < num10 && num14 > 0f && num13 > 0.01f)
			{
				float num15 = num14 * (num10 - num13) / (num10 * num13);
				num12 = math.min(num12, math.max(0.5f, math.max(1f, m_SpeedRange.max * num11 / num10) - num15));
			}
			num12 = MathUtils.Clamp(num12, m_SpeedRange);
			if (num12 < m_MaxSpeed)
			{
				m_MaxSpeed = num12;
				m_Blocker = other;
				m_BlockerType = BlockerType.Limit;
				m_QueueEntity = Entity.Null;
				m_QueueArea = default(Sphere3);
			}
		}
	}
```

- `private CheckQueue(Unity.Entities.Entity other, Unity.Entities.Entity& queueEntity, Colossal.Mathematics.Sphere3& queueArea) : System.Boolean`  

```csharp
private bool CheckQueue(Entity other, out Entity queueEntity, out Sphere3 queueArea)
	{
		queueEntity = Entity.Null;
		queueArea = default(Sphere3);
		if (m_CreatureData.TryGetComponent(other, out var componentData) && componentData.m_QueueArea.radius > 0f)
		{
			Transform transform = m_TransformData[other];
			float3 y = math.forward(transform.m_Rotation);
			if (math.dot(transform.m_Position - m_CurrentPosition, m_CurrentDirection) < math.dot(m_CurrentPosition - transform.m_Position, y))
			{
				return false;
			}
			if (m_Leader != Entity.Null)
			{
				if (m_GroupMemberData.TryGetComponent(other, out var componentData2))
				{
					other = componentData2.m_Leader;
				}
				if (other == m_Leader)
				{
					queueEntity = componentData.m_QueueEntity;
					queueArea = componentData.m_QueueArea;
					return true;
				}
			}
			else
			{
				if (m_GroupMemberData.TryGetComponent(other, out var componentData3))
				{
					other = componentData3.m_Leader;
				}
				if (other != m_Entity && ShouldQueue(componentData.m_QueueEntity, componentData.m_QueueArea, out queueArea))
				{
					queueEntity = componentData.m_QueueEntity;
					return true;
				}
			}
		}
		return false;
	}
```

- `private GetTargetPosition(System.Int32 elementIndex, Unity.Entities.Entity targetElement, System.Single curvePos) : Unity.Mathematics.float3`  

```csharp
private float3 GetTargetPosition(int elementIndex, Entity targetElement, float curvePos)
	{
		while (m_WaypointData.HasComponent(targetElement) || m_TaxiStandData.HasComponent(targetElement))
		{
			if (--elementIndex >= m_PathOwner.m_ElementIndex)
			{
				PathElement pathElement = m_PathElements[elementIndex];
				targetElement = pathElement.m_Target;
				curvePos = pathElement.m_TargetDelta.y;
				continue;
			}
			targetElement = m_CurrentLane;
			curvePos = m_CurvePosition;
			break;
		}
		if (m_CurveData.TryGetComponent(targetElement, out var componentData))
		{
			PrefabRef prefabRef = m_PrefabRefData[targetElement];
			NetLaneData prefabLaneData = m_PrefabLaneData[prefabRef.m_Prefab];
			float laneOffset = CreatureUtils.GetLaneOffset(m_PrefabObjectGeometry, prefabLaneData, m_LanePosition);
			return CreatureUtils.GetLanePosition(componentData.m_Bezier, curvePos, laneOffset);
		}
		if (m_TransformData.TryGetComponent(targetElement, out var componentData2))
		{
			return componentData2.m_Position;
		}
		return m_TargetPosition;
	}
```

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  

```csharp
public bool Intersect(QuadTreeBoundsXZ bounds)
	{
		if ((bounds.m_Mask & (BoundsMask.NotOverridden | BoundsMask.NotWalkThrough)) != (BoundsMask.NotOverridden | BoundsMask.NotWalkThrough))
		{
			return false;
		}
		return MathUtils.Intersect(m_Bounds, bounds.m_Bounds);
	}
```

- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity item) : System.Void`  

```csharp
public void Iterate(QuadTreeBoundsXZ bounds, Entity item)
	{
		if ((bounds.m_Mask & (BoundsMask.NotOverridden | BoundsMask.NotWalkThrough)) == (BoundsMask.NotOverridden | BoundsMask.NotWalkThrough) && MathUtils.Intersect(m_Bounds, bounds.m_Bounds))
		{
			CheckCollision(item);
		}
	}
```

- `public IterateBlocker(Game.Prefabs.HumanData prefabHumanData, Unity.Entities.Entity other) : System.Void`  

```csharp
public void IterateBlocker(AnimalData prefabAnimalData, Entity other)
	{
		if (CheckQueue(other, out var queueEntity, out var queueArea) && m_MovingData.TryGetComponent(other, out var componentData))
		{
			Transform transform = m_TransformData[other];
			PrefabRef prefabRef = m_PrefabRefData[other];
			ObjectGeometryData objectGeometryData = m_PrefabObjectGeometryData[prefabRef.m_Prefab];
			float num = (m_PrefabObjectGeometry.m_Bounds.max.x - m_PrefabObjectGeometry.m_Bounds.min.x) * 0.5f;
			float num2 = (objectGeometryData.m_Bounds.max.x - objectGeometryData.m_Bounds.min.x) * 0.5f;
			float num3 = num + num2 + 0.5f;
			float3 x = transform.m_Position - m_CurrentPosition;
			float3 @float = math.normalizesafe(m_TargetPosition - m_CurrentPosition);
			float distance = math.max(0f, math.length(x) * 2f - num3 - math.dot(x, @float));
			float maxResultSpeed = math.max(0f, math.dot(@float, componentData.m_Velocity));
			float maxBrakingSpeed = CreatureUtils.GetMaxBrakingSpeed(prefabAnimalData, distance, maxResultSpeed, m_TimeStep);
			maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
			if (maxBrakingSpeed <= m_MaxSpeed)
			{
				m_MaxSpeed = maxBrakingSpeed;
				m_Blocker = other;
				m_BlockerType = BlockerType.Continuing;
				CreatureUtils.SetQueue(ref m_QueueEntity, ref m_QueueArea, queueEntity, queueArea);
			}
		}
	}
```

- `public IterateBlocker(Game.Prefabs.AnimalData prefabAnimalData, Unity.Entities.Entity other) : System.Void`  

```csharp
public void IterateBlocker(AnimalData prefabAnimalData, Entity other)
	{
		if (CheckQueue(other, out var queueEntity, out var queueArea) && m_MovingData.TryGetComponent(other, out var componentData))
		{
			Transform transform = m_TransformData[other];
			PrefabRef prefabRef = m_PrefabRefData[other];
			ObjectGeometryData objectGeometryData = m_PrefabObjectGeometryData[prefabRef.m_Prefab];
			float num = (m_PrefabObjectGeometry.m_Bounds.max.x - m_PrefabObjectGeometry.m_Bounds.min.x) * 0.5f;
			float num2 = (objectGeometryData.m_Bounds.max.x - objectGeometryData.m_Bounds.min.x) * 0.5f;
			float num3 = num + num2 + 0.5f;
			float3 x = transform.m_Position - m_CurrentPosition;
			float3 @float = math.normalizesafe(m_TargetPosition - m_CurrentPosition);
			float distance = math.max(0f, math.length(x) * 2f - num3 - math.dot(x, @float));
			float maxResultSpeed = math.max(0f, math.dot(@float, componentData.m_Velocity));
			float maxBrakingSpeed = CreatureUtils.GetMaxBrakingSpeed(prefabAnimalData, distance, maxResultSpeed, m_TimeStep);
			maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
			if (maxBrakingSpeed <= m_MaxSpeed)
			{
				m_MaxSpeed = maxBrakingSpeed;
				m_Blocker = other;
				m_BlockerType = BlockerType.Continuing;
				CreatureUtils.SetQueue(ref m_QueueEntity, ref m_QueueArea, queueEntity, queueArea);
			}
		}
	}
```

- `public IterateFirstLane(Unity.Entities.Entity currentLane, Unity.Mathematics.float2 currentOffset, System.Boolean isBackward) : System.Boolean`  

```csharp
public bool IterateFirstLane(Entity currentLane, Entity targetLane, float2 currentOffset, float2 targetOffset, bool isBackward)
	{
		m_Size = (m_PrefabObjectGeometry.m_Bounds.max.x - m_PrefabObjectGeometry.m_Bounds.min.x) * 0.5f;
		m_PushFactor = 0.75f;
		if (m_AreaLaneData.HasComponent(targetLane))
		{
			CalculateTargetLine(targetLane, m_TargetPosition, isBackward);
			m_MovingObjectSearchTree.Iterate(ref this);
			m_StaticObjectSearchTree.Iterate(ref this);
			return false;
		}
		if (m_CurveData.TryGetComponent(targetLane, out var componentData))
		{
			CalculateTargetLine(targetLane, targetOffset.x);
			bool result = false;
			if (m_LaneObjects.TryGetBuffer(currentLane, out var bufferData))
			{
				float num = m_TargetDistance / math.max(1f, componentData.m_Length);
				Bounds1 bounds = new Bounds1(currentOffset.x - num, currentOffset.x + num);
				result = MathUtils.Intersect(bounds, currentOffset.y);
				for (int i = 0; i < bufferData.Length; i++)
				{
					LaneObject laneObject = bufferData[i];
					Bounds1 bounds2 = MathUtils.Bounds(laneObject.m_CurvePosition.x, laneObject.m_CurvePosition.y);
					if (MathUtils.Intersect(bounds, bounds2) && laneObject.m_LaneObject != m_Entity)
					{
						CheckCollision(laneObject.m_LaneObject);
					}
				}
			}
			m_StaticObjectSearchTree.Iterate(ref this);
			return result;
		}
		return false;
	}
```

- `public IterateFirstLane(Unity.Entities.Entity currentLane, Unity.Entities.Entity targetLane, Unity.Mathematics.float2 currentOffset, Unity.Mathematics.float2 targetOffset, System.Boolean isBackward) : System.Boolean`  

```csharp
public bool IterateFirstLane(Entity currentLane, Entity targetLane, float2 currentOffset, float2 targetOffset, bool isBackward)
	{
		m_Size = (m_PrefabObjectGeometry.m_Bounds.max.x - m_PrefabObjectGeometry.m_Bounds.min.x) * 0.5f;
		m_PushFactor = 0.75f;
		if (m_AreaLaneData.HasComponent(targetLane))
		{
			CalculateTargetLine(targetLane, m_TargetPosition, isBackward);
			m_MovingObjectSearchTree.Iterate(ref this);
			m_StaticObjectSearchTree.Iterate(ref this);
			return false;
		}
		if (m_CurveData.TryGetComponent(targetLane, out var componentData))
		{
			CalculateTargetLine(targetLane, targetOffset.x);
			bool result = false;
			if (m_LaneObjects.TryGetBuffer(currentLane, out var bufferData))
			{
				float num = m_TargetDistance / math.max(1f, componentData.m_Length);
				Bounds1 bounds = new Bounds1(currentOffset.x - num, currentOffset.x + num);
				result = MathUtils.Intersect(bounds, currentOffset.y);
				for (int i = 0; i < bufferData.Length; i++)
				{
					LaneObject laneObject = bufferData[i];
					Bounds1 bounds2 = MathUtils.Bounds(laneObject.m_CurvePosition.x, laneObject.m_CurvePosition.y);
					if (MathUtils.Intersect(bounds, bounds2) && laneObject.m_LaneObject != m_Entity)
					{
						CheckCollision(laneObject.m_LaneObject);
					}
				}
			}
			m_StaticObjectSearchTree.Iterate(ref this);
			return result;
		}
		return false;
	}
```

- `public IterateNextLane(Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextOffset) : System.Boolean`  

```csharp
public bool IterateNextLane(Entity nextLane, float2 nextOffset)
	{
		bool result = false;
		if (m_LaneObjects.TryGetBuffer(nextLane, out var bufferData))
		{
			float num = 5f / math.max(1f, m_CurveData[nextLane].m_Length);
			Bounds1 bounds = new Bounds1(nextOffset.x - num, nextOffset.x + num);
			result = MathUtils.Intersect(bounds, nextOffset.y);
			for (int i = 0; i < bufferData.Length; i++)
			{
				LaneObject laneObject = bufferData[i];
				Bounds1 bounds2 = MathUtils.Bounds(laneObject.m_CurvePosition.x, laneObject.m_CurvePosition.y);
				if (MathUtils.Intersect(bounds, bounds2) && laneObject.m_LaneObject != m_Entity)
				{
					CheckCollision(laneObject.m_LaneObject);
				}
			}
		}
		else if (m_AreaLaneData.HasComponent(nextLane))
		{
			m_MovingObjectSearchTree.Iterate(ref this);
		}
		return result;
	}
```

- `private ShouldQueue(Unity.Entities.Entity entity, Colossal.Mathematics.Sphere3 area, Colossal.Mathematics.Sphere3& queueArea) : System.Boolean`  

```csharp
private bool ShouldQueue(Entity entity, Sphere3 area, out Sphere3 queueArea)
	{
		if (!m_Queues.IsCreated || (m_PathOwner.m_State & (PathFlags.Pending | PathFlags.Failed | PathFlags.Obsolete | PathFlags.Updated)) != 0)
		{
			queueArea = default(Sphere3);
			return false;
		}
		Entity entity2 = Entity.Null;
		if (m_PathElements.Length > m_PathOwner.m_ElementIndex)
		{
			PathElement pathElement = m_PathElements[m_PathOwner.m_ElementIndex];
			if (m_WaypointData.HasComponent(pathElement.m_Target) || m_TaxiStandData.HasComponent(pathElement.m_Target))
			{
				entity2 = pathElement.m_Target;
			}
		}
		for (int i = 0; i < m_Queues.Length; i++)
		{
			Queue value = m_Queues[i];
			if (value.m_TargetEntity == entity)
			{
				if ((value.m_TargetEntity == entity2 || value.m_TargetEntity == m_CurrentLane) && m_CurveData.TryGetComponent(m_CurrentLane, out var componentData))
				{
					PrefabRef prefabRef = m_PrefabRefData[m_CurrentLane];
					NetLaneData prefabLaneData = m_PrefabLaneData[prefabRef.m_Prefab];
					float laneOffset = CreatureUtils.GetLaneOffset(m_PrefabObjectGeometry, prefabLaneData, m_LanePosition);
					value.m_TargetArea.position = CreatureUtils.GetLanePosition(componentData.m_Bezier, m_CurvePosition, laneOffset);
				}
				value.m_ObsoleteTime = 0;
				m_Queues[i] = value;
				if (value.m_TargetArea.radius > 0f && MathUtils.Intersect(value.m_TargetArea, area))
				{
					Sphere3 queueArea2 = CreatureUtils.GetQueueArea(m_PrefabObjectGeometry, m_CurrentPosition, m_TargetPosition);
					queueArea = MathUtils.Sphere(area, MathUtils.Sphere(queueArea2, value.m_TargetArea));
					return true;
				}
				queueArea = default(Sphere3);
				return false;
			}
		}
		if (m_CurrentLane == entity)
		{
			Queue elem = default(Queue);
			elem.m_TargetEntity = entity;
			elem.m_TargetArea = CreatureUtils.GetQueueArea(m_PrefabObjectGeometry, GetTargetPosition(m_PathOwner.m_ElementIndex - 1, m_CurrentLane, m_CurvePosition));
			elem.m_ObsoleteTime = 0;
			m_Queues.Add(elem);
			if (MathUtils.Intersect(elem.m_TargetArea, area))
			{
				Sphere3 queueArea3 = CreatureUtils.GetQueueArea(m_PrefabObjectGeometry, m_CurrentPosition, m_TargetPosition);
				queueArea = MathUtils.Sphere(area, MathUtils.Sphere(queueArea3, elem.m_TargetArea));
				return true;
			}
			queueArea = default(Sphere3);
			return false;
		}
		if (m_CurrentVehicle == Entity.Null)
		{
			Queue elem2 = default(Queue);
			for (int j = m_PathOwner.m_ElementIndex; j < m_PathElements.Length; j++)
			{
				PathElement pathElement2 = m_PathElements[j];
				if (pathElement2.m_Target == entity)
				{
					elem2.m_TargetEntity = entity;
					elem2.m_TargetArea = CreatureUtils.GetQueueArea(m_PrefabObjectGeometry, GetTargetPosition(j, pathElement2.m_Target, pathElement2.m_TargetDelta.y));
					elem2.m_ObsoleteTime = 0;
					m_Queues.Add(elem2);
					if (MathUtils.Intersect(elem2.m_TargetArea, area))
					{
						Sphere3 queueArea4 = CreatureUtils.GetQueueArea(m_PrefabObjectGeometry, m_CurrentPosition, m_TargetPosition);
						queueArea = MathUtils.Sphere(area, MathUtils.Sphere(queueArea4, elem2.m_TargetArea));
						return true;
					}
					queueArea = default(Sphere3);
					return false;
				}
			}
		}
		m_Queues.Add(new Queue
		{
			m_TargetEntity = entity
		});
		queueArea = default(Sphere3);
		return false;
	}
```


