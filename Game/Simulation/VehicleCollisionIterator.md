# Game.Simulation.VehicleCollisionIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct VehicleCollisionIterator : Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>
{
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
    public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.AreaLane> m_AreaLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData;
    public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticObjectSearchTree;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingObjectSearchTree;
    public Game.Simulation.TerrainHeightData m_TerrainHeightData;
    public Unity.Entities.Entity m_Entity;
    public Unity.Entities.Entity m_CurrentLane;
    public System.Single m_CurvePosition;
    public System.Single m_TimeStep;
    public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
    public Colossal.Mathematics.Bounds1 m_SpeedRange;
    public Unity.Mathematics.float3 m_CurrentPosition;
    public Unity.Mathematics.float3 m_CurrentVelocity;
    public System.Single m_MinDistance;
    public Unity.Mathematics.float3 m_TargetPosition;
    public System.Single m_MaxSpeed;
    public System.Single m_LanePosition;
    public Unity.Entities.Entity m_Blocker;
    public Game.Vehicles.BlockerType m_BlockerType;
    private Colossal.Mathematics.Line3+Segment m_TargetLine;
    private Colossal.Mathematics.Bounds1 m_TargetLimits;
    private System.Single m_PushFactor;
    private Colossal.Mathematics.Bounds3 m_Bounds;
    private System.Single m_Size;

    private System.Void CalculateTargetLine(Unity.Entities.Entity targetLane, Unity.Mathematics.float3 targetPosition);
    private System.Void CheckCollision(Unity.Entities.Entity other);
    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity item);
    public System.Boolean IterateFirstLane(Unity.Entities.Entity currentLane);
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

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
```

- `public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
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

- `public Game.Simulation.TerrainHeightData m_TerrainHeightData`  

```csharp
public Game.Simulation.TerrainHeightData m_TerrainHeightData;
```

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Unity.Entities.Entity m_CurrentLane`  

```csharp
public Unity.Entities.Entity m_CurrentLane;
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

- `public Unity.Mathematics.float3 m_CurrentVelocity`  

```csharp
public Unity.Mathematics.float3 m_CurrentVelocity;
```

- `public System.Single m_MinDistance`  

```csharp
public System.Single m_MinDistance;
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

- `private Colossal.Mathematics.Line3+Segment m_TargetLine`  

```csharp
private Colossal.Mathematics.Line3+Segment m_TargetLine;
```

- `private Colossal.Mathematics.Bounds1 m_TargetLimits`  

```csharp
private Colossal.Mathematics.Bounds1 m_TargetLimits;
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

- `private CalculateTargetLine(Unity.Entities.Entity targetLane, Unity.Mathematics.float3 targetPosition) : System.Void`  

