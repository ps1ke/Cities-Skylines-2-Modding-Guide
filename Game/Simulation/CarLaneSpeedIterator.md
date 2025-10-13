# Game.Simulation.CarLaneSpeedIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CarLaneSpeedIterator
{
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneCondition> m_LaneConditionData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.ParkingLane> m_ParkingLaneData;
    public Unity.Entities.ComponentLookup<Game.Objects.Unspawned> m_UnspawnedData;
    public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.CarData> m_PrefabCarData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.TrainData> m_PrefabTrainData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ParkingLaneData> m_PrefabParkingLaneData;
    public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData;
    public Unity.Entities.Entity m_Entity;
    public Unity.Entities.Entity m_Ignore;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_TempBuffer;
    public System.Int32 m_Priority;
    public System.Single m_TimeStep;
    public System.Single m_SafeTimeStep;
    public System.Single m_DistanceOffset;
    public System.Single m_SpeedLimitFactor;
    public System.Single m_CurrentSpeed;
    public Game.Prefabs.CarData m_PrefabCar;
    public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
    public Colossal.Mathematics.Bounds1 m_SpeedRange;
    public System.Boolean m_PushBlockers;
    public System.Single m_MaxSpeed;
    public System.Single m_CanChangeLane;
    public Unity.Mathematics.float3 m_CurrentPosition;
    public System.Single m_Oncoming;
    public Unity.Entities.Entity m_Blocker;
    public Game.Vehicles.BlockerType m_BlockerType;
    private Unity.Entities.Entity m_Lane;
    private Unity.Entities.Entity m_NextLane;
    private Game.Net.Curve m_Curve;
    private Unity.Mathematics.float2 m_CurveOffset;
    private Unity.Mathematics.float2 m_NextOffset;
    private Unity.Mathematics.float3 m_PrevPosition;
    private System.Single m_PrevDistance;
    private System.Single m_Distance;

    private System.Void CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean inverse);
    private System.Void CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean inverse, System.Single& canUseLane);
    private System.Void CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset, System.Int32 yieldOverride, System.Single speedLimit, System.Boolean isRoundabout, System.Boolean inverse, System.Boolean requestSpace);
    private System.Boolean CheckOverlapSpace(Unity.Entities.Entity currentLane, Unity.Mathematics.float2 curCurvePos, Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextCurvePos, Unity.Mathematics.float2 overlapPos, Unity.Entities.Entity& blocker);
    private System.Void CheckParkingLane(System.Single distance);
    private System.Void CheckPedestrian(Colossal.Mathematics.Line3+Segment overlapLine, Unity.Entities.Entity obj, System.Single targetOffset, System.Single distanceOffset, System.Boolean giveSpace, System.Boolean inverse);
    private System.Boolean CheckSpace(Unity.Entities.Entity currentLane, Unity.Mathematics.float2 curveOffset, Unity.Collections.NativeArray<Game.Vehicles.CarNavigationLane> nextLanes, Unity.Entities.Entity& blocker);
    private System.Single GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset);
    public System.Boolean IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float3 curveOffset, Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextOffset, System.Single laneOffset, System.Boolean requestSpace, Game.Net.CarLaneFlags& laneFlags);
    public System.Boolean IterateFirstLane(Unity.Entities.Entity lane1, Unity.Entities.Entity lane2, Unity.Mathematics.float3 curveOffset, Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextOffset, System.Single laneDelta, System.Single laneOffset1, System.Single laneOffset2, System.Boolean requestSpace, Game.Net.CarLaneFlags& laneFlags);
    public System.Boolean IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset, Unity.Collections.NativeArray<Game.Vehicles.CarNavigationLane> nextLanes, System.Boolean requestSpace, Game.Net.CarLaneFlags& laneFlags, System.Boolean& needSignal);
    public System.Void IterateTarget(Unity.Mathematics.float3 targetPosition);
    public System.Void IterateTarget(Unity.Mathematics.float3 targetPosition, System.Single maxLaneSpeed);
    private System.Void UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset, System.Boolean ignore, System.Boolean inverse1, System.Boolean inverse2, Unity.Mathematics.float3 currentPos);
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

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneCondition> m_LaneConditionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneCondition> m_LaneConditionData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.ParkingLane> m_ParkingLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.ParkingLane> m_ParkingLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Unspawned> m_UnspawnedData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Unspawned> m_UnspawnedData;
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

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ParkingLaneData> m_PrefabParkingLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ParkingLaneData> m_PrefabParkingLaneData;
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

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_TempBuffer`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_TempBuffer;
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

- `public System.Single m_DistanceOffset`  

```csharp
public System.Single m_DistanceOffset;
```

- `public System.Single m_SpeedLimitFactor`  

```csharp
public System.Single m_SpeedLimitFactor;
```

- `public System.Single m_CurrentSpeed`  

```csharp
public System.Single m_CurrentSpeed;
```

- `public Game.Prefabs.CarData m_PrefabCar`  

```csharp
public Game.Prefabs.CarData m_PrefabCar;
```

- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  

```csharp
public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
```

- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_SpeedRange;
```

- `public System.Boolean m_PushBlockers`  

```csharp
public System.Boolean m_PushBlockers;
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

- `public System.Single m_Oncoming`  

```csharp
public System.Single m_Oncoming;
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

- `private Unity.Entities.Entity m_NextLane`  

```csharp
private Unity.Entities.Entity m_NextLane;
```

- `private Game.Net.Curve m_Curve`  

```csharp
private Game.Net.Curve m_Curve;
```

- `private Unity.Mathematics.float2 m_CurveOffset`  

```csharp
private Unity.Mathematics.float2 m_CurveOffset;
```

- `private Unity.Mathematics.float2 m_NextOffset`  

```csharp
private Unity.Mathematics.float2 m_NextOffset;
```

- `private Unity.Mathematics.float3 m_PrevPosition`  

```csharp
private Unity.Mathematics.float3 m_PrevPosition;
```

- `private System.Single m_PrevDistance`  

```csharp
private System.Single m_PrevDistance;
```

- `private System.Single m_Distance`  

```csharp
private System.Single m_Distance;
```


## Methods

- `private CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean inverse) : System.Void`  

```csharp
private void CheckCurrentLane(float distance, float2 minOffset, bool inverse, ref float canUseLane)
	{
		if (!m_LaneObjectData.TryGetBuffer(m_Lane, out var bufferData) || bufferData.Length == 0)
		{
			return;
		}
		distance -= 0.9f;
		for (int i = 0; i < bufferData.Length; i++)
		{
			LaneObject laneObject = bufferData[i];
			if (laneObject.m_LaneObject == m_Entity || (m_ControllerData.TryGetComponent(laneObject.m_LaneObject, out var componentData) && componentData.m_Controller == m_Entity))
			{
				continue;
			}
			float2 curvePosition = laneObject.m_CurvePosition;
			bool flag = curvePosition.y < curvePosition.x;
			bool flag2 = false;
			if (inverse ? ((!flag) ? (curvePosition.x >= minOffset.x) : (curvePosition.y >= minOffset.y && (curvePosition.y > 0f || curvePosition.x >= minOffset.x))) : ((!flag) ? (curvePosition.y <= minOffset.y && (curvePosition.y < 1f || curvePosition.x <= minOffset.x)) : (curvePosition.x <= minOffset.x)))
			{
				PrefabRef prefabRef = m_PrefabRefData[laneObject.m_LaneObject];
				float num = 0f;
				if (m_PrefabObjectGeometryData.TryGetComponent(prefabRef.m_Prefab, out var componentData2))
				{
					num = 0f - componentData2.m_Bounds.max.z;
				}
				if ((curvePosition.x - minOffset.x) * m_Curve.m_Length > num)
				{
					canUseLane = 0f;
				}
			}
			else
			{
				float objectSpeed = GetObjectSpeed(laneObject.m_LaneObject, curvePosition.x);
				objectSpeed = math.select(objectSpeed, 0f - objectSpeed, inverse);
				BlockerType blockerType = ((inverse == flag) ? BlockerType.Continuing : BlockerType.Oncoming);
				UpdateMaxSpeed(laneObject.m_LaneObject, blockerType, objectSpeed, curvePosition.x, 1f, distance, laneObject.m_LaneObject == m_Ignore, inverse, flag, m_CurrentPosition);
			}
		}
	}
```

- `private CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean inverse, System.Single& canUseLane) : System.Void`  

