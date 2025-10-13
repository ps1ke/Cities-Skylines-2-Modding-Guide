# Game.Simulation.CarLaneSelectIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CarLaneSelectIterator
{
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.ComponentLookup<Game.Net.Lane> m_LaneData;
    public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
    public Unity.Entities.BufferLookup<Game.Net.SubLane> m_Lanes;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
    public Unity.Entities.Entity m_Entity;
    public Unity.Entities.Entity m_Blocker;
    public System.Int32 m_Priority;
    public Game.Net.CarLaneFlags m_ForbidLaneFlags;
    public Game.Net.CarLaneFlags m_PreferLaneFlags;
    private Unity.Collections.NativeArray<System.Single> m_Buffer;
    private System.Int32 m_BufferPos;
    private System.Single m_LaneSwitchCost;
    private System.Single m_LaneSwitchBaseCost;
    private Unity.Entities.Entity m_PrevLane;

    public System.Void CalculateLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, System.Int32 index);
    public System.Void CalculateLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, System.Int32 index);
    private System.Single CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.CarLaneFlags laneFlags);
    private System.Single CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.CarLaneFlags laneFlags);
    private System.Single CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.CarLaneFlags laneFlags);
    private System.Void DrawLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePos, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher, System.Single cost);
    public System.Void DrawLaneCosts(Game.Vehicles.CarCurrentLane currentLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher);
    public System.Void DrawLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher);
    private System.Single GetLaneDriveCost(Game.Net.CarLaneFlags flags);
    private System.Single GetLanePriorityCost(System.Int32 lanePriority);
    private System.Single GetLaneSwitchCost(System.Int32 numLanes);
    private Game.Vehicles.CarLaneFlags GetTurnFlags(Unity.Entities.Entity currentLane, System.Int32 currentIndex, System.Int32 changeIndex);
    public System.Void SetBuffer(Game.Simulation.CarLaneSelectBuffer& buffer);
    public System.Void UpdateOptimalLane(Game.Vehicles.CarCurrentLane& currentLane, Game.Vehicles.CarNavigationLane nextNavLaneData);
    public System.Void UpdateOptimalLane(Game.Vehicles.CarNavigationLane& navLaneData);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Lane> m_LaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Lane> m_LaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
```

- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_Lanes`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.SubLane> m_Lanes;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
```

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Unity.Entities.Entity m_Blocker`  

```csharp
public Unity.Entities.Entity m_Blocker;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public Game.Net.CarLaneFlags m_ForbidLaneFlags`  

```csharp
public Game.Net.CarLaneFlags m_ForbidLaneFlags;
```

- `public Game.Net.CarLaneFlags m_PreferLaneFlags`  

```csharp
public Game.Net.CarLaneFlags m_PreferLaneFlags;
```

