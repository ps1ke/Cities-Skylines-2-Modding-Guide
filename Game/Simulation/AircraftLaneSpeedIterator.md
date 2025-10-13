# Game.Simulation.AircraftLaneSpeedIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct AircraftLaneSpeedIterator
{
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.AircraftData> m_PrefabAircraftData;
    public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData;
    public Unity.Entities.Entity m_Entity;
    public Unity.Entities.Entity m_Ignore;
    public System.Int32 m_Priority;
    public System.Single m_TimeStep;
    public System.Single m_SafeTimeStep;
    public Game.Prefabs.AircraftData m_PrefabAircraft;
    public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
    public Colossal.Mathematics.Bounds1 m_SpeedRange;
    public System.Single m_MaxSpeed;
    public System.Single m_CanChangeLane;
    public Unity.Mathematics.float3 m_CurrentPosition;
    public System.Single m_Distance;
    public Unity.Entities.Entity m_Blocker;
    public Game.Vehicles.BlockerType m_BlockerType;
    private Unity.Entities.Entity m_Lane;
    private Game.Net.Curve m_Curve;
    private Unity.Mathematics.float2 m_CurveOffset;
    private Unity.Mathematics.float3 m_PrevPosition;
    private System.Single m_PrevDistance;

    private System.Void CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset);
    private System.Void CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset);
    private System.Single GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset);
    public System.Boolean IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float3 curveOffset);
    public System.Boolean IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset);
    public System.Void IterateTarget(Unity.Mathematics.float3 targetPosition);
    private System.Void UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.AircraftData> m_PrefabAircraftData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.AircraftData> m_PrefabAircraftData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData;
```

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Unity.Entities.Entity m_Ignore`  

```csharp
public Unity.Entities.Entity m_Ignore;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.Single m_TimeStep`  

```csharp
public System.Single m_TimeStep;
```

- `public System.Single m_SafeTimeStep`  

```csharp
public System.Single m_SafeTimeStep;
```

- `public Game.Prefabs.AircraftData m_PrefabAircraft`  

```csharp
public Game.Prefabs.AircraftData m_PrefabAircraft;
```

- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  

```csharp
public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
```

- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_SpeedRange;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public System.Single m_CanChangeLane`  

```csharp
public System.Single m_CanChangeLane;
```

- `public Unity.Mathematics.float3 m_CurrentPosition`  

```csharp
public Unity.Mathematics.float3 m_CurrentPosition;
```

- `public System.Single m_Distance`  

```csharp
public System.Single m_Distance;
```

- `public Unity.Entities.Entity m_Blocker`  

```csharp
public Unity.Entities.Entity m_Blocker;
```

- `public Game.Vehicles.BlockerType m_BlockerType`  

```csharp
public Game.Vehicles.BlockerType m_BlockerType;
```

- `private Unity.Entities.Entity m_Lane`  

```csharp
private Unity.Entities.Entity m_Lane;
```

- `private Game.Net.Curve m_Curve`  

```csharp
private Game.Net.Curve m_Curve;
```

- `private Unity.Mathematics.float2 m_CurveOffset`  

```csharp
private Unity.Mathematics.float2 m_CurveOffset;
```

- `private Unity.Mathematics.float3 m_PrevPosition`  

```csharp
private Unity.Mathematics.float3 m_PrevPosition;
```

- `private System.Single m_PrevDistance`  

```csharp
private System.Single m_PrevDistance;
```


## Methods

- `private CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset) : System.Void`  

```csharp
private void CheckCurrentLane(float distance, float2 minOffset)
	{
		if (!m_LaneObjectData.HasBuffer(m_Lane))
		{
			return;
		}
		DynamicBuffer<LaneObject> dynamicBuffer = m_LaneObjectData[m_Lane];
		if (dynamicBuffer.Length == 0)
		{
			return;
		}
		distance -= 1f;
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			LaneObject laneObject = dynamicBuffer[i];
			if (!(laneObject.m_LaneObject == m_Entity) && !(laneObject.m_LaneObject == m_Ignore))
			{
				float2 curvePosition = laneObject.m_CurvePosition;
				if (!(curvePosition.y <= minOffset.y) || (!(curvePosition.y < 1f) && !(curvePosition.x <= minOffset.x)))
				{
					float objectSpeed = GetObjectSpeed(laneObject.m_LaneObject, curvePosition.x);
					UpdateMaxSpeed(laneObject.m_LaneObject, BlockerType.Continuing, objectSpeed, curvePosition.x, 1f, distance);
				}
			}
		}
	}