```csharp
private void CheckCurrentLane(float distance, float2 minOffset, bool inverse, ref float canUseLane)
	{
		if (!m_LaneObjectData.TryGetBuffer(m_Lane, out var bufferData) || bufferData.Length == 0)
		{
			return;
		}
		distance -= 0.9f;
		for (int i = 0; i < bufferData.Length; i++)
		{
			LaneObject laneObject = bufferData[i];
			if (laneObject.m_LaneObject == m_Entity || (m_ControllerData.TryGetComponent(laneObject.m_LaneObject, out var componentData) && componentData.m_Controller == m_Entity))
			{
				continue;
			}
			float2 curvePosition = laneObject.m_CurvePosition;
			bool flag = curvePosition.y < curvePosition.x;
			bool flag2 = false;
			if (inverse ? ((!flag) ? (curvePosition.x >= minOffset.x) : (curvePosition.y >= minOffset.y && (curvePosition.y > 0f || curvePosition.x >= minOffset.x))) : ((!flag) ? (curvePosition.y <= minOffset.y && (curvePosition.y < 1f || curvePosition.x <= minOffset.x)) : (curvePosition.x <= minOffset.x)))
			{
				PrefabRef prefabRef = m_PrefabRefData[laneObject.m_LaneObject];
				float num = 0f;
				if (m_PrefabObjectGeometryData.TryGetComponent(prefabRef.m_Prefab, out var componentData2))
				{
					num = 0f - componentData2.m_Bounds.max.z;
				}
				if ((curvePosition.x - minOffset.x) * m_Curve.m_Length > num)
				{
					canUseLane = 0f;
				}
			}
			else
			{
				float objectSpeed = GetObjectSpeed(laneObject.m_LaneObject, curvePosition.x);
				objectSpeed = math.select(objectSpeed, 0f - objectSpeed, inverse);
				BlockerType blockerType = ((inverse == flag) ? BlockerType.Continuing : BlockerType.Oncoming);
				UpdateMaxSpeed(laneObject.m_LaneObject, blockerType, objectSpeed, curvePosition.x, 1f, distance, laneObject.m_LaneObject == m_Ignore, inverse, flag, m_CurrentPosition);
			}
		}
	}
```

- `private CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset, System.Int32 yieldOverride, System.Single speedLimit, System.Boolean isRoundabout, System.Boolean inverse, System.Boolean requestSpace) : System.Void`  

```csharp
private void CheckOverlappingLanes(float origDistance, float origMinOffset, int yieldOverride, float speedLimit, bool isRoundabout, bool inverse, bool requestSpace)
	{
		if (!m_LaneOverlapData.TryGetBuffer(m_Lane, out var bufferData) || bufferData.Length == 0)
		{
			return;
		}
		origDistance -= 0.9f;
		Entity lane = m_Lane;
		Bezier4x3 bezier = m_Curve.m_Bezier;
		float2 curveOffset = m_CurveOffset;
		float length = m_Curve.m_Length;
		float x = 1f;
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
			if (inverse)
			{
				if (@float.x >= curveOffset.x)
				{
					continue;
				}
			}
			else if (@float.y <= curveOffset.x)
			{
				continue;
			}
			m_Lane = laneOverlap.m_Other;
			m_Curve = m_CurveData[m_Lane];
			m_CurveOffset = math.select(@float.zw, @float.wz, inverse);
			Line3.Segment overlapLine = MathUtils.Line(bezier, @float.xy);
			float num2;
			OverlapFlags overlapFlags;
			OverlapFlags overlapFlags2;
			if (inverse)
			{
				num2 = math.max(0f, @float.y - origMinOffset);
				overlapFlags = OverlapFlags.MergeEnd | OverlapFlags.MergeMiddleEnd;
				overlapFlags2 = OverlapFlags.MergeStart | OverlapFlags.MergeMiddleStart;
			}
			else
			{
				num2 = math.max(0f, origMinOffset - @float.x);
				overlapFlags = OverlapFlags.MergeStart | OverlapFlags.MergeMiddleStart;
				overlapFlags2 = OverlapFlags.MergeEnd | OverlapFlags.MergeMiddleEnd;
			}
			if (isRoundabout && laneOverlap.m_PriorityDelta > 0 && (laneOverlap.m_Flags & OverlapFlags.Road) != 0 && @float.x >= curveOffset.x)
			{
				x = (@float.x = math.min(x, @float.x));
			}
			float num3 = origDistance + length * math.select(@float.x - curveOffset.x, curveOffset.x - @float.y, inverse);
			float distanceFactor = (float)(int)laneOverlap.m_Parallelism * (1f / 128f);
			bool flag = VehicleUtils.GetBrakingDistance(m_PrefabCar, m_CurrentSpeed, m_TimeStep) <= num3;
			int num4 = num;
			BlockerType blockerType = (((laneOverlap.m_Flags & overlapFlags2) != 0) ? BlockerType.Continuing : BlockerType.Crossing);
			if ((laneOverlap.m_Flags & overlapFlags) == 0)
			{
				if (inverse ? (@float.y >= origMinOffset) : (@float.x <= origMinOffset))
				{
					if (isRoundabout)
					{
						if (!m_TempBuffer.IsCreated)
						{
							m_TempBuffer = new NativeList<Entity>(16, Allocator.Temp);
						}
						m_TempBuffer.Add(in m_Lane);
					}
				}
				else
				{
					if (isRoundabout && m_TempBuffer.IsCreated)
					{
						int num5 = 0;
						while (num5 < m_TempBuffer.Length)
						{
							if (!(m_TempBuffer[num5] == m_Lane))
							{
								num5++;
								continue;
							}
							goto IL_04e8;
						}
					}
					int num6 = yieldOverride;
					if (m_LaneSignalData.TryGetComponent(m_Lane, out var componentData2))
					{
						switch (componentData2.m_Signal)
						{
						case LaneSignalType.Stop:
							num6++;
							break;
						case LaneSignalType.Yield:
							num6--;
							break;
						}
					}
					int num7 = math.select(laneOverlap.m_PriorityDelta, num6, num6 != 0);
					num7 = math.select(num7, 0, requestSpace && num7 > 0);
					num4 -= num7;
					if (m_LaneReservationData.TryGetComponent(m_Lane, out componentData))
					{
						float offset = componentData.GetOffset();
						float num8 = math.select(math.max(num2 + @float.z, m_CurveOffset.x), 0f, inverse);
						int priority2 = componentData.GetPriority();
						if (offset > num8 || priority2 > num4)
						{
							float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, num3, m_SafeTimeStep);
							maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
							if (maxBrakingSpeed < m_MaxSpeed)
							{
								m_MaxSpeed = maxBrakingSpeed;
								m_Blocker = Entity.Null;
								m_BlockerType = blockerType;
							}
						}
						else if (math.select(math.select(laneOverlap.m_PriorityDelta, yieldOverride, num6 != 0), 1, (laneOverlap.m_Flags & OverlapFlags.Slow) != 0) > 0)
						{
							float maxBrakingSpeed2 = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, num3, m_SafeTimeStep);
							if (maxBrakingSpeed2 >= speedLimit * 0.5f && maxBrakingSpeed2 < m_MaxSpeed)
							{
								m_MaxSpeed = maxBrakingSpeed2;
								m_Blocker = Entity.Null;
								m_BlockerType = blockerType;
							}
						}
						if (flag && priority2 == 96 && !CheckOverlapSpace(lane, curveOffset, m_NextLane, m_NextOffset, @float.xy, out var blocker))
						{
							float maxBrakingSpeed3 = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, num3, m_SafeTimeStep);
							if (maxBrakingSpeed3 < m_MaxSpeed)
							{
								m_MaxSpeed = maxBrakingSpeed3;
								m_Blocker = blocker;
								m_BlockerType = blockerType;
							}
						}
					}
				}
			}
			goto IL_04e8;
			IL_04e8:
			if (!m_LaneObjectData.TryGetBuffer(m_Lane, out var bufferData2) || bufferData2.Length == 0)
			{
				continue;
			}
			int num9 = 100;
			bool giveSpace = flag && num9 > num4;
			for (int j = 0; j < bufferData2.Length; j++)
			{
				LaneObject laneObject = bufferData2[j];
				if (laneObject.m_LaneObject == m_Entity)
				{
					continue;
				}
				Entity entity = laneObject.m_LaneObject;
				if (m_ControllerData.TryGetComponent(laneObject.m_LaneObject, out var componentData3))
				{
					if (componentData3.m_Controller == m_Entity)
					{
						continue;
					}
					entity = componentData3.m_Controller;
				}
				if (m_CreatureData.HasComponent(laneObject.m_LaneObject))
				{
					CheckPedestrian(overlapLine, laneObject.m_LaneObject, laneObject.m_CurvePosition.y, num3, giveSpace, inverse);
					continue;
				}
				float2 curvePosition = laneObject.m_CurvePosition;
				bool flag2 = curvePosition.y < curvePosition.x;
				float objectSpeed = GetObjectSpeed(laneObject.m_LaneObject, curvePosition.x);
				if ((laneOverlap.m_Flags & overlapFlags) == 0 && ((inverse ? (@float.y <= origMinOffset) : (@float.x >= origMinOffset)) | (flag2 ? (curvePosition.y < @float.w) : (curvePosition.y > @float.z))))
				{
					int num10;
					if (m_CarData.TryGetComponent(entity, out var componentData4))
					{
						num10 = VehicleUtils.GetPriority(componentData4);
					}
					else if (m_TrainData.HasComponent(laneObject.m_LaneObject))
					{
						PrefabRef prefabRef = m_PrefabRefData[laneObject.m_LaneObject];
						num10 = VehicleUtils.GetPriority(m_PrefabTrainData[prefabRef.m_Prefab]);
					}
					else
					{
						num10 = 0;
					}
					if (num10 - num4 > 0)
					{
						curvePosition.y += objectSpeed * 2f / math.max(1f, m_Curve.m_Length);
					}
				}
				if (flag2)
				{
					if (curvePosition.y >= @float.w - num2)
					{
						continue;
					}
				}
				else if (curvePosition.y <= @float.z + num2)
				{
					continue;
				}
				objectSpeed = math.select(objectSpeed, 0f - objectSpeed, inverse);
				float3 currentPos = MathUtils.Position(m_Curve.m_Bezier, math.select(m_CurveOffset.x, m_CurveOffset.y, flag2 != inverse));
				UpdateMaxSpeed(laneObject.m_LaneObject, blockerType, objectSpeed, curvePosition.x, distanceFactor, num3, laneObject.m_LaneObject == m_Ignore, inverse, flag2, currentPos);
			}
		}
	}
```