- `private Unity.Collections.NativeArray<System.Single> m_Buffer`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Buffer;
```

- `private System.Int32 m_BufferPos`  

```csharp
private System.Int32 m_BufferPos;
```

- `private System.Single m_LaneSwitchCost`  

```csharp
private System.Single m_LaneSwitchCost;
```

- `private System.Single m_LaneSwitchBaseCost`  

```csharp
private System.Single m_LaneSwitchBaseCost;
```

- `private Unity.Entities.Entity m_PrevLane`  

```csharp
private Unity.Entities.Entity m_PrevLane;
```


## Methods

- `public CalculateLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, System.Int32 index) : System.Void`  

```csharp
public void CalculateLaneCosts(CarNavigationLane navLaneData, CarNavigationLane nextNavLaneData, int index)
	{
		if ((navLaneData.m_Flags & (Game.Vehicles.CarLaneFlags.Reserved | Game.Vehicles.CarLaneFlags.FixedLane)) == 0 && m_SlaveLaneData.TryGetComponent(navLaneData.m_Lane, out var componentData))
		{
			Owner owner = m_OwnerData[navLaneData.m_Lane];
			DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
			int num = math.min(componentData.m_MaxIndex, dynamicBuffer.Length - 1);
			m_LaneSwitchCost = m_LaneSwitchBaseCost + math.select(1f, 5f, (componentData.m_Flags & SlaveLaneFlags.AllowChange) == 0);
			float laneObjectCost = math.abs(navLaneData.m_CurvePosition.y - navLaneData.m_CurvePosition.x) * 0.49f * (2f / (float)(2 + index));
			if ((nextNavLaneData.m_Flags & (Game.Vehicles.CarLaneFlags.Reserved | Game.Vehicles.CarLaneFlags.FixedLane)) == 0 && m_SlaveLaneData.TryGetComponent(nextNavLaneData.m_Lane, out var componentData2))
			{
				Owner owner2 = m_OwnerData[nextNavLaneData.m_Lane];
				DynamicBuffer<SubLane> dynamicBuffer2 = m_Lanes[owner2.m_Owner];
				int num2 = math.min(componentData2.m_MaxIndex, dynamicBuffer2.Length - 1);
				int num3 = m_BufferPos - (num2 - componentData2.m_MinIndex + 1);
				for (int i = componentData.m_MinIndex; i <= num; i++)
				{
					Entity subLane = dynamicBuffer[i].m_SubLane;
					Lane lane = m_LaneData[subLane];
					float num4 = 1000000f;
					int num5;
					int num6;
					if ((nextNavLaneData.m_Flags & Game.Vehicles.CarLaneFlags.GroupTarget) != 0)
					{
						num5 = componentData2.m_MinIndex;
						num6 = num2;
					}
					else
					{
						num5 = 100000;
						num6 = -100000;
						if ((componentData.m_Flags & SlaveLaneFlags.MiddleEnd) != 0)
						{
							for (int j = componentData2.m_MinIndex; j <= num2; j++)
							{
								Lane lane2 = m_LaneData[dynamicBuffer2[j].m_SubLane];
								if (lane.m_EndNode.EqualsIgnoreCurvePos(lane2.m_MiddleNode))
								{
									num5 = math.min(num5, j);
									num6 = j;
								}
							}
						}
						else if ((componentData2.m_Flags & SlaveLaneFlags.MiddleStart) != 0)
						{
							for (int k = componentData2.m_MinIndex; k <= num2; k++)
							{
								Lane lane3 = m_LaneData[dynamicBuffer2[k].m_SubLane];
								if (lane.m_MiddleNode.EqualsIgnoreCurvePos(lane3.m_StartNode))
								{
									num5 = math.min(num5, k);
									num6 = k;
								}
							}
						}
						else
						{
							for (int l = componentData2.m_MinIndex; l <= num2; l++)
							{
								Lane lane4 = m_LaneData[dynamicBuffer2[l].m_SubLane];
								if (lane.m_EndNode.Equals(lane4.m_StartNode))
								{
									num5 = math.min(num5, l);
									num6 = l;
								}
							}
						}
					}
					if (num5 <= num6)
					{
						int num7 = num3;
						for (int m = componentData2.m_MinIndex; m < num5; m++)
						{
							num4 = math.min(num4, m_Buffer[num7++] + GetLaneSwitchCost(num5 - m));
						}
						for (int n = num5; n <= num6; n++)
						{
							num4 = math.min(num4, m_Buffer[num7++]);
						}
						for (int num8 = num6 + 1; num8 <= num2; num8++)
						{
							num4 = math.min(num4, m_Buffer[num7++] + GetLaneSwitchCost(num8 - num6));
						}
						num4 += CalculateLaneObjectCost(laneObjectCost, index, subLane, navLaneData.m_Flags);
						if (m_LaneReservationData.TryGetComponent(subLane, out var componentData3))
						{
							num4 += GetLanePriorityCost(componentData3.GetPriority());
						}
						if (m_CarLaneData.TryGetComponent(subLane, out var componentData4))
						{
							num4 += GetLaneDriveCost(componentData4.m_Flags);
						}
					}
					m_Buffer[m_BufferPos++] = num4;
				}
			}
			else if ((nextNavLaneData.m_Flags & Game.Vehicles.CarLaneFlags.TransformTarget) != 0)
			{
				for (int num9 = componentData.m_MinIndex; num9 <= num; num9++)
				{
					Entity subLane2 = dynamicBuffer[num9].m_SubLane;
					float num10 = CalculateLaneObjectCost(laneObjectCost, index, subLane2, navLaneData.m_Flags);
					if (m_LaneReservationData.TryGetComponent(subLane2, out var componentData5))
					{
						num10 += GetLanePriorityCost(componentData5.GetPriority());
					}
					if (m_CarLaneData.TryGetComponent(subLane2, out var componentData6))
					{
						num10 += GetLaneDriveCost(componentData6.m_Flags);
					}
					m_Buffer[m_BufferPos++] = num10;
				}
			}
			else
			{
				int num11 = 100000;
				int num12 = -100000;
				if ((nextNavLaneData.m_Flags & Game.Vehicles.CarLaneFlags.GroupTarget) != 0)
				{
					for (int num13 = componentData.m_MinIndex; num13 <= num; num13++)
					{
						if (dynamicBuffer[num13].m_SubLane == nextNavLaneData.m_Lane)
						{
							num11 = num13;
							num12 = num13;
							break;
						}
					}
				}
				else
				{
					Lane lane5 = m_LaneData[nextNavLaneData.m_Lane];
					for (int num14 = componentData.m_MinIndex; num14 <= num; num14++)
					{
						Lane lane6 = m_LaneData[dynamicBuffer[num14].m_SubLane];
						if ((componentData.m_Flags & SlaveLaneFlags.MiddleEnd) != 0)
						{
							if (lane6.m_EndNode.EqualsIgnoreCurvePos(lane5.m_MiddleNode))
							{
								num11 = math.min(num11, num14);
								num12 = num14;
							}
						}
						else if (lane6.m_EndNode.Equals(lane5.m_StartNode))
						{
							num11 = math.min(num11, num14);
							num12 = num14;
						}
					}
				}
				for (int num15 = componentData.m_MinIndex; num15 <= num; num15++)
				{
					Entity subLane3 = dynamicBuffer[num15].m_SubLane;
					float num16 = 0f;
					if (num11 <= num12)
					{
						num16 += GetLaneSwitchCost(math.max(0, math.max(num11 - num15, num15 - num12)));
					}
					num16 += CalculateLaneObjectCost(laneObjectCost, index, subLane3, navLaneData.m_Flags);
					if (m_LaneReservationData.TryGetComponent(subLane3, out var componentData7))
					{
						num16 += GetLanePriorityCost(componentData7.GetPriority());
					}
					if (m_CarLaneData.TryGetComponent(subLane3, out var componentData8))
					{
						num16 += GetLaneDriveCost(componentData8.m_Flags);
					}
					m_Buffer[m_BufferPos++] = num16;
				}
			}
		}
		m_LaneSwitchBaseCost += 0.01f;
	}
