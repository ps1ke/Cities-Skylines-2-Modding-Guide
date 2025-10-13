# Game.Simulation.TrainLaneSpeedIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TrainLaneSpeedIterator
{
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.TrackLane> m_TrackLaneData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData;
    public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.CarData> m_PrefabCarData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.TrainData> m_PrefabTrainData;
    public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData;
    public Unity.Entities.Entity m_Controller;
    public System.Int32 m_Priority;
    public System.Single m_TimeStep;
    public System.Single m_SafeTimeStep;
    public System.Single m_CurrentSpeed;
    public Game.Prefabs.TrainData m_PrefabTrain;
    public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
    public Colossal.Mathematics.Bounds1 m_SpeedRange;
    public Unity.Mathematics.float3 m_RearPosition;
    public System.Boolean m_PushBlockers;
    public System.Single m_MaxSpeed;
    public Unity.Mathematics.float3 m_CurrentPosition;
    public System.Single m_Distance;
    public Unity.Entities.Entity m_Blocker;
    public Game.Vehicles.BlockerType m_BlockerType;
    private Unity.Entities.Entity m_Lane;
    private Game.Net.Curve m_Curve;
    private Unity.Mathematics.float2 m_CurveOffset;
    private Unity.Mathematics.float3 m_PrevPosition;
    private System.Single m_PrevDistance;

    private System.Void CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean exclusive);
    private System.Void CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset, System.Int32 yieldOverride, System.Boolean exclusive);
    private System.Void CheckPedestrian(Colossal.Mathematics.Line3+Segment overlapLine, Unity.Entities.Entity obj, System.Single targetOffset, System.Single distanceOffset, System.Boolean giveSpace);
    private System.Single GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset);
    public System.Boolean IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float4 curveOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean skipCurrent, System.Boolean& needSignal);
    public System.Boolean IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean& needSignal);
    public System.Void IteratePrevLane(Unity.Entities.Entity lane, System.Boolean& needSignal);
    public System.Boolean IterateTarget(Unity.Entities.Entity lane, System.Boolean ignoreObstacles);
    public System.Boolean IterateTarget();
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

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.TrackLane> m_TrackLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.TrackLane> m_TrackLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData;
```

- `public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.CarData> m_PrefabCarData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.CarData> m_PrefabCarData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.TrainData> m_PrefabTrainData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.TrainData> m_PrefabTrainData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData;
```

- `public Unity.Entities.Entity m_Controller`  

```csharp
public Unity.Entities.Entity m_Controller;
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

- `public System.Single m_CurrentSpeed`  

```csharp
public System.Single m_CurrentSpeed;
```

- `public Game.Prefabs.TrainData m_PrefabTrain`  

```csharp
public Game.Prefabs.TrainData m_PrefabTrain;
```

- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  

```csharp
public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
```

- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_SpeedRange;
```

- `public Unity.Mathematics.float3 m_RearPosition`  

```csharp
public Unity.Mathematics.float3 m_RearPosition;
```

- `public System.Boolean m_PushBlockers`  

```csharp
public System.Boolean m_PushBlockers;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
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

- `private CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean exclusive) : System.Void`  