- `private CheckOverlapSpace(Unity.Entities.Entity currentLane, Unity.Mathematics.float2 curCurvePos, Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextCurvePos, Unity.Mathematics.float2 overlapPos, Unity.Entities.Entity& blocker) : System.Boolean`  

```csharp
private bool CheckOverlapSpace(Entity currentLane, float2 curCurvePos, Entity nextLane, float2 nextCurvePos, float2 overlapPos, out Entity blocker)
	{
		blocker = Entity.Null;
		Entity entity = Entity.Null;
		Curve curve = m_CurveData[currentLane];
		float num = curve.m_Length * (1f - curCurvePos.x);
		float num2 = MathUtils.Size(m_PrefabObjectGeometry.m_Bounds.z);
		float num3 = num2;
		if (m_LaneObjectData.TryGetBuffer(currentLane, out var bufferData))
		{
			for (int i = 0; i < bufferData.Length; i++)
			{
				LaneObject laneObject = bufferData[i];
				if (laneObject.m_CurvePosition.x < curCurvePos.x || laneObject.m_LaneObject == m_Entity || (m_ControllerData.TryGetComponent(laneObject.m_LaneObject, out var componentData) && componentData.m_Controller == m_Entity))
				{
					continue;
				}
				if (m_MovingData.HasComponent(laneObject.m_LaneObject))
				{
					PrefabRef prefabRef = m_PrefabRefData[laneObject.m_LaneObject];
					if (m_PrefabObjectGeometryData.TryGetComponent(prefabRef.m_Prefab, out var componentData2))
					{
						num3 += MathUtils.Size(componentData2.m_Bounds.z) + 1f;
						blocker = laneObject.m_LaneObject;
					}
				}
				if (laneObject.m_CurvePosition.y >= overlapPos.y)
				{
					entity = laneObject.m_LaneObject;
					break;
				}
			}
		}
		if (entity == Entity.Null && m_CarLaneData.HasComponent(nextLane))
		{
			num += m_CurveData[nextLane].m_Length;
			if (m_LaneObjectData.TryGetBuffer(nextLane, out bufferData))
			{
				for (int j = 0; j < bufferData.Length; j++)
				{
					LaneObject laneObject2 = bufferData[j];
					if (!(laneObject2.m_CurvePosition.x < nextCurvePos.x) && !(laneObject2.m_LaneObject == m_Entity) && (!m_ControllerData.TryGetComponent(laneObject2.m_LaneObject, out var componentData3) || !(componentData3.m_Controller == m_Entity)))
					{
						entity = laneObject2.m_LaneObject;
						break;
					}
				}
			}
		}
		num = math.max(num, num2);
		if (entity != Entity.Null)
		{
			if (m_MovingData.TryGetComponent(entity, out var componentData4))
			{
				PrefabRef prefabRef2 = m_PrefabRefData[entity];
				float num4 = 0f;
				bool flag = false;
				ObjectGeometryData componentData6;
				if (m_PrefabTrainData.TryGetComponent(prefabRef2.m_Prefab, out var componentData5))
				{
					Train train = m_TrainData[entity];
					float2 @float = componentData5.m_AttachOffsets - componentData5.m_BogieOffsets;
					num4 = math.select(@float.y, @float.x, (train.m_Flags & Game.Vehicles.TrainFlags.Reversed) != 0);
					flag = true;
				}
				else if (m_PrefabObjectGeometryData.TryGetComponent(prefabRef2.m_Prefab, out componentData6))
				{
					num4 = 0f - componentData6.m_Bounds.min.z;
				}
				Transform transform = m_TransformData[entity];
				float3 y = math.normalizesafe(MathUtils.Tangent(curve.m_Bezier, overlapPos.y));
				num = math.dot(transform.m_Position - MathUtils.Position(curve.m_Bezier, overlapPos.y), y) - num4;
				float num5 = math.dot(componentData4.m_Velocity, y);
				if (num5 > 0.001f)
				{
					if (m_PrefabCarData.TryGetComponent(prefabRef2.m_Prefab, out var componentData7))
					{
						num += VehicleUtils.GetBrakingDistance(componentData7, num5, m_SafeTimeStep);
					}
					else if (flag)
					{
						num += VehicleUtils.GetBrakingDistance(componentData5, num5, m_SafeTimeStep);
					}
				}
			}
			blocker = entity;
		}
		if (num >= num3)
		{
			blocker = Entity.Null;
			return true;
		}
		return false;
	}
```

- `private CheckParkingLane(System.Single distance) : System.Void`  

```csharp
private void CheckParkingLane(float distance)
	{
		if (!m_LaneObjectData.TryGetBuffer(m_Lane, out var bufferData) || bufferData.Length == 0)
		{
			return;
		}
		PrefabRef prefabRef = m_PrefabRefData[m_Lane];
		ParkingLaneData parkingLaneData = m_PrefabParkingLaneData[prefabRef.m_Prefab];
		float3 x = MathUtils.Position(m_Curve.m_Bezier, m_CurveOffset.x);
		float2 @float;
		if (parkingLaneData.m_SlotInterval == 0f)
		{
			@float = VehicleUtils.GetParkingSize(m_PrefabObjectGeometry, out var offset).y * 0.5f;
			@float.x += 0.9f + offset;
			@float.y += 0.9f - offset;
		}
		else
		{
			@float = 0.1f;
		}
		for (int i = 0; i < bufferData.Length; i++)
		{
			LaneObject laneObject = bufferData[i];
			if (laneObject.m_LaneObject == m_Entity || (m_ControllerData.TryGetComponent(laneObject.m_LaneObject, out var componentData) && componentData.m_Controller == m_Entity) || m_UnspawnedData.HasComponent(laneObject.m_LaneObject))
			{
				continue;
			}
			bool test = laneObject.m_CurvePosition.y >= m_CurveOffset.x;
			float3 y = MathUtils.Position(m_Curve.m_Bezier, laneObject.m_CurvePosition.y);
			float num = math.select(@float.x, @float.y, test);
			if (parkingLaneData.m_SlotInterval == 0f)
			{
				float2 parkingOffsets = VehicleUtils.GetParkingOffsets(laneObject.m_LaneObject, ref m_PrefabRefData, ref m_PrefabObjectGeometryData);
				num += math.select(parkingOffsets.y, parkingOffsets.x, test);
			}
			if (math.distance(x, y) < num)
			{
				float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, distance, m_SafeTimeStep);
				maxBrakingSpeed = math.select(maxBrakingSpeed, 3f, laneObject.m_LaneObject == m_Ignore && maxBrakingSpeed < 1f);
				maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
				if (maxBrakingSpeed < m_MaxSpeed)
				{
					m_MaxSpeed = maxBrakingSpeed;
					m_Blocker = laneObject.m_LaneObject;
					m_BlockerType = BlockerType.Continuing;
				}
			}
		}
	}
```

- `private CheckPedestrian(Colossal.Mathematics.Line3+Segment overlapLine, Unity.Entities.Entity obj, System.Single targetOffset, System.Single distanceOffset, System.Boolean giveSpace, System.Boolean inverse) : System.Void`  