```

- `public CalculateLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, System.Int32 index) : System.Void`  

```csharp
public void CalculateLaneCosts(CarNavigationLane navLaneData, CarNavigationLane nextNavLaneData, int index)
	{
		if ((navLaneData.m_Flags & (Game.Vehicles.CarLaneFlags.Reserved | Game.Vehicles.CarLaneFlags.FixedLane)) == 0 && m_SlaveLaneData.TryGetComponent(navLaneData.m_Lane, out var componentData))
		{
			Owner owner = m_OwnerData[navLaneData.m_Lane];
			DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
			int num = math.min(componentData.m_MaxIndex, dynamicBuffer.Length - 1);
			m_LaneSwitchCost = m_LaneSwitchBaseCost + math.select(1f, 5f, (componentData.m_Flags & SlaveLaneFlags.AllowChange) == 0);
			float laneObjectCost = math.abs(navLaneData.m_CurvePosition.y - navLaneData.m_CurvePosition.x) * 0.49f * (2f / (float)(2 + index));
			if ((nextNavLaneData.m_Flags & (Game.Vehicles.CarLaneFlags.Reserved | Game.Vehicles.CarLaneFlags.FixedLane)) == 0 && m_SlaveLaneData.TryGetComponent(nextNavLaneData.m_Lane, out var componentData2))
			{
				Owner owner2 = m_OwnerData[nextNavLaneData.m_Lane];
				DynamicBuffer<SubLane> dynamicBuffer2 = m_Lanes[owner2.m_Owner];
				int num2 = math.min(componentData2.m_MaxIndex, dynamicBuffer2.Length - 1);
				int num3 = m_BufferPos - (num2 - componentData2.m_MinIndex + 1);
				for (int i = componentData.m_MinIndex; i <= num; i++)
				{
					Entity subLane = dynamicBuffer[i].m_SubLane;
					Lane lane = m_LaneData[subLane];
					float num4 = 1000000f;
					int num5;
					int num6;
					if ((nextNavLaneData.m_Flags & Game.Vehicles.CarLaneFlags.GroupTarget) != 0)
					{
						num5 = componentData2.m_MinIndex;
						num6 = num2;
					}
					else
					{
						num5 = 100000;
						num6 = -100000;
						if ((componentData.m_Flags & SlaveLaneFlags.MiddleEnd) != 0)
						{
							for (int j = componentData2.m_MinIndex; j <= num2; j++)
							{
								Lane lane2 = m_LaneData[dynamicBuffer2[j].m_SubLane];
								if (lane.m_EndNode.EqualsIgnoreCurvePos(lane2.m_MiddleNode))
								{
									num5 = math.min(num5, j);
									num6 = j;
								}
							}
						}
						else if ((componentData2.m_Flags & SlaveLaneFlags.MiddleStart) != 0)
						{
							for (int k = componentData2.m_MinIndex; k <= num2; k++)
							{
								Lane lane3 = m_LaneData[dynamicBuffer2[k].m_SubLane];
								if (lane.m_MiddleNode.EqualsIgnoreCurvePos(lane3.m_StartNode))
								{
									num5 = math.min(num5, k);
									num6 = k;
								}
							}
						}
						else
						{
							for (int l = componentData2.m_MinIndex; l <= num2; l++)
							{
								Lane lane4 = m_LaneData[dynamicBuffer2[l].m_SubLane];
								if (lane.m_EndNode.Equals(lane4.m_StartNode))
								{
									num5 = math.min(num5, l);
									num6 = l;
								}
							}
						}
					}
					if (num5 <= num6)
					{
						int num7 = num3;
						for (int m = componentData2.m_MinIndex; m < num5; m++)
						{
							num4 = math.min(num4, m_Buffer[num7++] + GetLaneSwitchCost(num5 - m));
						}
						for (int n = num5; n <= num6; n++)
						{
							num4 = math.min(num4, m_Buffer[num7++]);
						}
						for (int num8 = num6 + 1; num8 <= num2; num8++)
						{
							num4 = math.min(num4, m_Buffer[num7++] + GetLaneSwitchCost(num8 - num6));
						}
						num4 += CalculateLaneObjectCost(laneObjectCost, index, subLane, navLaneData.m_Flags);
						if (m_LaneReservationData.TryGetComponent(subLane, out var componentData3))
						{
							num4 += GetLanePriorityCost(componentData3.GetPriority());
						}
						if (m_CarLaneData.TryGetComponent(subLane, out var componentData4))
						{
							num4 += GetLaneDriveCost(componentData4.m_Flags);
						}
					}
					m_Buffer[m_BufferPos++] = num4;
				}
			}
			else if ((nextNavLaneData.m_Flags & Game.Vehicles.CarLaneFlags.TransformTarget) != 0)
			{
				for (int num9 = componentData.m_MinIndex; num9 <= num; num9++)
				{
					Entity subLane2 = dynamicBuffer[num9].m_SubLane;
					float num10 = CalculateLaneObjectCost(laneObjectCost, index, subLane2, navLaneData.m_Flags);
					if (m_LaneReservationData.TryGetComponent(subLane2, out var componentData5))
					{
						num10 += GetLanePriorityCost(componentData5.GetPriority());
					}
					if (m_CarLaneData.TryGetComponent(subLane2, out var componentData6))
					{
						num10 += GetLaneDriveCost(componentData6.m_Flags);
					}
					m_Buffer[m_BufferPos++] = num10;
				}
			}
			else
			{
				int num11 = 100000;
				int num12 = -100000;
				if ((nextNavLaneData.m_Flags & Game.Vehicles.CarLaneFlags.GroupTarget) != 0)
				{
					for (int num13 = componentData.m_MinIndex; num13 <= num; num13++)
					{
						if (dynamicBuffer[num13].m_SubLane == nextNavLaneData.m_Lane)
						{
							num11 = num13;
							num12 = num13;
							break;
						}
					}
				}
				else
				{
					Lane lane5 = m_LaneData[nextNavLaneData.m_Lane];
					for (int num14 = componentData.m_MinIndex; num14 <= num; num14++)
					{
						Lane lane6 = m_LaneData[dynamicBuffer[num14].m_SubLane];
						if ((componentData.m_Flags & SlaveLaneFlags.MiddleEnd) != 0)
						{
							if (lane6.m_EndNode.EqualsIgnoreCurvePos(lane5.m_MiddleNode))
							{
								num11 = math.min(num11, num14);
								num12 = num14;
							}
						}
						else if (lane6.m_EndNode.Equals(lane5.m_StartNode))
						{
							num11 = math.min(num11, num14);
							num12 = num14;
						}
					}
				}
				for (int num15 = componentData.m_MinIndex; num15 <= num; num15++)
				{
					Entity subLane3 = dynamicBuffer[num15].m_SubLane;
					float num16 = 0f;
					if (num11 <= num12)
					{
						num16 += GetLaneSwitchCost(math.max(0, math.max(num11 - num15, num15 - num12)));
					}
					num16 += CalculateLaneObjectCost(laneObjectCost, index, subLane3, navLaneData.m_Flags);
					if (m_LaneReservationData.TryGetComponent(subLane3, out var componentData7))
					{
						num16 += GetLanePriorityCost(componentData7.GetPriority());
					}
					if (m_CarLaneData.TryGetComponent(subLane3, out var componentData8))
					{
						num16 += GetLaneDriveCost(componentData8.m_Flags);
					}
					m_Buffer[m_BufferPos++] = num16;
				}
			}
		}
		m_LaneSwitchBaseCost += 0.01f;
	}