```csharp
private void CalculateTargetLine(Entity targetLane, float3 targetPosition)
	{
		Owner owner = m_OwnerData[targetLane];
		AreaLane areaLane = m_AreaLaneData[targetLane];
		DynamicBuffer<Game.Areas.Node> dynamicBuffer = m_AreaNodes[owner.m_Owner];
		float3 @float = targetPosition - m_CurrentPosition;
		float num = math.length(@float.xz);
		if (num < m_MinDistance)
		{
			m_TargetLine = new Line3.Segment(targetPosition, targetPosition);
			m_TargetLimits = new Bounds1(0f, 1f);
		}
		else
		{
			if (num > m_MinDistance)
			{
				targetPosition = m_CurrentPosition + @float * (m_MinDistance / num);
			}
			float2 float2 = MathUtils.Right(@float.xz) * (0.5f / math.max(0.1f, num));
			Line3 line = new Line3.Segment(targetPosition, targetPosition);
			line.a.xz -= float2;
			line.b.xz += float2;
			Bounds1 bounds = default(Bounds1);
			float2 t;
			if (areaLane.m_Nodes.y == areaLane.m_Nodes.z)
			{
				float3 position = dynamicBuffer[areaLane.m_Nodes.x].m_Position;
				float3 position2 = dynamicBuffer[areaLane.m_Nodes.y].m_Position;
				float3 position3 = dynamicBuffer[areaLane.m_Nodes.w].m_Position;
				if (MathUtils.Intersect(new Line2.Segment(position.xz, position2.xz), line.xz, out t))
				{
					bounds |= t.y;
				}
				if (MathUtils.Intersect(new Line2.Segment(position2.xz, position3.xz), line.xz, out t))
				{
					bounds |= t.y;
				}
				if (MathUtils.Intersect(new Line2.Segment(position3.xz, position.xz), line.xz, out t))
				{
					bounds |= t.y;
				}
			}
			else
			{
				float3 position4 = dynamicBuffer[areaLane.m_Nodes.x].m_Position;
				float3 position5 = dynamicBuffer[areaLane.m_Nodes.y].m_Position;
				float3 position6 = dynamicBuffer[areaLane.m_Nodes.w].m_Position;
				float3 position7 = dynamicBuffer[areaLane.m_Nodes.z].m_Position;
				if (MathUtils.Intersect(new Line2.Segment(position4.xz, position5.xz), line.xz, out t))
				{
					bounds |= t.y;
				}
				if (MathUtils.Intersect(new Line2.Segment(position5.xz, position6.xz), line.xz, out t))
				{
					bounds |= t.y;
				}
				if (MathUtils.Intersect(new Line2.Segment(position6.xz, position7.xz), line.xz, out t))
				{
					bounds |= t.y;
				}
				if (MathUtils.Intersect(new Line2.Segment(position7.xz, position4.xz), line.xz, out t))
				{
					bounds |= t.y;
				}
			}
			m_TargetLimits.min = math.min(bounds.min + m_Size, 0f);
			m_TargetLimits.max = math.max(bounds.max - m_Size, 0f);
			bounds.min = math.max(m_TargetLimits.min, m_MinDistance * -0.9f);
			bounds.max = math.min(m_TargetLimits.max, m_MinDistance * 0.9f);
			m_TargetLine.a = MathUtils.Position(line, bounds.min);
			m_TargetLine.b = MathUtils.Position(line, bounds.max);
			float num2 = 1f / math.max(1f, m_TargetLimits.max - m_TargetLimits.min);
			m_TargetLimits.min = (bounds.min - m_TargetLimits.min) * num2;
			m_TargetLimits.max = (bounds.max - m_TargetLimits.min) * num2;
		}
		m_Bounds = MathUtils.Expand(MathUtils.Bounds(m_TargetLine) | m_CurrentPosition, m_Size);
	}
```

- `private CheckCollision(Unity.Entities.Entity other) : System.Void`  