```csharp
private void CheckPedestrian(Line3.Segment overlapLine, Entity obj, float targetOffset, float distanceOffset, bool giveSpace, bool inverse)
	{
		float2 @float = math.select(m_CurveOffset, m_CurveOffset.yx, inverse);
		if ((targetOffset <= @float.x) | (targetOffset >= @float.y))
		{
			PrefabRef prefabRef = m_PrefabRefData[obj];
			Transform transform = m_TransformData[obj];
			float num = m_PrefabObjectGeometry.m_Size.x * 0.5f;
			if (m_PrefabObjectGeometryData.TryGetComponent(prefabRef.m_Prefab, out var componentData))
			{
				num += componentData.m_Size.z * 0.5f;
			}
			float t;
			float num2 = MathUtils.Distance(overlapLine.xz, transform.m_Position.xz, out t);
			float num3 = math.dot(math.forward(transform.m_Rotation).xz, math.normalizesafe(MathUtils.Position(overlapLine, t).xz - transform.m_Position.xz));
			if (num2 - math.select(math.min(0f - num3, 0f), math.max(num3, 0f), giveSpace) >= num)
			{
				return;
			}
		}
		float position = ((m_PushBlockers || !m_MovingData.TryGetComponent(obj, out var componentData2) || !(math.lengthsq(componentData2.m_Velocity) >= 0.01f)) ? math.max(3f, VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, distanceOffset, 3f, m_SafeTimeStep)) : VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, distanceOffset, m_SafeTimeStep));
		position = MathUtils.Clamp(position, m_SpeedRange);
		if (position < m_MaxSpeed)
		{
			m_MaxSpeed = position;
			m_Blocker = obj;
			m_BlockerType = BlockerType.Temporary;
		}
	}
```

- `private CheckSpace(Unity.Entities.Entity currentLane, Unity.Mathematics.float2 curveOffset, Unity.Collections.NativeArray<Game.Vehicles.CarNavigationLane> nextLanes, Unity.Entities.Entity& blocker) : System.Boolean`  

```csharp
private bool CheckSpace(Entity currentLane, float2 curveOffset, NativeArray<CarNavigationLane> nextLanes, out Entity blocker)
	{
		blocker = Entity.Null;
		if (nextLanes.Length == 0)
		{
			return true;
		}
		CarNavigationLane carNavigationLane = nextLanes[0];
		bool flag = carNavigationLane.m_CurvePosition.y < carNavigationLane.m_CurvePosition.x;
		if (carNavigationLane.m_CurvePosition.x != math.select(0f, 1f, flag) || !m_CarLaneData.TryGetComponent(carNavigationLane.m_Lane, out var componentData))
		{
			return true;
		}
		if ((componentData.m_Flags & (Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.Yield | Game.Net.CarLaneFlags.Stop | Game.Net.CarLaneFlags.UTurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight | Game.Net.CarLaneFlags.Forward | Game.Net.CarLaneFlags.Roundabout | Game.Net.CarLaneFlags.RightOfWay | Game.Net.CarLaneFlags.TrafficLights)) != 0 && (componentData.m_Flags & Game.Net.CarLaneFlags.Approach) == 0)
		{
			return true;
		}
		if (!m_LaneOverlapData.TryGetBuffer(currentLane, out var bufferData))
		{
			return true;
		}
		Curve curve = m_CurveData[carNavigationLane.m_Lane];
		bool num = curveOffset.y < curveOffset.x;
		bool flag2 = false;
		float num2 = float.MaxValue;
		float num3 = MathUtils.Size(m_PrefabObjectGeometry.m_Bounds.z);
		float num4 = num3;
		int num5 = 1;
		OverlapFlags overlapFlags = (num ? OverlapFlags.MergeStart : OverlapFlags.MergeEnd);
		float3 @float = math.normalizesafe(MathUtils.Tangent(curve.m_Bezier, carNavigationLane.m_CurvePosition.x));
		float3 float2 = MathUtils.Position(curve.m_Bezier, carNavigationLane.m_CurvePosition.x);
		@float = math.select(@float, -@float, flag);
		DynamicBuffer<LaneObject> bufferData2;
		for (int i = 0; i < bufferData.Length; i++)
		{
			LaneOverlap laneOverlap = bufferData[i];
			if ((laneOverlap.m_Flags & (OverlapFlags.MergeStart | OverlapFlags.MergeEnd | OverlapFlags.MergeMiddleStart | OverlapFlags.MergeMiddleEnd | OverlapFlags.Unsafe | OverlapFlags.Water)) == 0)
			{
				flag2 = true;
			}
			else
			{
				if ((laneOverlap.m_Flags & overlapFlags) == 0 || !(laneOverlap.m_Other != carNavigationLane.m_Lane) || !m_LaneObjectData.TryGetBuffer(laneOverlap.m_Other, out bufferData2) || bufferData2.Length == 0)
				{
					continue;
				}
				float2 float3 = new float2((int)laneOverlap.m_OtherStart, (int)laneOverlap.m_OtherEnd) * 0.003921569f;
				for (int j = 0; j < bufferData2.Length; j++)
				{
					LaneObject laneObject = bufferData2[j];
					if (laneObject.m_LaneObject == m_Entity)
					{
						continue;
					}
					Entity entity = laneObject.m_LaneObject;
					if (m_ControllerData.TryGetComponent(laneObject.m_LaneObject, out var componentData2))
					{
						if (componentData2.m_Controller == m_Entity)
						{
							continue;
						}
						entity = componentData2.m_Controller;
					}
					float2 curvePosition = laneObject.m_CurvePosition;
					if ((curvePosition.y < curvePosition.x) ? (curvePosition.y >= float3.y) : (curvePosition.y <= float3.x))
					{
						int num6;
						if (m_CarData.TryGetComponent(entity, out var componentData3))
						{
							num6 = VehicleUtils.GetPriority(componentData3);
						}
						else if (m_TrainData.HasComponent(laneObject.m_LaneObject))
						{
							PrefabRef prefabRef = m_PrefabRefData[laneObject.m_LaneObject];
							num6 = VehicleUtils.GetPriority(m_PrefabTrainData[prefabRef.m_Prefab]);
						}
						else
						{
							num6 = 0;
						}
						if (num6 < m_Priority)
						{
							continue;
						}
					}
					if (!m_MovingData.TryGetComponent(laneObject.m_LaneObject, out var componentData4))
					{
						continue;
					}
					PrefabRef prefabRef2 = m_PrefabRefData[laneObject.m_LaneObject];
					if (!m_PrefabObjectGeometryData.TryGetComponent(prefabRef2.m_Prefab, out var componentData5))
					{
						continue;
					}
					num4 += MathUtils.Size(componentData5.m_Bounds.z) + 1f;
					num5++;
					blocker = laneObject.m_LaneObject;
					if (!(num2 >= num3))
					{
						continue;
					}
					float num7 = 0f - componentData5.m_Bounds.min.z;
					bool flag3 = false;
					if (m_PrefabTrainData.TryGetComponent(prefabRef2.m_Prefab, out var componentData6))
					{
						Train train = m_TrainData[laneObject.m_LaneObject];
						float2 float4 = componentData6.m_AttachOffsets - componentData6.m_BogieOffsets;
						num7 = math.select(float4.y, float4.x, (train.m_Flags & Game.Vehicles.TrainFlags.Reversed) != 0);
						flag3 = true;
					}
					num2 = math.dot(m_TransformData[laneObject.m_LaneObject].m_Position - float2, @float) - num7;
					float num8 = math.dot(componentData4.m_Velocity, @float);
					if (num8 > 0.001f)
					{
						if (m_PrefabCarData.TryGetComponent(prefabRef2.m_Prefab, out var componentData7))
						{
							num2 += VehicleUtils.GetBrakingDistance(componentData7, num8, m_SafeTimeStep);
						}
						else if (flag3)
						{
							num2 += VehicleUtils.GetBrakingDistance(componentData6, num8, m_SafeTimeStep);
						}
					}
				}
			}
		}
		if (!flag2)
		{
			return true;
		}
		if (m_LaneObjectData.TryGetBuffer(currentLane, out bufferData2))
		{
			for (int k = 0; k < bufferData2.Length; k++)
			{
				LaneObject laneObject2 = bufferData2[k];
				if (laneObject2.m_LaneObject == m_Entity || (m_ControllerData.TryGetComponent(laneObject2.m_LaneObject, out var componentData8) && componentData8.m_Controller == m_Entity) || !m_MovingData.TryGetComponent(laneObject2.m_LaneObject, out var componentData9))
				{
					continue;
				}
				PrefabRef prefabRef3 = m_PrefabRefData[laneObject2.m_LaneObject];
				if (!m_PrefabObjectGeometryData.TryGetComponent(prefabRef3.m_Prefab, out var componentData10))
				{
					continue;
				}
				num4 += MathUtils.Size(componentData10.m_Bounds.z) + 1f;
				num5++;
				blocker = laneObject2.m_LaneObject;
				if (!(num2 >= num3))
				{
					continue;
				}
				float num9 = 0f - componentData10.m_Bounds.min.z;
				bool flag4 = false;
				if (m_PrefabTrainData.TryGetComponent(prefabRef3.m_Prefab, out var componentData11))
				{
					Train train2 = m_TrainData[laneObject2.m_LaneObject];
					float2 float5 = componentData11.m_AttachOffsets - componentData11.m_BogieOffsets;
					num9 = math.select(float5.y, float5.x, (train2.m_Flags & Game.Vehicles.TrainFlags.Reversed) != 0);
					flag4 = true;
				}
				num2 = math.dot(m_TransformData[laneObject2.m_LaneObject].m_Position - float2, @float) - num9;
				float num10 = math.dot(componentData9.m_Velocity, @float);
				if (num10 > 0.001f)
				{
					if (m_PrefabCarData.TryGetComponent(prefabRef3.m_Prefab, out var componentData12))
					{
						num2 += VehicleUtils.GetBrakingDistance(componentData12, num10, m_SafeTimeStep);
					}
					else if (flag4)
					{
						num2 += VehicleUtils.GetBrakingDistance(componentData11, num10, m_SafeTimeStep);
					}
				}
			}
		}
		if (num2 != float.MaxValue && num2 >= num3)
		{
			blocker = Entity.Null;
			return true;
		}
		num2 = 0f;
		int num11 = 1;
		while (true)
		{
			if (m_LaneObjectData.TryGetBuffer(carNavigationLane.m_Lane, out bufferData2))
			{
				for (int l = 0; l < bufferData2.Length; l++)
				{
					LaneObject laneObject3 = bufferData2[math.select(l, bufferData2.Length - 1 - l, flag)];
					bool flag5 = laneObject3.m_CurvePosition.y < laneObject3.m_CurvePosition.x;
					if (flag != flag5)
					{
						continue;
					}
					if (flag)
					{
						if (laneObject3.m_CurvePosition.x > carNavigationLane.m_CurvePosition.x)
						{
							continue;
						}
					}
					else if (laneObject3.m_CurvePosition.x < carNavigationLane.m_CurvePosition.x)
					{
						continue;
					}
					if (laneObject3.m_LaneObject == m_Entity || (m_ControllerData.TryGetComponent(laneObject3.m_LaneObject, out var componentData13) && componentData13.m_Controller == m_Entity) || !m_MovingData.TryGetComponent(laneObject3.m_LaneObject, out var componentData14))
					{
						continue;
					}
					PrefabRef prefabRef4 = m_PrefabRefData[laneObject3.m_LaneObject];
					m_PrefabObjectGeometryData.TryGetComponent(prefabRef4.m_Prefab, out var componentData15);
					float num12 = 0f - componentData15.m_Bounds.min.z;
					bool flag6 = false;
					if (m_PrefabTrainData.TryGetComponent(prefabRef4.m_Prefab, out var componentData16))
					{
						Train train3 = m_TrainData[laneObject3.m_LaneObject];
						float2 float6 = componentData16.m_AttachOffsets - componentData16.m_BogieOffsets;
						num12 = math.select(float6.y, float6.x, (train3.m_Flags & Game.Vehicles.TrainFlags.Reversed) != 0);
						flag6 = true;
					}
					float num13 = num2 + math.dot(m_TransformData[laneObject3.m_LaneObject].m_Position - float2, @float) - num12;
					float num14 = math.dot(componentData14.m_Velocity, @float);
					if (num14 > 0.001f)
					{
						if (m_PrefabCarData.TryGetComponent(prefabRef4.m_Prefab, out var componentData17))
						{
							num13 += VehicleUtils.GetBrakingDistance(componentData17, num14, m_SafeTimeStep);
						}
						else if (flag6)
						{
							num13 += VehicleUtils.GetBrakingDistance(componentData16, num14, m_SafeTimeStep);
						}
					}
					if (num13 >= num4)
					{
						blocker = Entity.Null;
						return true;
					}
					blocker = laneObject3.m_LaneObject;
					if (--num5 == 0)
					{
						return false;
					}
					num4 += MathUtils.Size(componentData15.m_Bounds.z) + 1f;
				}
			}
			num2 += curve.m_Length;
			if (math.max(num2, num3) >= num4)
			{
				blocker = Entity.Null;
				return true;
			}
			if (num11 >= nextLanes.Length)
			{
				return false;
			}
			carNavigationLane = nextLanes[num11++];
			flag = carNavigationLane.m_CurvePosition.y < carNavigationLane.m_CurvePosition.x;
			if (carNavigationLane.m_CurvePosition.x != math.select(0f, 1f, flag) || !m_CarLaneData.TryGetComponent(carNavigationLane.m_Lane, out componentData))
			{
				return false;
			}
			if ((componentData.m_Flags & (Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.Yield | Game.Net.CarLaneFlags.Stop | Game.Net.CarLaneFlags.UTurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight | Game.Net.CarLaneFlags.Forward | Game.Net.CarLaneFlags.Roundabout | Game.Net.CarLaneFlags.RightOfWay | Game.Net.CarLaneFlags.TrafficLights)) != 0 && (componentData.m_Flags & Game.Net.CarLaneFlags.Approach) == 0)
			{
				break;
			}
			curve = m_CurveData[carNavigationLane.m_Lane];
			@float = math.normalizesafe(MathUtils.Tangent(curve.m_Bezier, carNavigationLane.m_CurvePosition.x));
			float2 = MathUtils.Position(curve.m_Bezier, carNavigationLane.m_CurvePosition.x);
			@float = math.select(@float, -@float, flag);
		}
		return false;
	}
```