```

- `private CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset) : System.Void`  

```csharp
private void CheckOverlappingLanes(float origDistance, float origMinOffset)
	{
		if (!m_LaneOverlapData.HasBuffer(m_Lane))
		{
			return;
		}
		DynamicBuffer<LaneOverlap> dynamicBuffer = m_LaneOverlapData[m_Lane];
		if (dynamicBuffer.Length == 0)
		{
			return;
		}
		origDistance -= 1f;
		float2 curveOffset = m_CurveOffset;
		float length = m_Curve.m_Length;
		int priority = m_Priority;
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			LaneOverlap laneOverlap = dynamicBuffer[i];
			float4 @float = new float4((int)laneOverlap.m_ThisStart, (int)laneOverlap.m_ThisEnd, (int)laneOverlap.m_OtherStart, (int)laneOverlap.m_OtherEnd) * 0.003921569f;
			if (@float.y <= curveOffset.x)
			{
				continue;
			}
			m_Lane = laneOverlap.m_Other;
			m_Curve = m_CurveData[m_Lane];
			m_CurveOffset = @float.zw;
			float num = math.max(0f, origMinOffset - @float.x) + @float.z;
			float num2 = origDistance + length * (@float.x - curveOffset.x);
			float distanceFactor = (float)(int)laneOverlap.m_Parallelism * (1f / 128f);
			int num3 = priority;
			BlockerType blockerType = (((laneOverlap.m_Flags & (OverlapFlags.MergeEnd | OverlapFlags.MergeMiddleEnd)) != 0) ? BlockerType.Continuing : BlockerType.Crossing);
			if ((laneOverlap.m_Flags & (OverlapFlags.MergeStart | OverlapFlags.MergeMiddleStart)) == 0 && @float.x > origMinOffset)
			{
				num3 -= laneOverlap.m_PriorityDelta;
				if (m_LaneReservationData.HasComponent(m_Lane))
				{
					LaneReservation laneReservation = m_LaneReservationData[m_Lane];
					float offset = laneReservation.GetOffset();
					int priority2 = laneReservation.GetPriority();
					if (offset > math.max(num, m_CurveOffset.x) || priority2 > num3)
					{
						float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabAircraft, num2, m_SafeTimeStep);
						maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
						if (maxBrakingSpeed < m_MaxSpeed)
						{
							m_MaxSpeed = maxBrakingSpeed;
							m_Blocker = Entity.Null;
							m_BlockerType = blockerType;
						}
					}
				}
			}
			if (!m_LaneObjectData.HasBuffer(m_Lane))
			{
				continue;
			}
			DynamicBuffer<LaneObject> dynamicBuffer2 = m_LaneObjectData[m_Lane];
			if (dynamicBuffer2.Length == 0)
			{
				continue;
			}
			m_CurrentPosition = MathUtils.Position(m_Curve.m_Bezier, m_CurveOffset.x);
			for (int j = 0; j < dynamicBuffer2.Length; j++)
			{
				LaneObject laneObject = dynamicBuffer2[j];
				if (laneObject.m_LaneObject == m_Ignore)
				{
					continue;
				}
				float2 curvePosition = laneObject.m_CurvePosition;
				float objectSpeed = GetObjectSpeed(laneObject.m_LaneObject, curvePosition.x);
				if ((laneOverlap.m_Flags & (OverlapFlags.MergeStart | OverlapFlags.MergeMiddleStart)) == 0 && (@float.x >= origMinOffset || curvePosition.y > @float.z))
				{
					int num4;
					if (m_AircraftData.HasComponent(laneObject.m_LaneObject))
					{
						PrefabRef prefabRef = m_PrefabRefData[laneObject.m_LaneObject];
						num4 = VehicleUtils.GetPriority(m_PrefabAircraftData[prefabRef.m_Prefab]);
					}
					else
					{
						num4 = 0;
					}
					int num5 = num4 - num3;
					if (num5 > 0)
					{
						curvePosition.y += objectSpeed * 2f / math.max(1f, m_Curve.m_Length);
					}
					else if (num5 < 0)
					{
						curvePosition.y -= math.max(0f, @float.z - num);
					}
				}
				if (!(curvePosition.y <= num))
				{
					UpdateMaxSpeed(laneObject.m_LaneObject, blockerType, objectSpeed, curvePosition.x, distanceFactor, num2);
				}
			}
		}
	}