```csharp
private void CheckCollision(Entity other)
	{
		if (other == m_Entity || !m_TransformData.TryGetComponent(other, out var componentData))
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
			if (m_CreatureData.HasComponent(other) || (m_ControllerData.TryGetComponent(other, out var componentData3) && componentData3.m_Controller == m_Entity))
			{
				return;
			}
			float num = (objectGeometryData.m_Bounds.max.x - objectGeometryData.m_Bounds.min.x) * 0.5f;
			float num2 = m_Size + num + 0.5f;
			Line2.Segment segment = new Line2.Segment(m_CurrentPosition.xz, m_TargetPosition.xz);
			Line2.Segment segment2 = new Line2.Segment(componentData.m_Position.xz, componentData.m_Position.xz + componentData2.m_Velocity.xz);
			if (math.dot(segment2.a + componentData2.m_Velocity.xz * (m_TimeStep * 2f) - segment.a - m_CurrentVelocity.xz * m_TimeStep, m_TargetPosition.xz - m_CurrentPosition.xz) < 0f)
			{
				return;
			}
			float2 t;
			float num3 = MathUtils.Distance(segment, segment2, out t);
			if (!(num3 < num2))
			{
				return;
			}
			float2 @float = MathUtils.Position(segment, t.x * 0.99f);
			float2 float2 = MathUtils.Position(segment2, t.y);
			float2 float3 = math.normalizesafe(m_TargetPosition.xz - m_CurrentPosition.xz);
			float2 x = @float - float2;
			x -= float3 * math.dot(x, float3);
			x = math.normalizesafe(x);
			float2 position = m_TargetPosition.xz + x * ((num2 - num3) * m_PushFactor);
			m_PushFactor /= 2f;
			if (m_TargetLine.a.Equals(m_TargetLine.b))
			{
				m_TargetPosition = m_TargetLine.a;
			}
			else
			{
				MathUtils.Distance(m_TargetLine.xz, position, out m_LanePosition);
				m_TargetPosition = MathUtils.Position(m_TargetLine, m_LanePosition);
				m_LanePosition = m_TargetLimits.min + m_LanePosition * (m_TargetLimits.max - m_TargetLimits.min) - 0.5f;
			}
			if (m_TerrainHeightData.isCreated)
			{
				m_TargetPosition.y = TerrainUtils.SampleHeight(ref m_TerrainHeightData, m_TargetPosition);
			}
			float num4 = math.min(1f, 0.7f + 0.3f * math.dot(float3, math.normalizesafe(componentData2.m_Velocity.xz)) + num3 / num2);
			num4 *= m_SpeedRange.max;
			x = componentData.m_Position.xz - m_CurrentPosition.xz;
			float num5 = math.length(x);
			float num6 = math.dot(x, float3);
			BlockerType blockerType = BlockerType.Crossing;
			if (num5 < num2 && num6 > 0f)
			{
				blockerType = BlockerType.Continuing;
				if (num5 > 0.01f)
				{
					float num7 = num6 * (num2 - num5) / (num2 * num5);
					num4 = math.min(num4, math.max(0f, math.max(1f, math.lerp(math.dot(float3, componentData2.m_Velocity.xz), m_SpeedRange.max, num3 / num2)) - num7));
				}
				else
				{
					num4 = 0f;
				}
			}
			num4 = MathUtils.Clamp(num4, m_SpeedRange);
			if (num4 < m_MaxSpeed)
			{
				m_MaxSpeed = num4;
				m_Blocker = other;
				m_BlockerType = blockerType;
			}
			return;
		}
		float num8 = (((objectGeometryData.m_Flags & Game.Objects.GeometryFlags.Standing) == 0) ? (math.cmax(objectGeometryData.m_Bounds.max.xz - objectGeometryData.m_Bounds.min.xz) * 0.5f) : math.cmax(objectGeometryData.m_LegSize.xz + objectGeometryData.m_LegOffset * 2f));
		float num9 = m_Size + num8 + 0.25f;
		Line2.Segment line = new Line2.Segment(m_CurrentPosition.xz, m_TargetPosition.xz);
		float t2;
		float num10 = MathUtils.Distance(line, componentData.m_Position.xz, out t2);
		if (num10 < num9)
		{
			float2 float4 = MathUtils.Position(line, t2 * 0.99f);
			float2 float5 = math.normalizesafe(m_TargetPosition.xz - m_CurrentPosition.xz);
			float2 x2 = float4 - componentData.m_Position.xz;
			x2 -= float5 * math.dot(x2, float5);
			x2 = math.normalizesafe(x2);
			float2 position2 = m_TargetPosition.xz + x2 * ((num9 - num10) * m_PushFactor);
			m_PushFactor /= 2f;
			if (m_TargetLine.a.Equals(m_TargetLine.b))
			{
				m_TargetPosition = m_TargetLine.a;
			}
			else
			{
				MathUtils.Distance(m_TargetLine.xz, position2, out m_LanePosition);
				m_TargetPosition = MathUtils.Position(m_TargetLine, m_LanePosition);
				m_LanePosition = m_TargetLimits.min + m_LanePosition * (m_TargetLimits.max - m_TargetLimits.min) - 0.5f;
			}
			if (m_TerrainHeightData.isCreated)
			{
				m_TargetPosition.y = TerrainUtils.SampleHeight(ref m_TerrainHeightData, m_TargetPosition);
			}
		}
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

- `public IterateFirstLane(Unity.Entities.Entity currentLane) : System.Boolean`  

```csharp
public bool IterateFirstLane(Entity currentLane)
	{
		m_Size = (m_PrefabObjectGeometry.m_Bounds.max.x - m_PrefabObjectGeometry.m_Bounds.min.x) * 0.5f;
		m_PushFactor = 0.75f;
		if (m_AreaLaneData.HasComponent(currentLane))
		{
			CalculateTargetLine(currentLane, m_TargetPosition);
			m_MovingObjectSearchTree.Iterate(ref this);
			m_StaticObjectSearchTree.Iterate(ref this);
			return false;
		}
		return false;
	}
```