- `private GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset) : System.Single`  

```csharp
private float GetObjectSpeed(Entity obj, float curveOffset)
	{
		if (!m_MovingData.TryGetComponent(obj, out var componentData))
		{
			return 0f;
		}
		float3 y = math.normalizesafe(MathUtils.Tangent(m_Curve.m_Bezier, curveOffset));
		return math.dot(componentData.m_Velocity, y);
	}
```

- `public IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float3 curveOffset, Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextOffset, System.Single laneOffset, System.Boolean requestSpace, Game.Net.CarLaneFlags& laneFlags) : System.Boolean`  

```csharp
public bool IterateFirstLane(Entity lane1, Entity lane2, float3 curveOffset, Entity nextLane, float2 nextOffset, float laneDelta, float laneOffset1, float laneOffset2, bool requestSpace, out Game.Net.CarLaneFlags laneFlags)
	{
		laneDelta = math.saturate(laneDelta);
		laneFlags = ~(Game.Net.CarLaneFlags.Unsafe | Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.Invert | Game.Net.CarLaneFlags.SideConnection | Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.Twoway | Game.Net.CarLaneFlags.IsSecured | Game.Net.CarLaneFlags.Runway | Game.Net.CarLaneFlags.Yield | Game.Net.CarLaneFlags.Stop | Game.Net.CarLaneFlags.ForbidCombustionEngines | Game.Net.CarLaneFlags.ForbidTransitTraffic | Game.Net.CarLaneFlags.ForbidHeavyTraffic | Game.Net.CarLaneFlags.PublicOnly | Game.Net.CarLaneFlags.Highway | Game.Net.CarLaneFlags.UTurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight | Game.Net.CarLaneFlags.Forward | Game.Net.CarLaneFlags.Approach | Game.Net.CarLaneFlags.Roundabout | Game.Net.CarLaneFlags.RightLimit | Game.Net.CarLaneFlags.LeftLimit | Game.Net.CarLaneFlags.ForbidPassing | Game.Net.CarLaneFlags.RightOfWay | Game.Net.CarLaneFlags.TrafficLights | Game.Net.CarLaneFlags.ParkingLeft | Game.Net.CarLaneFlags.ParkingRight | Game.Net.CarLaneFlags.Forbidden | Game.Net.CarLaneFlags.AllowEnter);
		Curve curve = m_CurveData[lane1];
		Curve curve2 = m_CurveData[lane2];
		float3 @float = MathUtils.Position(curve.m_Bezier, curveOffset.x);
		float3 float2 = MathUtils.Position(curve2.m_Bezier, curveOffset.x);
		float3 x = math.lerp(@float, float2, laneDelta);
		float3 lanePosition = VehicleUtils.GetLanePosition(curve.m_Bezier, curveOffset.x, laneOffset1);
		float3 lanePosition2 = VehicleUtils.GetLanePosition(curve2.m_Bezier, curveOffset.x, laneOffset2);
		float3 y = math.lerp(lanePosition, lanePosition2, laneDelta);
		m_PrevPosition = m_CurrentPosition;
		m_Distance = math.distance(m_CurrentPosition, y);
		if (m_CarLaneData.TryGetComponent(lane1, out var componentData))
		{
			componentData.m_SpeedLimit *= m_SpeedLimitFactor;
			laneFlags = componentData.m_Flags;
			float driveSpeed = VehicleUtils.GetMaxDriveSpeed(m_PrefabCar, componentData);
			int yieldOverride = 0;
			bool isRoundabout = false;
			bool flag = curveOffset.z < curveOffset.x;
			if ((componentData.m_Flags & Game.Net.CarLaneFlags.Approach) == 0)
			{
				isRoundabout = (componentData.m_Flags & Game.Net.CarLaneFlags.Roundabout) != 0;
				if ((componentData.m_Flags & (Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.TrafficLights)) != 0 && m_LaneSignalData.HasComponent(lane1))
				{
					switch (m_LaneSignalData[lane1].m_Signal)
					{
					case LaneSignalType.Stop:
						yieldOverride = -1;
						break;
					case LaneSignalType.Yield:
						yieldOverride = 1;
						break;
					}
				}
			}
			if (m_LaneConditionData.HasComponent(lane1))
			{
				VehicleUtils.ModifyDriveSpeed(ref driveSpeed, m_LaneConditionData[lane1]);
			}
			if (m_Priority < 102 && m_LaneReservationData.HasComponent(lane1) && m_LaneReservationData.HasComponent(lane2))
			{
				if (laneDelta < 0.9f)
				{
					LaneReservation laneReservation = m_LaneReservationData[lane1];
					LaneReservation laneReservation2 = m_LaneReservationData[lane2];
					if (math.any(new int2(laneReservation.GetPriority(), laneReservation2.GetPriority()) == 102))
					{
						driveSpeed *= 0.5f;
					}
				}
				else if (m_LaneReservationData[lane2].GetPriority() == 102)
				{
					driveSpeed *= 0.5f;
				}
			}
			if (driveSpeed < m_MaxSpeed)
			{
				m_MaxSpeed = MathUtils.Clamp(driveSpeed, m_SpeedRange);
				m_Blocker = Entity.Null;
				m_BlockerType = BlockerType.Limit;
			}
			float2 xy = curveOffset.xy;
			float num = 0f - m_PrefabObjectGeometry.m_Bounds.max.z;
			float num2 = m_Distance + num + m_DistanceOffset;
			if (componentData.m_CautionEnd >= componentData.m_CautionStart)
			{
				Bounds1 cautionBounds = componentData.cautionBounds;
				float2 float3 = math.select(curveOffset.xz, curveOffset.zx, flag);
				if (cautionBounds.max > float3.x && cautionBounds.min < float3.y)
				{
					float distance = num2 + curve.m_Length * math.max(0f, math.select(cautionBounds.min - float3.x, float3.y - cautionBounds.max, flag));
					float num3 = componentData.m_SpeedLimit * math.select(0.5f, 0.8f, (componentData.m_Flags & Game.Net.CarLaneFlags.IsSecured) != 0);
					driveSpeed = math.max(num3, VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, distance, num3, m_SafeTimeStep));
					if (driveSpeed < m_MaxSpeed)
					{
						m_MaxSpeed = MathUtils.Clamp(driveSpeed, m_SpeedRange);
						m_Blocker = Entity.Null;
						m_BlockerType = BlockerType.Caution;
					}
				}
			}
			if (laneDelta < 0.9f)
			{
				m_Lane = lane1;
				m_Curve = curve;
				m_CurveOffset = curveOffset.xz;
				m_CurrentPosition = @float;
				CheckCurrentLane(num2, xy, flag);
				CheckOverlappingLanes(num2, xy.y, yieldOverride, componentData.m_SpeedLimit, isRoundabout, flag, requestSpace);
			}
			m_Lane = lane2;
			m_NextLane = nextLane;
			m_Curve = curve2;
			m_CurveOffset = curveOffset.xz;
			m_NextOffset = nextOffset;
			m_CurrentPosition = float2;
			if (laneDelta == 0f)
			{
				CheckCurrentLane(num2, xy, flag, ref m_CanChangeLane);
			}
			else
			{
				CheckCurrentLane(num2, xy, flag);
			}
			CheckOverlappingLanes(num2, xy.y, 0, componentData.m_SpeedLimit, isRoundabout, flag, requestSpace);
		}
		float3 float4 = MathUtils.Position(curve2.m_Bezier, curveOffset.z);
		float num4 = math.lerp(curve.m_Length, curve2.m_Length, laneDelta);
		float num5 = math.abs(curveOffset.z - curveOffset.x);
		float num6 = math.max(0.001f, math.lerp(math.distance(x, float4), num4 * num5, num5));
		if (num6 > 1f)
		{
			m_PrevPosition = m_CurrentPosition;
			m_PrevDistance = m_Distance;
		}
		m_CurrentPosition = float4;
		m_Distance += num6;
		float brakingDistance = VehicleUtils.GetBrakingDistance(m_PrefabCar, m_MaxSpeed, m_SafeTimeStep);
		return (m_Distance + m_DistanceOffset - 20f >= brakingDistance) | (m_MaxSpeed == m_SpeedRange.min);
	}
```