```

- `private GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset) : System.Single`  

```csharp
private float GetObjectSpeed(Entity obj, float curveOffset)
	{
		if (!m_MovingData.HasComponent(obj))
		{
			return 0f;
		}
		Moving moving = m_MovingData[obj];
		return math.dot(y: math.normalizesafe(MathUtils.Tangent(m_Curve.m_Bezier, curveOffset)), x: moving.m_Velocity);
	}
```

- `public IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float3 curveOffset) : System.Boolean`  

```csharp
public bool IterateFirstLane(Entity lane, float3 curveOffset)
	{
		Curve curve = m_CurveData[lane];
		float3 @float = MathUtils.Position(curve.m_Bezier, curveOffset.x);
		m_PrevPosition = m_CurrentPosition;
		m_Distance = math.distance(m_CurrentPosition.xz, @float.xz);
		if (m_CarLaneData.HasComponent(lane))
		{
			Game.Net.CarLane carLaneData = m_CarLaneData[lane];
			float num = VehicleUtils.GetMaxDriveSpeed(m_PrefabAircraft, carLaneData);
			if (m_Priority < 102 && m_LaneReservationData.HasComponent(lane) && m_LaneReservationData[lane].GetPriority() == 102)
			{
				num *= 0.5f;
			}
			if (num < m_MaxSpeed)
			{
				m_MaxSpeed = MathUtils.Clamp(num, m_SpeedRange);
				m_Blocker = Entity.Null;
				m_BlockerType = BlockerType.Limit;
			}
			float2 xy = curveOffset.xy;
			float num2 = 0f - m_PrefabObjectGeometry.m_Bounds.max.z;
			float num3 = m_Distance + num2;
			m_Lane = lane;
			m_Curve = curve;
			m_CurveOffset = curveOffset.xz;
			m_CurrentPosition = @float;
			CheckCurrentLane(num3, xy);
			CheckOverlappingLanes(num3, xy.y);
		}
		float3 float2 = MathUtils.Position(curve.m_Bezier, curveOffset.z);
		float num4 = math.abs(curveOffset.z - curveOffset.x);
		float num5 = math.max(0.001f, math.lerp(math.distance(@float, float2), curve.m_Length * num4, num4));
		if (num5 > 1f)
		{
			m_PrevPosition = m_CurrentPosition;
			m_PrevDistance = m_Distance;
		}
		m_CurrentPosition = float2;
		m_Distance += num5;
		float brakingDistance = VehicleUtils.GetBrakingDistance(m_PrefabAircraft, m_MaxSpeed, m_SafeTimeStep);
		return (m_Distance - 20f >= brakingDistance) | (m_MaxSpeed == m_SpeedRange.min);
	}
```

- `public IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset) : System.Boolean`  

```csharp
public bool IterateNextLane(Entity lane, float2 curveOffset, float minOffset)
	{
		if (!m_CurveData.HasComponent(lane))
		{
			return false;
		}
		Curve curve = m_CurveData[lane];
		if (m_CarLaneData.HasComponent(lane))
		{
			Game.Net.CarLane carLaneData = m_CarLaneData[lane];
			float maxDriveSpeed = VehicleUtils.GetMaxDriveSpeed(m_PrefabAircraft, carLaneData);
			float num = 0f - m_PrefabObjectGeometry.m_Bounds.max.z;
			float num2 = m_Distance + num;
			float num3 = ((maxDriveSpeed != 0f) ? math.max(maxDriveSpeed, VehicleUtils.GetMaxBrakingSpeed(m_PrefabAircraft, m_Distance, maxDriveSpeed, m_TimeStep)) : VehicleUtils.GetMaxBrakingSpeed(m_PrefabAircraft, num2, m_SafeTimeStep));
			if (num3 < m_MaxSpeed)
			{
				m_MaxSpeed = MathUtils.Clamp(num3, m_SpeedRange);
				m_Blocker = Entity.Null;
				m_BlockerType = BlockerType.Limit;
			}
			m_Curve = curve;
			m_CurveOffset = curveOffset;
			m_Lane = lane;
			minOffset = math.select(minOffset, curveOffset.x, curveOffset.x > 0f);
			CheckCurrentLane(num2, minOffset);
			CheckOverlappingLanes(num2, minOffset);
		}
		float3 @float = MathUtils.Position(curve.m_Bezier, curveOffset.y);
		float num4 = math.abs(curveOffset.y - curveOffset.x);
		float num5 = math.max(0.001f, math.lerp(math.distance(m_CurrentPosition, @float), curve.m_Length * num4, num4));
		if (num5 > 1f)
		{
			m_PrevPosition = m_CurrentPosition;
			m_PrevDistance = m_Distance;
		}
		m_CurrentPosition = @float;
		m_Distance += num5;
		float brakingDistance = VehicleUtils.GetBrakingDistance(m_PrefabAircraft, m_MaxSpeed, m_SafeTimeStep);
		return (m_Distance - 20f >= brakingDistance) | (m_MaxSpeed == m_SpeedRange.min);
	}