```

- `private CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.CarLaneFlags laneFlags) : System.Single`  

```csharp
private float CalculateLaneObjectCost(LaneObject laneObject, float laneObjectCost, Game.Vehicles.CarLaneFlags laneFlags)
	{
		if (!m_MovingData.HasComponent(laneObject.m_LaneObject))
		{
			if (m_CarData.HasComponent(laneObject.m_LaneObject) && (m_CarData[laneObject.m_LaneObject].m_Flags & CarFlags.Queueing) != 0 && (laneFlags & Game.Vehicles.CarLaneFlags.Queue) != 0)
			{
				return laneObjectCost;
			}
			return math.lerp(10000000f, 9000000f, laneObject.m_CurvePosition.y);
		}
		return laneObjectCost;
	}
```

- `private CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.CarLaneFlags laneFlags) : System.Single`  

```csharp
private float CalculateLaneObjectCost(LaneObject laneObject, float laneObjectCost, Game.Vehicles.CarLaneFlags laneFlags)
	{
		if (!m_MovingData.HasComponent(laneObject.m_LaneObject))
		{
			if (m_CarData.HasComponent(laneObject.m_LaneObject) && (m_CarData[laneObject.m_LaneObject].m_Flags & CarFlags.Queueing) != 0 && (laneFlags & Game.Vehicles.CarLaneFlags.Queue) != 0)
			{
				return laneObjectCost;
			}
			return math.lerp(10000000f, 9000000f, laneObject.m_CurvePosition.y);
		}
		return laneObjectCost;
	}