- `public IterateFirstLane(Unity.Entities.Entity lane1, Unity.Entities.Entity lane2, Unity.Mathematics.float3 curveOffset, Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextOffset, System.Single laneDelta, System.Single laneOffset1, System.Single laneOffset2, System.Boolean requestSpace, Game.Net.CarLaneFlags& laneFlags) : System.Boolean`  

```csharp
public bool IterateFirstLane(Entity lane1, Entity lane2, float3 curveOffset, Entity nextLane, float2 nextOffset, float laneDelta, float laneOffset1, float laneOffset2, bool requestSpace, out Game.Net.CarLaneFlags laneFlags)
	{
		laneDelta = math.saturate(laneDelta);
		laneFlags = ~(Game.Net.CarLaneFlags.Unsafe | Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.Invert | Game.Net.CarLaneFlags.SideConnection | Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.Twoway | Game.Net.CarLaneFlags.IsSecured | Game.Net.CarLaneFlags.Runway | Game.Net.CarLaneFlags.Yield | Game.Net.CarLaneFlags.Stop | Game.Net.CarLaneFlags.ForbidCombustionEngines | Game.Net.CarLaneFlags.ForbidTransitTraffic | Game.Net.CarLaneFlags.ForbidHeavyTraffic | Game.Net.CarLaneFlags.PublicOnly | Game.Net.CarLaneFlags.Highway | Game.Net.CarLaneFlags.UTurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight | Game.Net.CarLaneFlags.Forward | Game.Net.CarLaneFlags.Approach | Game.Net.CarLaneFlags.Roundabout | Game.Net.CarLaneFlags.RightLimit | Game.Net.CarLaneFlags.LeftLimit | Game.Net.CarLaneFlags.ForbidPassing | Game.Net.CarLaneFlags.RightOfWay | Game.Net.CarLaneFlags.TrafficLights | Game.Net.CarLaneFlags.ParkingLeft | Game.Net.CarLaneFlags.ParkingRight | Game.Net.CarLaneFlags.Forbidden | Game.Net.CarLaneFlags.AllowEnter);
		Curve curve = m_CurveData[lane1];
		Curve curve2 = m_CurveData[lane2];
		float3 @float = MathUtils.Position(curve.m_Bezier, curveOffset.x);
		float3 float2 = MathUtils.Position(curve2.m_Bezier, curveOffset.x);
		float3 x = math.lerp(@float, float2, laneDelta);
		float3 lanePosition = VehicleUtils.GetLanePosition(curve.m_Bezier, curveOffset.x, laneOffset1);
		float3 lanePosition2 = VehicleUtils.GetLanePosition(curve2.m_Bezier, curveOffset.x, laneOffset2);
		float3 y = math.lerp(lanePosition, lanePosition2, laneDelta);
		m_PrevPosition = m_CurrentPosition;
		m_Distance = math.distance(m_CurrentPosition, y);
		if (m_CarLaneData.TryGetComponent(lane1, out var componentData))
		{
			componentData.m_SpeedLimit *= m_SpeedLimitFactor;
			laneFlags = componentData.m_Flags;
			float driveSpeed = VehicleUtils.GetMaxDriveSpeed(m_PrefabCar, componentData);
			int yieldOverride = 0;
			bool isRoundabout = false;
			bool flag = curveOffset.z < curveOffset.x;
			if ((componentData.m_Flags & Game.Net.CarLaneFlags.Approach) == 0)
			{
				isRoundabout = (componentData.m_Flags & Game.Net.CarLaneFlags.Roundabout) != 0;
				if ((componentData.m_Flags & (Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.TrafficLights)) != 0 && m_LaneSignalData.HasComponent(lane1))
				{
					switch (m_LaneSignalData[lane1].m_Signal)
					{
					case LaneSignalType.Stop:
						yieldOverride = -1;
						break;
					case LaneSignalType.Yield:
						yieldOverride = 1;
						break;
					}
				}
			}
			if (m_LaneConditionData.HasComponent(lane1))
			{
				VehicleUtils.ModifyDriveSpeed(ref driveSpeed, m_LaneConditionData[lane1]);
			}
			if (m_Priority < 102 && m_LaneReservationData.HasComponent(lane1) && m_LaneReservationData.HasComponent(lane2))
			{
				if (laneDelta < 0.9f)
				{
					LaneReservation laneReservation = m_LaneReservationData[lane1];
					LaneReservation laneReservation2 = m_LaneReservationData[lane2];
					if (math.any(new int2(laneReservation.GetPriority(), laneReservation2.GetPriority()) == 102))
					{
						driveSpeed *= 0.5f;
					}
				}
				else if (m_LaneReservationData[lane2].GetPriority() == 102)
				{
					driveSpeed *= 0.5f;
				}
			}
			if (driveSpeed < m_MaxSpeed)
			{
				m_MaxSpeed = MathUtils.Clamp(driveSpeed, m_SpeedRange);
				m_Blocker = Entity.Null;
				m_BlockerType = BlockerType.Limit;
			}
			float2 xy = curveOffset.xy;
			float num = 0f - m_PrefabObjectGeometry.m_Bounds.max.z;
			float num2 = m_Distance + num + m_DistanceOffset;
			if (componentData.m_CautionEnd >= componentData.m_CautionStart)
			{
				Bounds1 cautionBounds = componentData.cautionBounds;
				float2 float3 = math.select(curveOffset.xz, curveOffset.zx, flag);
				if (cautionBounds.max > float3.x && cautionBounds.min < float3.y)
				{
					float distance = num2 + curve.m_Length * math.max(0f, math.select(cautionBounds.min - float3.x, float3.y - cautionBounds.max, flag));
					float num3 = componentData.m_SpeedLimit * math.select(0.5f, 0.8f, (componentData.m_Flags & Game.Net.CarLaneFlags.IsSecured) != 0);
					driveSpeed = math.max(num3, VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, distance, num3, m_SafeTimeStep));
					if (driveSpeed < m_MaxSpeed)
					{
						m_MaxSpeed = MathUtils.Clamp(driveSpeed, m_SpeedRange);
						m_Blocker = Entity.Null;
						m_BlockerType = BlockerType.Caution;
					}
				}
			}
			if (laneDelta < 0.9f)
			{
				m_Lane = lane1;
				m_Curve = curve;
				m_CurveOffset = curveOffset.xz;
				m_CurrentPosition = @float;
				CheckCurrentLane(num2, xy, flag);
				CheckOverlappingLanes(num2, xy.y, yieldOverride, componentData.m_SpeedLimit, isRoundabout, flag, requestSpace);
			}
			m_Lane = lane2;
			m_NextLane = nextLane;
			m_Curve = curve2;
			m_CurveOffset = curveOffset.xz;
			m_NextOffset = nextOffset;
			m_CurrentPosition = float2;
			if (laneDelta == 0f)
			{
				CheckCurrentLane(num2, xy, flag, ref m_CanChangeLane);
			}
			else
			{
				CheckCurrentLane(num2, xy, flag);
			}
			CheckOverlappingLanes(num2, xy.y, 0, componentData.m_SpeedLimit, isRoundabout, flag, requestSpace);
		}
		float3 float4 = MathUtils.Position(curve2.m_Bezier, curveOffset.z);
		float num4 = math.lerp(curve.m_Length, curve2.m_Length, laneDelta);
		float num5 = math.abs(curveOffset.z - curveOffset.x);
		float num6 = math.max(0.001f, math.lerp(math.distance(x, float4), num4 * num5, num5));
		if (num6 > 1f)
		{
			m_PrevPosition = m_CurrentPosition;
			m_PrevDistance = m_Distance;
		}
		m_CurrentPosition = float4;
		m_Distance += num6;
		float brakingDistance = VehicleUtils.GetBrakingDistance(m_PrefabCar, m_MaxSpeed, m_SafeTimeStep);
		return (m_Distance + m_DistanceOffset - 20f >= brakingDistance) | (m_MaxSpeed == m_SpeedRange.min);
	}
```