```

- `public IterateTarget(Unity.Mathematics.float3 targetPosition) : System.Void`  

```csharp
public void IterateTarget(float3 targetPosition)
	{
		float maxDriveSpeed = VehicleUtils.GetMaxDriveSpeed(m_PrefabAircraft, 11.111112f, MathF.PI / 12f);
		float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabAircraft, m_Distance, maxDriveSpeed, m_TimeStep);
		m_Distance += math.distance(m_CurrentPosition.xz, targetPosition.xz);
		maxBrakingSpeed = math.min(maxBrakingSpeed, VehicleUtils.GetMaxBrakingSpeed(m_PrefabAircraft, m_Distance, m_TimeStep));
		if (maxBrakingSpeed < m_MaxSpeed)
		{
			m_MaxSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
			m_Blocker = Entity.Null;
			m_BlockerType = BlockerType.None;
		}
	}
```

- `private UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset) : System.Void`  

```csharp
private void UpdateMaxSpeed(Entity obj, BlockerType blockerType, float objectSpeed, float laneOffset, float distanceFactor, float distanceOffset)
	{
		PrefabRef prefabRef = m_PrefabRefData[obj];
		float num = 0f;
		if (m_PrefabObjectGeometryData.HasComponent(prefabRef.m_Prefab))
		{
			num = math.max(0f, 0f - m_PrefabObjectGeometryData[prefabRef.m_Prefab].m_Bounds.min.z);
		}
		if ((laneOffset - m_CurveOffset.y) * m_Curve.m_Length >= num)
		{
			return;
		}
		Transform transform = m_TransformData[obj];
		float num2 = math.distance(MathUtils.Position(m_Curve.m_Bezier, math.max(m_CurveOffset.x, laneOffset)).xz, m_CurrentPosition.xz);
		num2 -= math.max(0f, m_CurveOffset.x - laneOffset) * m_Curve.m_Length;
		num2 = ((!(math.dot(transform.m_Position.xz - m_CurrentPosition.xz, m_CurrentPosition.xz - m_PrevPosition.xz) < 0f)) ? math.min(num2, math.distance(transform.m_Position.xz, m_CurrentPosition.xz)) : math.min(num2, math.distance(transform.m_Position.xz, m_PrevPosition.xz) + m_PrevDistance - m_Distance));
		num2 -= num;
		num2 *= distanceFactor;
		num2 += distanceOffset;
		float maxBrakingSpeed;
		if (objectSpeed > 0.001f && m_PrefabAircraftData.HasComponent(prefabRef.m_Prefab))
		{
			AircraftData prefabAircraftData = m_PrefabAircraftData[prefabRef.m_Prefab];
			objectSpeed = math.max(0f, objectSpeed - prefabAircraftData.m_GroundBraking * m_TimeStep * 2f) * distanceFactor;
			if (m_PrefabAircraft.m_GroundBraking >= prefabAircraftData.m_GroundBraking)
			{
				num2 += objectSpeed * m_SafeTimeStep;
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabAircraft, num2, objectSpeed, m_SafeTimeStep);
			}
			else
			{
				num2 += VehicleUtils.GetBrakingDistance(prefabAircraftData, objectSpeed, m_SafeTimeStep);
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabAircraft, num2, m_SafeTimeStep);
			}
		}
		else
		{
			maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabAircraft, num2, m_SafeTimeStep);
		}
		maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
		if (maxBrakingSpeed < m_MaxSpeed)
		{
			m_MaxSpeed = maxBrakingSpeed;
			m_Blocker = obj;
			m_BlockerType = blockerType;
		}
	}
```