```

- `private CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.CarLaneFlags laneFlags) : System.Single`  

```csharp
private float CalculateLaneObjectCost(LaneObject laneObject, float laneObjectCost, Game.Vehicles.CarLaneFlags laneFlags)
	{
		if (!m_MovingData.HasComponent(laneObject.m_LaneObject))
		{
			if (m_CarData.HasComponent(laneObject.m_LaneObject) && (m_CarData[laneObject.m_LaneObject].m_Flags & CarFlags.Queueing) != 0 && (laneFlags & Game.Vehicles.CarLaneFlags.Queue) != 0)
			{
				return laneObjectCost;
			}
			return math.lerp(10000000f, 9000000f, laneObject.m_CurvePosition.y);
		}
		return laneObjectCost;
	}
```

- `private DrawLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePos, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher, System.Single cost) : System.Void`  

```csharp
private void DrawLane(Entity lane, float2 curvePos, ComponentLookup<Curve> curveData, GizmoBatcher gizmoBatcher, float cost)
	{
		Curve curve = curveData[lane];
		UnityEngine.Color color;
		if (cost >= 100000f)
		{
			color = UnityEngine.Color.black;
		}
		else
		{
			cost = math.sqrt(cost);
			color = ((!(cost < 2f)) ? UnityEngine.Color.Lerp(UnityEngine.Color.yellow, UnityEngine.Color.red, (cost - 2f) * 0.5f) : UnityEngine.Color.Lerp(UnityEngine.Color.cyan, UnityEngine.Color.yellow, cost * 0.5f));
		}
		Bezier4x3 bezier = MathUtils.Cut(curve.m_Bezier, curvePos);
		float length = curve.m_Length * math.abs(curvePos.y - curvePos.x);
		gizmoBatcher.DrawCurve(bezier, length, color);
	}