- `public IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset, Unity.Collections.NativeArray<Game.Vehicles.CarNavigationLane> nextLanes, System.Boolean requestSpace, Game.Net.CarLaneFlags& laneFlags, System.Boolean& needSignal) : System.Boolean`  

```csharp
public bool IterateNextLane(Entity lane, float2 curveOffset, float minOffset, NativeArray<CarNavigationLane> nextLanes, bool requestSpace, ref Game.Net.CarLaneFlags laneFlags, out bool needSignal)
	{
		needSignal = false;
		Game.Net.CarLaneFlags carLaneFlags = laneFlags;
		laneFlags = ~(Game.Net.CarLaneFlags.Unsafe | Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.Invert | Game.Net.CarLaneFlags.SideConnection | Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.Twoway | Game.Net.CarLaneFlags.IsSecured | Game.Net.CarLaneFlags.Runway | Game.Net.CarLaneFlags.Yield | Game.Net.CarLaneFlags.Stop | Game.Net.CarLaneFlags.ForbidCombustionEngines | Game.Net.CarLaneFlags.ForbidTransitTraffic | Game.Net.CarLaneFlags.ForbidHeavyTraffic | Game.Net.CarLaneFlags.PublicOnly | Game.Net.CarLaneFlags.Highway | Game.Net.CarLaneFlags.UTurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight | Game.Net.CarLaneFlags.Forward | Game.Net.CarLaneFlags.Approach | Game.Net.CarLaneFlags.Roundabout | Game.Net.CarLaneFlags.RightLimit | Game.Net.CarLaneFlags.LeftLimit | Game.Net.CarLaneFlags.ForbidPassing | Game.Net.CarLaneFlags.RightOfWay | Game.Net.CarLaneFlags.TrafficLights | Game.Net.CarLaneFlags.ParkingLeft | Game.Net.CarLaneFlags.ParkingRight | Game.Net.CarLaneFlags.Forbidden | Game.Net.CarLaneFlags.AllowEnter);
		if (!m_CurveData.TryGetComponent(lane, out var componentData))
		{
			return false;
		}
		if (m_CarLaneData.TryGetComponent(lane, out var componentData2))
		{
			componentData2.m_SpeedLimit *= m_SpeedLimitFactor;
			laneFlags = componentData2.m_Flags;
			float driveSpeed = VehicleUtils.GetMaxDriveSpeed(m_PrefabCar, componentData2);
			float num = 0f - m_PrefabObjectGeometry.m_Bounds.max.z;
			float num2 = m_Distance + num;
			int yieldOverride = 0;
			bool flag = false;
			bool flag2 = curveOffset.y < curveOffset.x;
			Entity blocker = Entity.Null;
			BlockerType blockerType = BlockerType.Limit;
			if ((componentData2.m_Flags & Game.Net.CarLaneFlags.Approach) == 0)
			{
				if ((carLaneFlags & Game.Net.CarLaneFlags.Approach) == 0)
				{
					componentData2.m_Flags &= ~(Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.Stop | Game.Net.CarLaneFlags.TrafficLights);
					if ((componentData2.m_Flags & Game.Net.CarLaneFlags.SideConnection) == 0)
					{
						componentData2.m_Flags &= ~(Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.UTurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight | Game.Net.CarLaneFlags.Forward);
					}
				}
				flag = (componentData2.m_Flags & Game.Net.CarLaneFlags.Roundabout) != 0;
				if ((componentData2.m_Flags & (Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.TrafficLights)) != 0 && m_LaneSignalData.TryGetComponent(lane, out var componentData3))
				{
					float brakingDistance = VehicleUtils.GetBrakingDistance(m_PrefabCar, m_CurrentSpeed, 0f);
					if (!flag && brakingDistance <= num2 && !CheckSpace(lane, curveOffset, nextLanes, out blocker))
					{
						driveSpeed = 0f;
						blockerType = BlockerType.Continuing;
					}
					else
					{
						needSignal = true;
						switch (componentData3.m_Signal)
						{
						case LaneSignalType.Stop:
							if ((m_Priority < 108 || (componentData3.m_Flags & LaneSignalFlags.Physical) != 0) && brakingDistance <= num2 + 1f)
							{
								driveSpeed = 0f;
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
							if ((m_Priority < 108 || (componentData3.m_Flags & LaneSignalFlags.Physical) != 0) && brakingDistance <= num2)
							{
								driveSpeed = 0f;
								blocker = componentData3.m_Blocker;
								blockerType = BlockerType.Signal;
							}
							break;
						case LaneSignalType.Yield:
							yieldOverride = 1;
							break;
						}
					}
				}
				else if ((componentData2.m_Flags & Game.Net.CarLaneFlags.Stop) != 0)
				{
					if (m_Priority < 108 && num2 >= 1.1f)
					{
						driveSpeed = 0f;
						blockerType = BlockerType.Limit;
					}
					else if (!flag && VehicleUtils.GetBrakingDistance(m_PrefabCar, m_CurrentSpeed, 0f) <= num2 && !CheckSpace(lane, curveOffset, nextLanes, out blocker))
					{
						driveSpeed = 0f;
						blockerType = BlockerType.Continuing;
					}
					yieldOverride = 1;
				}
				else if ((componentData2.m_Flags & (Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.UTurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight | Game.Net.CarLaneFlags.Forward)) != 0 && !flag && VehicleUtils.GetBrakingDistance(m_PrefabCar, m_CurrentSpeed, 0f) <= num2 && !CheckSpace(lane, curveOffset, nextLanes, out blocker))
				{
					driveSpeed = 0f;
					blockerType = BlockerType.Continuing;
				}
			}
			num2 += m_DistanceOffset;
			float num3;
			if (driveSpeed == 0f)
			{
				num3 = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, math.max(0f, num2 - 0.5f), m_SafeTimeStep);
			}
			else
			{
				if (m_LaneConditionData.HasComponent(lane))
				{
					VehicleUtils.ModifyDriveSpeed(ref driveSpeed, m_LaneConditionData[lane]);
				}
				num3 = math.max(driveSpeed, VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, m_Distance, driveSpeed, m_TimeStep));
			}
			if (num3 < m_MaxSpeed)
			{
				m_MaxSpeed = MathUtils.Clamp(num3, m_SpeedRange);
				m_Blocker = blocker;
				m_BlockerType = blockerType;
			}
			if (componentData2.m_CautionEnd >= componentData2.m_CautionStart)
			{
				Bounds1 cautionBounds = componentData2.cautionBounds;
				float2 @float = math.select(curveOffset, curveOffset.yx, flag2);
				if (cautionBounds.max > @float.x && cautionBounds.min < @float.y)
				{
					float distance = num2 + componentData.m_Length * math.max(0f, math.select(cautionBounds.min - @float.x, @float.y - cautionBounds.max, flag2));
					float num4 = componentData2.m_SpeedLimit * math.select(0.5f, 0.8f, (componentData2.m_Flags & Game.Net.CarLaneFlags.IsSecured) != 0);
					num3 = math.max(num4, VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, distance, num4, m_SafeTimeStep));
					if (num3 < m_MaxSpeed)
					{
						m_MaxSpeed = MathUtils.Clamp(num3, m_SpeedRange);
						m_Blocker = Entity.Null;
						m_BlockerType = BlockerType.Caution;
					}
				}
			}
			m_Curve = componentData;
			m_CurveOffset = curveOffset;
			m_Lane = lane;
			if (nextLanes.Length != 0)
			{
				CarNavigationLane carNavigationLane = nextLanes[0];
				m_NextOffset = carNavigationLane.m_CurvePosition;
				m_NextLane = carNavigationLane.m_Lane;
			}
			else
			{
				m_NextOffset = 0f;
				m_NextLane = Entity.Null;
			}
			minOffset = math.select(minOffset, curveOffset.x, flag2 ? (curveOffset.x < 1f) : (curveOffset.x > 0f));
			CheckCurrentLane(num2, minOffset, flag2);
			CheckOverlappingLanes(num2, minOffset, yieldOverride, componentData2.m_SpeedLimit, flag, flag2, requestSpace);
		}
		else if (m_ParkingLaneData.HasComponent(lane))
		{
			float num5 = 0f - m_PrefabObjectGeometry.m_Bounds.max.z;
			float distance2 = m_Distance + num5 + m_DistanceOffset;
			m_Curve = componentData;
			m_CurveOffset = curveOffset;
			m_Lane = lane;
			CheckParkingLane(distance2);
		}
		float3 float2 = MathUtils.Position(componentData.m_Bezier, curveOffset.y);
		float num6 = math.abs(curveOffset.y - curveOffset.x);
		float num7 = math.max(0.001f, math.lerp(math.distance(m_CurrentPosition, float2), componentData.m_Length * num6, num6));
		if (num7 > 1f)
		{
			m_PrevPosition = m_CurrentPosition;
			m_PrevDistance = m_Distance;
		}
		m_CurrentPosition = float2;
		m_Distance += num7;
		float brakingDistance2 = VehicleUtils.GetBrakingDistance(m_PrefabCar, m_MaxSpeed, m_SafeTimeStep);
		return (m_Distance + m_DistanceOffset - 20f >= brakingDistance2) | (m_MaxSpeed == m_SpeedRange.min);
	}
```