```csharp
private void CheckCurrentLane(float distance, float2 minOffset, bool exclusive)
	{
		if (!m_LaneObjectData.TryGetBuffer(m_Lane, out var bufferData) || bufferData.Length == 0)
		{
			return;
		}
		distance = ((!exclusive) ? (distance - 1f) : (distance - 10f));
		for (int i = 0; i < bufferData.Length; i++)
		{
			LaneObject laneObject = bufferData[i];
			if (laneObject.m_LaneObject == m_Controller || (m_ControllerData.TryGetComponent(laneObject.m_LaneObject, out var componentData) && componentData.m_Controller == m_Controller))
			{
				continue;
			}
			if (exclusive)
			{
				float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, distance, m_SafeTimeStep);
				maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
				if (maxBrakingSpeed < m_MaxSpeed)
				{
					m_MaxSpeed = maxBrakingSpeed;
					m_Blocker = laneObject.m_LaneObject;
					m_BlockerType = BlockerType.Continuing;
				}
			}
			else
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

- `private CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset, System.Int32 yieldOverride, System.Boolean exclusive) : System.Void`  

```csharp
private void CheckOverlappingLanes(float origDistance, float origMinOffset, int yieldOverride, bool exclusive)
	{
		if (!m_LaneOverlapData.TryGetBuffer(m_Lane, out var bufferData) || bufferData.Length == 0)
		{
			return;
		}
		float distance = origDistance - 10f;
		origDistance -= 1f;
		Bezier4x3 bezier = m_Curve.m_Bezier;
		float2 curveOffset = m_CurveOffset;
		float length = m_Curve.m_Length;
		int num = m_Priority;
		if (m_LaneReservationData.TryGetComponent(m_Lane, out var componentData))
		{
			int priority = componentData.GetPriority();
			num = math.select(num, 106, priority >= 108 && 106 > num);
		}
		for (int i = 0; i < bufferData.Length; i++)
		{
			LaneOverlap laneOverlap = bufferData[i];
			float4 @float = new float4((int)laneOverlap.m_ThisStart, (int)laneOverlap.m_ThisEnd, (int)laneOverlap.m_OtherStart, (int)laneOverlap.m_OtherEnd) * 0.003921569f;
			if (@float.y <= curveOffset.x)
			{
				continue;
			}
			BlockerType blockerType = (((laneOverlap.m_Flags & (OverlapFlags.MergeEnd | OverlapFlags.MergeMiddleEnd)) != 0) ? BlockerType.Continuing : BlockerType.Crossing);
			DynamicBuffer<LaneObject> bufferData2;
			if (exclusive && m_TrackLaneData.TryGetComponent(laneOverlap.m_Other, out var componentData2) && (componentData2.m_Flags & TrackLaneFlags.Exclusive) != 0)
			{
				if (m_LaneReservationData.TryGetComponent(laneOverlap.m_Other, out componentData) && componentData.GetPriority() >= m_Priority)
				{
					float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, distance, m_SafeTimeStep);
					maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
					if (maxBrakingSpeed < m_MaxSpeed)
					{
						m_MaxSpeed = maxBrakingSpeed;
						m_Blocker = componentData.m_Blocker;
						m_BlockerType = blockerType;
					}
				}
				if (!m_LaneObjectData.TryGetBuffer(laneOverlap.m_Other, out bufferData2) || bufferData2.Length == 0)
				{
					continue;
				}
				for (int j = 0; j < bufferData2.Length; j++)
				{
					LaneObject laneObject = bufferData2[j];
					if (!(laneObject.m_LaneObject == m_Controller) && (!m_ControllerData.TryGetComponent(laneObject.m_LaneObject, out var componentData3) || !(componentData3.m_Controller == m_Controller)))
					{
						float maxBrakingSpeed2 = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, distance, m_SafeTimeStep);
						maxBrakingSpeed2 = MathUtils.Clamp(maxBrakingSpeed2, m_SpeedRange);
						if (maxBrakingSpeed2 < m_MaxSpeed)
						{
							m_MaxSpeed = maxBrakingSpeed2;
							m_Blocker = laneObject.m_LaneObject;
							m_BlockerType = blockerType;
						}
					}
				}
				continue;
			}
			m_Lane = laneOverlap.m_Other;
			m_Curve = m_CurveData[m_Lane];
			m_CurveOffset = @float.zw;
			Line3.Segment overlapLine = MathUtils.Line(bezier, @float.xy);
			float num2 = math.max(0f, origMinOffset - @float.x) + @float.z;
			float num3 = origDistance + length * (@float.x - curveOffset.x);
			float distanceFactor = (float)(int)laneOverlap.m_Parallelism * (1f / 128f);
			int num4 = num;
			if ((laneOverlap.m_Flags & (OverlapFlags.MergeStart | OverlapFlags.MergeMiddleStart)) == 0 && @float.x > origMinOffset)
			{
				int num5 = yieldOverride;
				if (m_LaneSignalData.HasComponent(m_Lane))
				{
					switch (m_LaneSignalData[m_Lane].m_Signal)
					{
					case LaneSignalType.Stop:
						num5++;
						break;
					case LaneSignalType.Yield:
						num5--;
						break;
					}
				}
				int num6 = math.select(laneOverlap.m_PriorityDelta, num5, num5 != 0);
				num4 -= num6;
				if (m_LaneReservationData.TryGetComponent(m_Lane, out componentData))
				{
					float offset = componentData.GetOffset();
					int priority2 = componentData.GetPriority();
					if (offset > math.max(num2, m_CurveOffset.x) || priority2 > num4)
					{
						float maxBrakingSpeed3 = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, num3, m_SafeTimeStep);
						maxBrakingSpeed3 = MathUtils.Clamp(maxBrakingSpeed3, m_SpeedRange);
						if (maxBrakingSpeed3 < m_MaxSpeed)
						{
							m_MaxSpeed = maxBrakingSpeed3;
							m_Blocker = componentData.m_Blocker;
							m_BlockerType = blockerType;
						}
					}
				}
			}
			if (!m_LaneObjectData.TryGetBuffer(m_Lane, out bufferData2) || bufferData2.Length == 0)
			{
				continue;
			}
			m_CurrentPosition = MathUtils.Position(m_Curve.m_Bezier, m_CurveOffset.x);
			for (int k = 0; k < bufferData2.Length; k++)
			{
				LaneObject laneObject2 = bufferData2[k];
				if (laneObject2.m_LaneObject == m_Controller)
				{
					continue;
				}
				Entity entity = laneObject2.m_LaneObject;
				if (m_ControllerData.TryGetComponent(laneObject2.m_LaneObject, out var componentData4))
				{
					if (componentData4.m_Controller == m_Controller)
					{
						continue;
					}
					entity = componentData4.m_Controller;
				}
				if (m_CreatureData.HasComponent(laneObject2.m_LaneObject))
				{
					CheckPedestrian(overlapLine, laneObject2.m_LaneObject, laneObject2.m_CurvePosition.y, num3, giveSpace: false);
					continue;
				}
				float2 curvePosition = laneObject2.m_CurvePosition;
				float objectSpeed = GetObjectSpeed(laneObject2.m_LaneObject, curvePosition.x);
				if ((laneOverlap.m_Flags & (OverlapFlags.MergeStart | OverlapFlags.MergeMiddleStart)) == 0 && (@float.x >= origMinOffset || curvePosition.y > @float.z))
				{
					int num7;
					if (m_CarData.TryGetComponent(entity, out var componentData5))
					{
						num7 = VehicleUtils.GetPriority(componentData5);
					}
					else if (m_TrainData.HasComponent(laneObject2.m_LaneObject))
					{
						PrefabRef prefabRef = m_PrefabRefData[laneObject2.m_LaneObject];
						num7 = VehicleUtils.GetPriority(m_PrefabTrainData[prefabRef.m_Prefab]);
					}
					else
					{
						num7 = 0;
					}
					if (num7 - num4 > 0)
					{
						curvePosition.y += objectSpeed * 2f / math.max(1f, m_Curve.m_Length);
					}
				}
				if (!(curvePosition.y <= num2))
				{
					UpdateMaxSpeed(laneObject2.m_LaneObject, blockerType, objectSpeed, curvePosition.x, distanceFactor, num3);
				}
			}
		}
	}