```

- `public DrawLaneCosts(Game.Vehicles.CarCurrentLane currentLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  

```csharp
public void DrawLaneCosts(CarNavigationLane navLaneData, ComponentLookup<Curve> curveData, GizmoBatcher gizmoBatcher)
	{
		if (m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			Owner owner = m_OwnerData[navLaneData.m_Lane];
			DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
			int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
			if ((navLaneData.m_Flags & (Game.Vehicles.CarLaneFlags.Reserved | Game.Vehicles.CarLaneFlags.FixedLane)) == 0)
			{
				m_BufferPos -= num - slaveLane.m_MinIndex + 1;
				int bufferPos = m_BufferPos;
				for (int i = slaveLane.m_MinIndex; i <= num; i++)
				{
					float cost = m_Buffer[bufferPos++];
					DrawLane(dynamicBuffer[i].m_SubLane, navLaneData.m_CurvePosition, curveData, gizmoBatcher, cost);
				}
			}
			else
			{
				for (int j = slaveLane.m_MinIndex; j <= num; j++)
				{
					Entity subLane = dynamicBuffer[j].m_SubLane;
					float cost2 = math.select(1000000f, 0f, subLane == navLaneData.m_Lane);
					DrawLane(subLane, navLaneData.m_CurvePosition, curveData, gizmoBatcher, cost2);
				}
			}
		}
		m_PrevLane = navLaneData.m_Lane;
	}
```

- `public DrawLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  

```csharp
public void DrawLaneCosts(CarNavigationLane navLaneData, ComponentLookup<Curve> curveData, GizmoBatcher gizmoBatcher)
	{
		if (m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			Owner owner = m_OwnerData[navLaneData.m_Lane];
			DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
			int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
			if ((navLaneData.m_Flags & (Game.Vehicles.CarLaneFlags.Reserved | Game.Vehicles.CarLaneFlags.FixedLane)) == 0)
			{
				m_BufferPos -= num - slaveLane.m_MinIndex + 1;
				int bufferPos = m_BufferPos;
				for (int i = slaveLane.m_MinIndex; i <= num; i++)
				{
					float cost = m_Buffer[bufferPos++];
					DrawLane(dynamicBuffer[i].m_SubLane, navLaneData.m_CurvePosition, curveData, gizmoBatcher, cost);
				}
			}
			else
			{
				for (int j = slaveLane.m_MinIndex; j <= num; j++)
				{
					Entity subLane = dynamicBuffer[j].m_SubLane;
					float cost2 = math.select(1000000f, 0f, subLane == navLaneData.m_Lane);
					DrawLane(subLane, navLaneData.m_CurvePosition, curveData, gizmoBatcher, cost2);
				}
			}
		}
		m_PrevLane = navLaneData.m_Lane;
	}
```

- `private GetLaneDriveCost(Game.Net.CarLaneFlags flags) : System.Single`  

```csharp
private float GetLaneDriveCost(Game.Net.CarLaneFlags flags)
	{
		float falseValue = math.select(0f, 0.4f, ((flags & m_PreferLaneFlags) == 0) & (m_PreferLaneFlags != ~(Game.Net.CarLaneFlags.Unsafe | Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.Invert | Game.Net.CarLaneFlags.SideConnection | Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.LevelCrossing | Game.Net.CarLaneFlags.Twoway | Game.Net.CarLaneFlags.IsSecured | Game.Net.CarLaneFlags.Runway | Game.Net.CarLaneFlags.Yield | Game.Net.CarLaneFlags.Stop | Game.Net.CarLaneFlags.ForbidCombustionEngines | Game.Net.CarLaneFlags.ForbidTransitTraffic | Game.Net.CarLaneFlags.ForbidHeavyTraffic | Game.Net.CarLaneFlags.PublicOnly | Game.Net.CarLaneFlags.Highway | Game.Net.CarLaneFlags.UTurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight | Game.Net.CarLaneFlags.Forward | Game.Net.CarLaneFlags.Approach | Game.Net.CarLaneFlags.Roundabout | Game.Net.CarLaneFlags.RightLimit | Game.Net.CarLaneFlags.LeftLimit | Game.Net.CarLaneFlags.ForbidPassing | Game.Net.CarLaneFlags.RightOfWay | Game.Net.CarLaneFlags.TrafficLights | Game.Net.CarLaneFlags.ParkingLeft | Game.Net.CarLaneFlags.ParkingRight | Game.Net.CarLaneFlags.Forbidden | Game.Net.CarLaneFlags.AllowEnter)));
		float trueValue = math.select(0.9f, 4.9f, m_Priority < 108);
		return math.select(falseValue, trueValue, (flags & m_ForbidLaneFlags) != 0);
	}
```

- `private GetLanePriorityCost(System.Int32 lanePriority) : System.Single`  

```csharp
private float GetLanePriorityCost(int lanePriority)
	{
		return (float)math.max(0, lanePriority - m_Priority) * 1f;
	}
```

- `private GetLaneSwitchCost(System.Int32 numLanes) : System.Single`  

```csharp
private float GetLaneSwitchCost(int numLanes)
	{
		return (float)(numLanes * numLanes * numLanes) * m_LaneSwitchCost;
	}
```

- `private GetTurnFlags(Unity.Entities.Entity currentLane, System.Int32 currentIndex, System.Int32 changeIndex) : Game.Vehicles.CarLaneFlags`  

```csharp
private Game.Vehicles.CarLaneFlags GetTurnFlags(Entity currentLane, int currentIndex, int changeIndex)
	{
		if (changeIndex != currentIndex)
		{
			bool flag = false;
			if (m_CarLaneData.TryGetComponent(currentLane, out var componentData))
			{
				flag = (componentData.m_Flags & Game.Net.CarLaneFlags.Invert) != 0;
			}
			if (changeIndex < currentIndex != flag)
			{
				return Game.Vehicles.CarLaneFlags.TurnLeft;
			}
			return Game.Vehicles.CarLaneFlags.TurnRight;
		}
		return (Game.Vehicles.CarLaneFlags)0u;
	}
```

- `public SetBuffer(Game.Simulation.CarLaneSelectBuffer& buffer) : System.Void`  

```csharp
public void SetBuffer(ref CarLaneSelectBuffer buffer)
	{
		m_Buffer = buffer.Ensure();
	}
```

- `public UpdateOptimalLane(Game.Vehicles.CarCurrentLane& currentLane, Game.Vehicles.CarNavigationLane nextNavLaneData) : System.Void`  

```csharp
public void UpdateOptimalLane(ref CarNavigationLane navLaneData)
	{
		if (m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			if ((navLaneData.m_Flags & (Game.Vehicles.CarLaneFlags.Reserved | Game.Vehicles.CarLaneFlags.FixedLane | Game.Vehicles.CarLaneFlags.FixedStart)) == 0 && m_LaneData.HasComponent(m_PrevLane))
			{
				Owner owner = m_OwnerData[navLaneData.m_Lane];
				DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
				int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
				m_BufferPos -= num - slaveLane.m_MinIndex + 1;
				int num2 = 100000;
				int num3 = -100000;
				if ((navLaneData.m_Flags & Game.Vehicles.CarLaneFlags.GroupTarget) == 0)
				{
					Lane lane = m_LaneData[m_PrevLane];
					SlaveLane slaveLane2 = default(SlaveLane);
					if (m_SlaveLaneData.HasComponent(m_PrevLane))
					{
						slaveLane2 = m_SlaveLaneData[m_PrevLane];
					}
					if ((slaveLane2.m_Flags & SlaveLaneFlags.MiddleEnd) != 0)
					{
						for (int i = slaveLane.m_MinIndex; i <= num; i++)
						{
							Lane lane2 = m_LaneData[dynamicBuffer[i].m_SubLane];
							if (lane.m_EndNode.EqualsIgnoreCurvePos(lane2.m_MiddleNode))
							{
								num2 = math.min(num2, i);
								num3 = i;
							}
						}
					}
					else if ((slaveLane.m_Flags & SlaveLaneFlags.MiddleStart) != 0)
					{
						for (int j = slaveLane.m_MinIndex; j <= num; j++)
						{
							Lane lane3 = m_LaneData[dynamicBuffer[j].m_SubLane];
							if (lane.m_MiddleNode.EqualsIgnoreCurvePos(lane3.m_StartNode))
							{
								num2 = math.min(num2, j);
								num3 = j;
							}
						}
					}
					else
					{
						for (int k = slaveLane.m_MinIndex; k <= num; k++)
						{
							Lane lane4 = m_LaneData[dynamicBuffer[k].m_SubLane];
							if (lane.m_EndNode.Equals(lane4.m_StartNode))
							{
								num2 = math.min(num2, k);
								num3 = k;
							}
						}
					}
				}
				if (num2 > num3)
				{
					num2 = slaveLane.m_MinIndex;
					num3 = num;
				}
				int bufferPos = m_BufferPos;
				float num4 = float.MaxValue;
				int index = slaveLane.m_MinIndex;
				for (int l = slaveLane.m_MinIndex; l < num2; l++)
				{
					float num5 = m_Buffer[bufferPos++] + GetLaneSwitchCost(num2 - l);
					if (num5 < num4)
					{
						num4 = num5;
						index = l;
					}
				}
				for (int m = num2; m <= num3; m++)
				{
					float num6 = m_Buffer[bufferPos++];
					if (num6 < num4)
					{
						num4 = num6;
						index = m;
					}
				}
				for (int n = num3 + 1; n <= num; n++)
				{
					float num7 = m_Buffer[bufferPos++] + GetLaneSwitchCost(n - num3);
					if (num7 < num4)
					{
						num4 = num7;
						index = n;
					}
				}
				navLaneData.m_Lane = dynamicBuffer[index].m_SubLane;
			}
			m_LaneSwitchCost = m_LaneSwitchBaseCost + math.select(1f, 5f, (slaveLane.m_Flags & SlaveLaneFlags.AllowChange) == 0);
		}
		else
		{
			m_LaneSwitchCost = 10000000f;
		}
		m_PrevLane = navLaneData.m_Lane;
		m_LaneSwitchBaseCost -= 0.01f;
	}
```

- `public UpdateOptimalLane(Game.Vehicles.CarNavigationLane& navLaneData) : System.Void`  

```csharp
public void UpdateOptimalLane(ref CarNavigationLane navLaneData)
	{
		if (m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			if ((navLaneData.m_Flags & (Game.Vehicles.CarLaneFlags.Reserved | Game.Vehicles.CarLaneFlags.FixedLane | Game.Vehicles.CarLaneFlags.FixedStart)) == 0 && m_LaneData.HasComponent(m_PrevLane))
			{
				Owner owner = m_OwnerData[navLaneData.m_Lane];
				DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
				int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
				m_BufferPos -= num - slaveLane.m_MinIndex + 1;
				int num2 = 100000;
				int num3 = -100000;
				if ((navLaneData.m_Flags & Game.Vehicles.CarLaneFlags.GroupTarget) == 0)
				{
					Lane lane = m_LaneData[m_PrevLane];
					SlaveLane slaveLane2 = default(SlaveLane);
					if (m_SlaveLaneData.HasComponent(m_PrevLane))
					{
						slaveLane2 = m_SlaveLaneData[m_PrevLane];
					}
					if ((slaveLane2.m_Flags & SlaveLaneFlags.MiddleEnd) != 0)
					{
						for (int i = slaveLane.m_MinIndex; i <= num; i++)
						{
							Lane lane2 = m_LaneData[dynamicBuffer[i].m_SubLane];
							if (lane.m_EndNode.EqualsIgnoreCurvePos(lane2.m_MiddleNode))
							{
								num2 = math.min(num2, i);
								num3 = i;
							}
						}
					}
					else if ((slaveLane.m_Flags & SlaveLaneFlags.MiddleStart) != 0)
					{
						for (int j = slaveLane.m_MinIndex; j <= num; j++)
						{
							Lane lane3 = m_LaneData[dynamicBuffer[j].m_SubLane];
							if (lane.m_MiddleNode.EqualsIgnoreCurvePos(lane3.m_StartNode))
							{
								num2 = math.min(num2, j);
								num3 = j;
							}
						}
					}
					else
					{
						for (int k = slaveLane.m_MinIndex; k <= num; k++)
						{
							Lane lane4 = m_LaneData[dynamicBuffer[k].m_SubLane];
							if (lane.m_EndNode.Equals(lane4.m_StartNode))
							{
								num2 = math.min(num2, k);
								num3 = k;
							}
						}
					}
				}
				if (num2 > num3)
				{
					num2 = slaveLane.m_MinIndex;
					num3 = num;
				}
				int bufferPos = m_BufferPos;
				float num4 = float.MaxValue;
				int index = slaveLane.m_MinIndex;
				for (int l = slaveLane.m_MinIndex; l < num2; l++)
				{
					float num5 = m_Buffer[bufferPos++] + GetLaneSwitchCost(num2 - l);
					if (num5 < num4)
					{
						num4 = num5;
						index = l;
					}
				}
				for (int m = num2; m <= num3; m++)
				{
					float num6 = m_Buffer[bufferPos++];
					if (num6 < num4)
					{
						num4 = num6;
						index = m;
					}
				}
				for (int n = num3 + 1; n <= num; n++)
				{
					float num7 = m_Buffer[bufferPos++] + GetLaneSwitchCost(n - num3);
					if (num7 < num4)
					{
						num4 = num7;
						index = n;
					}
				}
				navLaneData.m_Lane = dynamicBuffer[index].m_SubLane;
			}
			m_LaneSwitchCost = m_LaneSwitchBaseCost + math.select(1f, 5f, (slaveLane.m_Flags & SlaveLaneFlags.AllowChange) == 0);
		}
		else
		{
			m_LaneSwitchCost = 10000000f;
		}
		m_PrevLane = navLaneData.m_Lane;
		m_LaneSwitchBaseCost -= 0.01f;
	}
```