- `public IterateTarget(Unity.Mathematics.float3 targetPosition) : System.Void`  

```csharp
public void IterateTarget(float3 targetPosition, float maxLaneSpeed)
	{
		float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, m_Distance, maxLaneSpeed, m_TimeStep);
		m_Distance += math.distance(m_CurrentPosition, targetPosition);
		maxBrakingSpeed = math.min(maxBrakingSpeed, VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, m_Distance, m_TimeStep));
		if (maxBrakingSpeed < m_MaxSpeed)
		{
			m_MaxSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
			m_Blocker = Entity.Null;
			m_BlockerType = BlockerType.None;
		}
	}
```

- `public IterateTarget(Unity.Mathematics.float3 targetPosition, System.Single maxLaneSpeed) : System.Void`  

```csharp
public void IterateTarget(float3 targetPosition, float maxLaneSpeed)
	{
		float maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, m_Distance, maxLaneSpeed, m_TimeStep);
		m_Distance += math.distance(m_CurrentPosition, targetPosition);
		maxBrakingSpeed = math.min(maxBrakingSpeed, VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, m_Distance, m_TimeStep));
		if (maxBrakingSpeed < m_MaxSpeed)
		{
			m_MaxSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
			m_Blocker = Entity.Null;
			m_BlockerType = BlockerType.None;
		}
	}
```

- `private UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset, System.Boolean ignore, System.Boolean inverse1, System.Boolean inverse2, Unity.Mathematics.float3 currentPos) : System.Void`  

```csharp
private void UpdateMaxSpeed(Entity obj, BlockerType blockerType, float objectSpeed, float laneOffset, float distanceFactor, float distanceOffset, bool ignore, bool inverse1, bool inverse2, float3 currentPos)
	{
		PrefabRef prefabRef = m_PrefabRefData[obj];
		float num = 0f;
		bool flag = false;
		ObjectGeometryData componentData2;
		if (m_PrefabTrainData.TryGetComponent(prefabRef.m_Prefab, out var componentData))
		{
			Train train = m_TrainData[obj];
			float2 @float = componentData.m_AttachOffsets - componentData.m_BogieOffsets;
			num = math.select(@float.y, @float.x, (train.m_Flags & Game.Vehicles.TrainFlags.Reversed) != 0);
			flag = true;
		}
		else if (m_PrefabObjectGeometryData.TryGetComponent(prefabRef.m_Prefab, out componentData2))
		{
			num = 0f - componentData2.m_Bounds.min.z;
		}
		float2 float2 = math.select(m_CurveOffset, m_CurveOffset.yx, inverse1 != inverse2);
		float2 = math.select(laneOffset - float2, float2 - laneOffset, inverse2);
		if (float2.y * m_Curve.m_Length >= num)
		{
			return;
		}
		float2.x = math.min(0f, float2.x);
		Transform transform = m_TransformData[obj];
		float num2 = math.distance(MathUtils.Position(m_Curve.m_Bezier, laneOffset + math.select(0f - float2.x, float2.x, inverse2)), currentPos);
		num2 += float2.x * m_Curve.m_Length;
		num2 = ((!(math.dot(transform.m_Position - currentPos, currentPos - m_PrevPosition) < 0f)) ? math.min(num2, math.distance(transform.m_Position, currentPos)) : math.min(num2, math.distance(transform.m_Position, m_PrevPosition) + m_PrevDistance - m_Distance));
		num2 -= num;
		num2 *= distanceFactor;
		num2 += distanceOffset;
		float maxBrakingSpeed;
		if (objectSpeed > 0.001f && m_PrefabCarData.TryGetComponent(prefabRef.m_Prefab, out var componentData3))
		{
			objectSpeed = math.max(0f, objectSpeed - componentData3.m_Braking * m_TimeStep * 2f) * distanceFactor;
			if (m_PrefabCar.m_Braking >= componentData3.m_Braking)
			{
				num2 += objectSpeed * m_SafeTimeStep;
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, num2, objectSpeed, m_SafeTimeStep);
			}
			else
			{
				num2 += VehicleUtils.GetBrakingDistance(componentData3, objectSpeed, m_SafeTimeStep);
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, num2, m_SafeTimeStep);
			}
		}
		else if (objectSpeed > 0.001f && flag)
		{
			objectSpeed = math.max(0f, objectSpeed - componentData.m_Braking * m_TimeStep * 2f) * distanceFactor;
			if (m_PrefabCar.m_Braking >= componentData.m_Braking)
			{
				num2 += objectSpeed * m_SafeTimeStep;
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, num2, objectSpeed, m_SafeTimeStep);
			}
			else
			{
				num2 += VehicleUtils.GetBrakingDistance(componentData, objectSpeed, m_SafeTimeStep);
				maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, num2, m_SafeTimeStep);
			}
		}
		else
		{
			maxBrakingSpeed = VehicleUtils.GetMaxBrakingSpeed(m_PrefabCar, num2, m_SafeTimeStep);
		}
		if (blockerType == BlockerType.Oncoming)
		{
			float y = 2f - maxBrakingSpeed * (1f / 6f);
			m_Oncoming = math.max(m_Oncoming, y);
			maxBrakingSpeed = math.max(maxBrakingSpeed, 3f);
			maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
			if (maxBrakingSpeed < m_MaxSpeed)
			{
				m_MaxSpeed = maxBrakingSpeed;
				m_Blocker = Entity.Null;
				m_BlockerType = blockerType;
			}
		}
		else
		{
			maxBrakingSpeed = math.select(maxBrakingSpeed, 3f, ignore && maxBrakingSpeed < 3f);
			maxBrakingSpeed = MathUtils.Clamp(maxBrakingSpeed, m_SpeedRange);
			if (maxBrakingSpeed < m_MaxSpeed)
			{
				m_MaxSpeed = maxBrakingSpeed;
				m_Blocker = obj;
				m_BlockerType = blockerType;
			}
		}
	}
```