```

- `private CheckPedestrian(Colossal.Mathematics.Line3+Segment overlapLine, Unity.Entities.Entity obj, System.Single targetOffset, System.Single distanceOffset, System.Boolean giveSpace) : System.Void`  

```csharp
private void CheckPedestrian(Line3.Segment overlapLine, Entity obj, float targetOffset, float distanceOffset, bool giveSpace)
	{
		if ((targetOffset <= m_CurveOffset.x) | (targetOffset >= m_CurveOffset.y))
		{
			PrefabRef prefabRef = m_PrefabRefData[obj];
			Transform transform = m_TransformData[obj];
			float num = m_PrefabObjectGeometry.m_Size.x * 0.5f;
			if (m_PrefabObjectGeometryData.HasComponent(prefabRef.m_Prefab))
			{
				num += m_PrefabObjectGeometryData[prefabRef.m_Prefab].m_Size.z * 0.5f;
			}
			float t;
			float num2 = MathUtils.Distance(overlapLine.xz, transform.m_Position.xz, out t);
			float num3 = math.dot(math.forward(transform.m_Rotation).xz, math.normalizesafe(MathUtils.Position(overlapLine, t).xz - transform.m_Position.xz));
			if (num2 - math.select(math.min(0f - num3, 0f), math.max(num3, 0f), giveSpace) >= num)
			{
				return;
			}
		}
		float position = ((m_PushBlockers || !m_MovingData.TryGetComponent(obj, out var componentData) || !(math.lengthsq(componentData.m_Velocity) >= 0.01f)) ? math.max(3f, VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, distanceOffset, 3f, m_SafeTimeStep)) : VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, distanceOffset, m_SafeTimeStep));
		position = MathUtils.Clamp(position, m_SpeedRange);
		if (position < m_MaxSpeed)
		{
			m_MaxSpeed = position;
			m_Blocker = obj;
			m_BlockerType = BlockerType.Temporary;
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

- `public IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float4 curveOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean skipCurrent, System.Boolean& needSignal) : System.Boolean`  

```csharp
public bool IterateFirstLane(Entity lane, float4 curveOffset, bool exclusive, bool ignoreObstacles, bool skipCurrent, out bool needSignal)
	{
		Curve curve = m_CurveData[lane];
		needSignal = false;
		float3 @float = MathUtils.Position(curve.m_Bezier, curveOffset.y);
		m_PrevPosition = m_CurrentPosition;
		m_PrevDistance = 0f - (m_PrefabTrain.m_AttachOffsets.x - m_PrefabTrain.m_BogieOffsets.x);
		m_Distance = math.distance(m_CurrentPosition, @float);
		m_Distance = math.min(m_Distance, math.distance(m_RearPosition, @float) - math.max(1f, math.csum(m_PrefabTrain.m_BogieOffsets)));
		m_Distance -= m_PrefabTrain.m_AttachOffsets.x - m_PrefabTrain.m_BogieOffsets.x;
		if (m_TrackLaneData.TryGetComponent(lane, out var componentData))
		{
			int yieldOverride = 0;
			if (m_LaneSignalData.TryGetComponent(lane, out var componentData2))
			{
				switch (componentData2.m_Signal)
				{
				case LaneSignalType.Stop:
					yieldOverride = -1;
					break;
				case LaneSignalType.Yield:
					yieldOverride = 1;
					break;
				}
				if (lane != m_Lane)
				{
					needSignal = true;
				}
			}
			m_Lane = lane;
			m_Curve = curve;
			m_CurveOffset = curveOffset.yw;
			m_CurrentPosition = @float;
			float num = VehicleUtils.GetMaxDriveSpeed(m_PrefabTrain, componentData);
			if (!exclusive && m_LaneReservationData.TryGetComponent(lane, out var componentData3) && componentData3.GetPriority() == 102)
			{
				num *= 0.5f;
			}
			if (num < m_MaxSpeed)
			{
				m_MaxSpeed = MathUtils.Clamp(num, m_SpeedRange);
				m_Blocker = Entity.Null;
				m_BlockerType = BlockerType.Limit;
			}
			if (!ignoreObstacles)
			{
				if (!exclusive && !skipCurrent)
				{
					CheckCurrentLane(m_Distance, curveOffset.yz, exclusive);
				}
				CheckOverlappingLanes(m_Distance, curveOffset.z, yieldOverride, exclusive);
			}
		}
		float3 float2 = MathUtils.Position(curve.m_Bezier, curveOffset.w);
		float num2 = math.abs(curveOffset.w - curveOffset.y);
		float num3 = math.max(0.001f, math.lerp(math.distance(@float, float2), curve.m_Length * num2, num2));
		if (num3 > 1f)
		{
			m_PrevPosition = m_CurrentPosition;
			m_PrevDistance = m_Distance;
		}
		m_CurrentPosition = float2;
		m_Distance += num3;
		float brakingDistance = VehicleUtils.GetBrakingDistance(m_PrefabTrain, m_MaxSpeed, m_SafeTimeStep);
		brakingDistance += VehicleUtils.GetSignalDistance(m_PrefabTrain, m_MaxSpeed);
		return (m_Distance - 10f >= brakingDistance) | (m_MaxSpeed == m_SpeedRange.min);
	}
```

- `public IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean& needSignal) : System.Boolean`  

```csharp
public bool IterateNextLane(Entity lane, float2 curveOffset, float minOffset, bool exclusive, bool ignoreObstacles, out bool needSignal)
	{
		needSignal = false;
		if (!m_CurveData.TryGetComponent(lane, out var componentData))
		{
			return false;
		}
		if (m_TrackLaneData.TryGetComponent(lane, out var componentData2))
		{
			float num = VehicleUtils.GetMaxDriveSpeed(m_PrefabTrain, componentData2);
			int yieldOverride = 0;
			Entity blocker = Entity.Null;
			BlockerType blockerType = BlockerType.Limit;
			if (m_LaneSignalData.TryGetComponent(lane, out var componentData3))
			{
				needSignal = true;
				switch (componentData3.m_Signal)
				{
				case LaneSignalType.Stop:
					if ((m_Priority < 108 || (componentData3.m_Flags & LaneSignalFlags.Physical) != 0) && VehicleUtils.GetBrakingDistance(m_PrefabTrain, m_CurrentSpeed, 0f) <= m_Distance + 1f)
					{
						num = 0f;
						blocker = componentData3.m_Blocker;
						blockerType = BlockerType.Signal;
						yieldOverride = 1;
					}
					else
					{
						yieldOverride = -1;
					}
					break;
				case LaneSignalType.SafeStop:
					if ((m_Priority < 108 || (componentData3.m_Flags & LaneSignalFlags.Physical) != 0) && VehicleUtils.GetBrakingDistance(m_PrefabTrain, m_CurrentSpeed, 0f) <= m_Distance)
					{
						num = 0f;
						blocker = componentData3.m_Blocker;
						blockerType = BlockerType.Signal;
					}
					break;
				case LaneSignalType.Yield:
					yieldOverride = 1;
					break;
				}
			}
			float num2;
			if (num == 0f)
			{
				float y = m_Distance - math.select(10f, 0.5f, (m_PrefabTrain.m_TrackType & TrackTypes.Tram) != 0);
				num2 = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, math.max(0f, y), m_SafeTimeStep);
			}
			else
			{
				num2 = math.max(num, VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, m_Distance, num, m_TimeStep));
			}
			if (num2 < m_MaxSpeed)
			{
				m_MaxSpeed = MathUtils.Clamp(num2, m_SpeedRange);
				m_Blocker = blocker;
				m_BlockerType = blockerType;
			}
			if (!ignoreObstacles)
			{
				m_Lane = lane;
				m_Curve = componentData;
				m_CurveOffset = curveOffset;
				CheckCurrentLane(m_Distance, minOffset, exclusive);
				CheckOverlappingLanes(m_Distance, minOffset, yieldOverride, exclusive);
			}
		}
		float3 @float = MathUtils.Position(componentData.m_Bezier, curveOffset.y);
		float num3 = math.abs(curveOffset.y - curveOffset.x);
		float num4 = math.max(0.001f, math.lerp(math.distance(m_CurrentPosition, @float), componentData.m_Length * num3, num3));
		if (num4 > 1f)
		{
			m_PrevPosition = m_CurrentPosition;
			m_PrevDistance = m_Distance;
		}
		m_CurrentPosition = @float;
		m_Distance += num4;
		float brakingDistance = VehicleUtils.GetBrakingDistance(m_PrefabTrain, m_MaxSpeed, m_SafeTimeStep);
		brakingDistance += VehicleUtils.GetSignalDistance(m_PrefabTrain, m_MaxSpeed);
		return (m_Distance - 10f >= brakingDistance) | (m_MaxSpeed == m_SpeedRange.min);
	}
```

- `public IteratePrevLane(Unity.Entities.Entity lane, System.Boolean& needSignal) : System.Void`  

```csharp
public void IteratePrevLane(Entity lane, out bool needSignal)
	{
		needSignal = false;
		if (lane != m_Lane && m_TrackLaneData.TryGetComponent(lane, out var componentData))
		{
			if (m_LaneSignalData.HasComponent(lane))
			{
				needSignal = true;
			}
			m_Lane = lane;
			float maxDriveSpeed = VehicleUtils.GetMaxDriveSpeed(m_PrefabTrain, componentData);
			if (maxDriveSpeed < m_MaxSpeed)
			{
				m_MaxSpeed = MathUtils.Clamp(maxDriveSpeed, m_SpeedRange);
				m_Blocker = Entity.Null;
				m_BlockerType = BlockerType.Limit;
			}
		}
	}
```

- `public IterateTarget(Unity.Entities.Entity lane, System.Boolean ignoreObstacles) : System.Boolean`  

```csharp
public bool IterateTarget()
	{
		float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, m_Distance, m_TimeStep);
		if (maxBrakingSpeed < m_MaxSpeed)
		{
			m_MaxSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
			m_Blocker = Entity.Null;
			m_BlockerType = BlockerType.None;
			return true;
		}
		return false;
	}
```

- `public IterateTarget() : System.Boolean`  

```csharp
public bool IterateTarget()
	{
		float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, m_Distance, m_TimeStep);
		if (maxBrakingSpeed < m_MaxSpeed)
		{
			m_MaxSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
			m_Blocker = Entity.Null;
			m_BlockerType = BlockerType.None;
			return true;
		}
		return false;
	}
```

- `private UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset) : System.Void`  

```csharp
private void UpdateMaxSpeed(Entity obj, BlockerType blockerType, float objectSpeed, float laneOffset, float distanceFactor, float distanceOffset)
	{
		PrefabRef prefabRef = m_PrefabRefData[obj];
		float num = 0f;
		if (m_PrefabTrainData.HasComponent(prefabRef.m_Prefab))
		{
			Train train = m_TrainData[obj];
			TrainData trainData = m_PrefabTrainData[prefabRef.m_Prefab];
			float2 @float = trainData.m_AttachOffsets - trainData.m_BogieOffsets;
			num = math.select(@float.y, @float.x, (train.m_Flags & Game.Vehicles.TrainFlags.Reversed) != 0);
		}
		else if (m_PrefabObjectGeometryData.HasComponent(prefabRef.m_Prefab))
		{
			num = 0f - m_PrefabObjectGeometryData[prefabRef.m_Prefab].m_Bounds.min.z;
		}
		if ((laneOffset - m_CurveOffset.y) * m_Curve.m_Length >= num)
		{
			return;
		}
		Transform transform = m_TransformData[obj];
		float num2 = math.distance(MathUtils.Position(m_Curve.m_Bezier, math.max(m_CurveOffset.x, laneOffset)), m_CurrentPosition);
		num2 -= math.max(0f, m_CurveOffset.x - laneOffset) * m_Curve.m_Length;
		num2 = ((!(math.dot(transform.m_Position - m_CurrentPosition, m_CurrentPosition - m_PrevPosition) < 0f)) ? math.min(num2, math.distance(transform.m_Position, m_CurrentPosition)) : math.min(num2, math.distance(transform.m_Position, m_PrevPosition) + m_PrevDistance - m_Distance));
		num2 -= num;
		num2 *= distanceFactor;
		num2 += distanceOffset;
		float maxBrakingSpeed;
		if (objectSpeed > 0.001f && m_PrefabCarData.HasComponent(prefabRef.m_Prefab))
		{
			CarData prefabCarData = m_PrefabCarData[prefabRef.m_Prefab];
			objectSpeed = math.max(0f, objectSpeed - prefabCarData.m_Braking * m_TimeStep * 2f) * distanceFactor;
			if (m_PrefabTrain.m_Braking >= prefabCarData.m_Braking)
			{
				num2 += objectSpeed * m_SafeTimeStep;
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, num2, objectSpeed, m_SafeTimeStep);
			}
			else
			{
				num2 += VehicleUtils.GetBrakingDistance(prefabCarData, objectSpeed, m_SafeTimeStep);
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, num2, m_SafeTimeStep);
			}
		}
		else if (objectSpeed > 0.001f && m_PrefabTrainData.HasComponent(prefabRef.m_Prefab))
		{
			TrainData prefabTrainData = m_PrefabTrainData[prefabRef.m_Prefab];
			objectSpeed = math.max(0f, objectSpeed - prefabTrainData.m_Braking * m_TimeStep * 2f) * distanceFactor;
			if (m_PrefabTrain.m_Braking >= prefabTrainData.m_Braking)
			{
				num2 += objectSpeed * m_SafeTimeStep;
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, num2, objectSpeed, m_SafeTimeStep);
			}
			else
			{
				num2 += VehicleUtils.GetBrakingDistance(prefabTrainData, objectSpeed, m_SafeTimeStep);
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, num2, m_SafeTimeStep);
			}
		}
		else
		{
			maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabTrain, num2, m_SafeTimeStep);
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


