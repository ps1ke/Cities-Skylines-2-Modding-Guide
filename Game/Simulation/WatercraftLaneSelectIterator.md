# Game.Simulation.WatercraftLaneSelectIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct WatercraftLaneSelectIterator
{
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.ComponentLookup<Game.Net.Lane> m_LaneData;
    public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_WatercraftData;
    public Unity.Entities.BufferLookup<Game.Net.SubLane> m_Lanes;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
    public Unity.Entities.Entity m_Entity;
    public Unity.Entities.Entity m_Blocker;
    public System.Int32 m_Priority;
    private Unity.Collections.NativeArray<System.Single> m_Buffer;
    private System.Int32 m_BufferPos;
    private System.Single m_LaneSwitchCost;
    private System.Single m_LaneSwitchBaseCost;
    private Unity.Entities.Entity m_PrevLane;

    public System.Void CalculateLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, System.Int32 index);
    public System.Void CalculateLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, System.Int32 index);
    private System.Single CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.WatercraftLaneFlags laneFlags);
    private System.Single CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.WatercraftLaneFlags laneFlags);
    private System.Single CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.WatercraftLaneFlags laneFlags);
    private System.Void DrawLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePos, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher, System.Single cost);
    public System.Void DrawLaneCosts(Game.Vehicles.WatercraftCurrentLane currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher);
    public System.Void DrawLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher);
    private System.Single GetLanePriorityCost(System.Int32 lanePriority);
    private System.Single GetLaneSwitchCost(System.Int32 numLanes);
    public System.Void SetBuffer(Game.Simulation.WatercraftLaneSelectBuffer& buffer);
    public System.Void UpdateOptimalLane(Game.Vehicles.WatercraftCurrentLane& currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData);
    public System.Void UpdateOptimalLane(Game.Vehicles.WatercraftNavigationLane& navLaneData);
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

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_WatercraftData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_WatercraftData;
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

- `public CalculateLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, System.Int32 index) : System.Void`  

```csharp
public void CalculateLaneCosts(WatercraftNavigationLane navLaneData, WatercraftNavigationLane nextNavLaneData, int index)
	{
		if ((navLaneData.m_Flags & (WatercraftLaneFlags.Reserved | WatercraftLaneFlags.FixedLane)) == 0 && m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			Owner owner = m_OwnerData[navLaneData.m_Lane];
			DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
			int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
			m_LaneSwitchCost = m_LaneSwitchBaseCost + math.select(1f, 5f, (slaveLane.m_Flags & SlaveLaneFlags.AllowChange) == 0);
			float laneObjectCost = math.abs(navLaneData.m_CurvePosition.y - navLaneData.m_CurvePosition.x) * 0.49f;
			if ((nextNavLaneData.m_Flags & (WatercraftLaneFlags.Reserved | WatercraftLaneFlags.FixedLane)) == 0 && m_SlaveLaneData.HasComponent(nextNavLaneData.m_Lane))
			{
				SlaveLane slaveLane2 = m_SlaveLaneData[nextNavLaneData.m_Lane];
				Owner owner2 = m_OwnerData[nextNavLaneData.m_Lane];
				DynamicBuffer<SubLane> dynamicBuffer2 = m_Lanes[owner2.m_Owner];
				int num2 = math.min(slaveLane2.m_MaxIndex, dynamicBuffer2.Length - 1);
				int num3 = m_BufferPos - (num2 - slaveLane2.m_MinIndex + 1);
				for (int i = slaveLane.m_MinIndex; i <= num; i++)
				{
					Entity subLane = dynamicBuffer[i].m_SubLane;
					Lane lane = m_LaneData[subLane];
					float num4 = 1000000f;
					int num5;
					int num6;
					if ((nextNavLaneData.m_Flags & WatercraftLaneFlags.GroupTarget) != 0)
					{
						num5 = slaveLane2.m_MinIndex;
						num6 = num2;
					}
					else
					{
						num5 = 100000;
						num6 = -100000;
						for (int j = slaveLane2.m_MinIndex; j <= num2; j++)
						{
							Lane lane2 = m_LaneData[dynamicBuffer2[j].m_SubLane];
							if (lane.m_EndNode.Equals(lane2.m_StartNode))
							{
								num5 = math.min(num5, j);
								num6 = j;
							}
						}
					}
					if (num5 <= num6)
					{
						int num7 = num3;
						for (int k = slaveLane2.m_MinIndex; k < num5; k++)
						{
							num4 = math.min(num4, m_Buffer[num7++] + GetLaneSwitchCost(num5 - k));
						}
						for (int l = num5; l <= num6; l++)
						{
							num4 = math.min(num4, m_Buffer[num7++]);
						}
						for (int m = num6 + 1; m <= num2; m++)
						{
							num4 = math.min(num4, m_Buffer[num7++] + GetLaneSwitchCost(m - num6));
						}
						num4 += CalculateLaneObjectCost(laneObjectCost, index, subLane, navLaneData.m_Flags);
						if (m_LaneReservationData.HasComponent(subLane))
						{
							num4 += GetLanePriorityCost(m_LaneReservationData[subLane].GetPriority());
						}
					}
					m_Buffer[m_BufferPos++] = num4;
				}
			}
			else if ((nextNavLaneData.m_Flags & WatercraftLaneFlags.TransformTarget) != 0)
			{
				for (int n = slaveLane.m_MinIndex; n <= num; n++)
				{
					Entity subLane2 = dynamicBuffer[n].m_SubLane;
					float num8 = CalculateLaneObjectCost(laneObjectCost, index, subLane2, navLaneData.m_Flags);
					if (m_LaneReservationData.HasComponent(subLane2))
					{
						num8 += GetLanePriorityCost(m_LaneReservationData[subLane2].GetPriority());
					}
					m_Buffer[m_BufferPos++] = num8;
				}
			}
			else
			{
				int num9 = 100000;
				int num10 = -100000;
				if ((nextNavLaneData.m_Flags & WatercraftLaneFlags.GroupTarget) != 0)
				{
					for (int num11 = slaveLane.m_MinIndex; num11 <= num; num11++)
					{
						if (dynamicBuffer[num11].m_SubLane == nextNavLaneData.m_Lane)
						{
							num9 = num11;
							num10 = num11;
							break;
						}
					}
				}
				else
				{
					Lane lane3 = m_LaneData[nextNavLaneData.m_Lane];
					for (int num12 = slaveLane.m_MinIndex; num12 <= num; num12++)
					{
						if (m_LaneData[dynamicBuffer[num12].m_SubLane].m_EndNode.Equals(lane3.m_StartNode))
						{
							num9 = math.min(num9, num12);
							num10 = num12;
						}
					}
				}
				for (int num13 = slaveLane.m_MinIndex; num13 <= num; num13++)
				{
					Entity subLane3 = dynamicBuffer[num13].m_SubLane;
					float num14 = 0f;
					if (num9 <= num10)
					{
						num14 += GetLaneSwitchCost(math.max(0, math.max(num9 - num13, num13 - num10)));
					}
					num14 += CalculateLaneObjectCost(laneObjectCost, index, subLane3, navLaneData.m_Flags);
					if (m_LaneReservationData.HasComponent(subLane3))
					{
						num14 += GetLanePriorityCost(m_LaneReservationData[subLane3].GetPriority());
					}
					m_Buffer[m_BufferPos++] = num14;
				}
			}
		}
		m_LaneSwitchBaseCost += 0.01f;
	}
```

- `public CalculateLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, System.Int32 index) : System.Void`  

```csharp
public void CalculateLaneCosts(WatercraftNavigationLane navLaneData, WatercraftNavigationLane nextNavLaneData, int index)
	{
		if ((navLaneData.m_Flags & (WatercraftLaneFlags.Reserved | WatercraftLaneFlags.FixedLane)) == 0 && m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			Owner owner = m_OwnerData[navLaneData.m_Lane];
			DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
			int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
			m_LaneSwitchCost = m_LaneSwitchBaseCost + math.select(1f, 5f, (slaveLane.m_Flags & SlaveLaneFlags.AllowChange) == 0);
			float laneObjectCost = math.abs(navLaneData.m_CurvePosition.y - navLaneData.m_CurvePosition.x) * 0.49f;
			if ((nextNavLaneData.m_Flags & (WatercraftLaneFlags.Reserved | WatercraftLaneFlags.FixedLane)) == 0 && m_SlaveLaneData.HasComponent(nextNavLaneData.m_Lane))
			{
				SlaveLane slaveLane2 = m_SlaveLaneData[nextNavLaneData.m_Lane];
				Owner owner2 = m_OwnerData[nextNavLaneData.m_Lane];
				DynamicBuffer<SubLane> dynamicBuffer2 = m_Lanes[owner2.m_Owner];
				int num2 = math.min(slaveLane2.m_MaxIndex, dynamicBuffer2.Length - 1);
				int num3 = m_BufferPos - (num2 - slaveLane2.m_MinIndex + 1);
				for (int i = slaveLane.m_MinIndex; i <= num; i++)
				{
					Entity subLane = dynamicBuffer[i].m_SubLane;
					Lane lane = m_LaneData[subLane];
					float num4 = 1000000f;
					int num5;
					int num6;
					if ((nextNavLaneData.m_Flags & WatercraftLaneFlags.GroupTarget) != 0)
					{
						num5 = slaveLane2.m_MinIndex;
						num6 = num2;
					}
					else
					{
						num5 = 100000;
						num6 = -100000;
						for (int j = slaveLane2.m_MinIndex; j <= num2; j++)
						{
							Lane lane2 = m_LaneData[dynamicBuffer2[j].m_SubLane];
							if (lane.m_EndNode.Equals(lane2.m_StartNode))
							{
								num5 = math.min(num5, j);
								num6 = j;
							}
						}
					}
					if (num5 <= num6)
					{
						int num7 = num3;
						for (int k = slaveLane2.m_MinIndex; k < num5; k++)
						{
							num4 = math.min(num4, m_Buffer[num7++] + GetLaneSwitchCost(num5 - k));
						}
						for (int l = num5; l <= num6; l++)
						{
							num4 = math.min(num4, m_Buffer[num7++]);
						}
						for (int m = num6 + 1; m <= num2; m++)
						{
							num4 = math.min(num4, m_Buffer[num7++] + GetLaneSwitchCost(m - num6));
						}
						num4 += CalculateLaneObjectCost(laneObjectCost, index, subLane, navLaneData.m_Flags);
						if (m_LaneReservationData.HasComponent(subLane))
						{
							num4 += GetLanePriorityCost(m_LaneReservationData[subLane].GetPriority());
						}
					}
					m_Buffer[m_BufferPos++] = num4;
				}
			}
			else if ((nextNavLaneData.m_Flags & WatercraftLaneFlags.TransformTarget) != 0)
			{
				for (int n = slaveLane.m_MinIndex; n <= num; n++)
				{
					Entity subLane2 = dynamicBuffer[n].m_SubLane;
					float num8 = CalculateLaneObjectCost(laneObjectCost, index, subLane2, navLaneData.m_Flags);
					if (m_LaneReservationData.HasComponent(subLane2))
					{
						num8 += GetLanePriorityCost(m_LaneReservationData[subLane2].GetPriority());
					}
					m_Buffer[m_BufferPos++] = num8;
				}
			}
			else
			{
				int num9 = 100000;
				int num10 = -100000;
				if ((nextNavLaneData.m_Flags & WatercraftLaneFlags.GroupTarget) != 0)
				{
					for (int num11 = slaveLane.m_MinIndex; num11 <= num; num11++)
					{
						if (dynamicBuffer[num11].m_SubLane == nextNavLaneData.m_Lane)
						{
							num9 = num11;
							num10 = num11;
							break;
						}
					}
				}
				else
				{
					Lane lane3 = m_LaneData[nextNavLaneData.m_Lane];
					for (int num12 = slaveLane.m_MinIndex; num12 <= num; num12++)
					{
						if (m_LaneData[dynamicBuffer[num12].m_SubLane].m_EndNode.Equals(lane3.m_StartNode))
						{
							num9 = math.min(num9, num12);
							num10 = num12;
						}
					}
				}
				for (int num13 = slaveLane.m_MinIndex; num13 <= num; num13++)
				{
					Entity subLane3 = dynamicBuffer[num13].m_SubLane;
					float num14 = 0f;
					if (num9 <= num10)
					{
						num14 += GetLaneSwitchCost(math.max(0, math.max(num9 - num13, num13 - num10)));
					}
					num14 += CalculateLaneObjectCost(laneObjectCost, index, subLane3, navLaneData.m_Flags);
					if (m_LaneReservationData.HasComponent(subLane3))
					{
						num14 += GetLanePriorityCost(m_LaneReservationData[subLane3].GetPriority());
					}
					m_Buffer[m_BufferPos++] = num14;
				}
			}
		}
		m_LaneSwitchBaseCost += 0.01f;
	}
```

- `private CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.WatercraftLaneFlags laneFlags) : System.Single`  

```csharp
private float CalculateLaneObjectCost(LaneObject laneObject, float laneObjectCost, WatercraftLaneFlags laneFlags)
	{
		if (!m_MovingData.HasComponent(laneObject.m_LaneObject))
		{
			if (m_WatercraftData.HasComponent(laneObject.m_LaneObject) && (m_WatercraftData[laneObject.m_LaneObject].m_Flags & WatercraftFlags.Queueing) != 0 && (laneFlags & WatercraftLaneFlags.Queue) != 0)
			{
				return laneObjectCost;
			}
			return math.lerp(10000000f, 9000000f, laneObject.m_CurvePosition.y);
		}
		return laneObjectCost;
	}
```

- `private CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.WatercraftLaneFlags laneFlags) : System.Single`  

```csharp
private float CalculateLaneObjectCost(LaneObject laneObject, float laneObjectCost, WatercraftLaneFlags laneFlags)
	{
		if (!m_MovingData.HasComponent(laneObject.m_LaneObject))
		{
			if (m_WatercraftData.HasComponent(laneObject.m_LaneObject) && (m_WatercraftData[laneObject.m_LaneObject].m_Flags & WatercraftFlags.Queueing) != 0 && (laneFlags & WatercraftLaneFlags.Queue) != 0)
			{
				return laneObjectCost;
			}
			return math.lerp(10000000f, 9000000f, laneObject.m_CurvePosition.y);
		}
		return laneObjectCost;
	}
```

- `private CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.WatercraftLaneFlags laneFlags) : System.Single`  

```csharp
private float CalculateLaneObjectCost(LaneObject laneObject, float laneObjectCost, WatercraftLaneFlags laneFlags)
	{
		if (!m_MovingData.HasComponent(laneObject.m_LaneObject))
		{
			if (m_WatercraftData.HasComponent(laneObject.m_LaneObject) && (m_WatercraftData[laneObject.m_LaneObject].m_Flags & WatercraftFlags.Queueing) != 0 && (laneFlags & WatercraftLaneFlags.Queue) != 0)
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

- `public DrawLaneCosts(Game.Vehicles.WatercraftCurrentLane currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  

```csharp
public void DrawLaneCosts(WatercraftNavigationLane navLaneData, ComponentLookup<Curve> curveData, GizmoBatcher gizmoBatcher)
	{
		if (m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			Owner owner = m_OwnerData[navLaneData.m_Lane];
			DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
			int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
			if ((navLaneData.m_Flags & (WatercraftLaneFlags.Reserved | WatercraftLaneFlags.FixedLane)) == 0)
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

- `public DrawLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  

```csharp
public void DrawLaneCosts(WatercraftNavigationLane navLaneData, ComponentLookup<Curve> curveData, GizmoBatcher gizmoBatcher)
	{
		if (m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			Owner owner = m_OwnerData[navLaneData.m_Lane];
			DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
			int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
			if ((navLaneData.m_Flags & (WatercraftLaneFlags.Reserved | WatercraftLaneFlags.FixedLane)) == 0)
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

- `public SetBuffer(Game.Simulation.WatercraftLaneSelectBuffer& buffer) : System.Void`  

```csharp
public void SetBuffer(ref WatercraftLaneSelectBuffer buffer)
	{
		m_Buffer = buffer.Ensure();
	}
```

- `public UpdateOptimalLane(Game.Vehicles.WatercraftCurrentLane& currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData) : System.Void`  

```csharp
public void UpdateOptimalLane(ref WatercraftNavigationLane navLaneData)
	{
		if (m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			if ((navLaneData.m_Flags & (WatercraftLaneFlags.FixedStart | WatercraftLaneFlags.Reserved | WatercraftLaneFlags.FixedLane)) == 0 && m_LaneData.HasComponent(m_PrevLane))
			{
				Owner owner = m_OwnerData[navLaneData.m_Lane];
				DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
				int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
				m_BufferPos -= num - slaveLane.m_MinIndex + 1;
				int num2 = 100000;
				int num3 = -100000;
				if ((navLaneData.m_Flags & WatercraftLaneFlags.GroupTarget) == 0)
				{
					Lane lane = m_LaneData[m_PrevLane];
					for (int i = slaveLane.m_MinIndex; i <= num; i++)
					{
						Lane lane2 = m_LaneData[dynamicBuffer[i].m_SubLane];
						if (lane.m_EndNode.Equals(lane2.m_StartNode))
						{
							num2 = math.min(num2, i);
							num3 = i;
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
				for (int j = slaveLane.m_MinIndex; j < num2; j++)
				{
					float num5 = m_Buffer[bufferPos++] + GetLaneSwitchCost(num2 - j);
					if (num5 < num4)
					{
						num4 = num5;
						index = j;
					}
				}
				for (int k = num2; k <= num3; k++)
				{
					float num6 = m_Buffer[bufferPos++];
					if (num6 < num4)
					{
						num4 = num6;
						index = k;
					}
				}
				for (int l = num3 + 1; l <= num; l++)
				{
					float num7 = m_Buffer[bufferPos++] + GetLaneSwitchCost(l - num3);
					if (num7 < num4)
					{
						num4 = num7;
						index = l;
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

- `public UpdateOptimalLane(Game.Vehicles.WatercraftNavigationLane& navLaneData) : System.Void`  

```csharp
public void UpdateOptimalLane(ref WatercraftNavigationLane navLaneData)
	{
		if (m_SlaveLaneData.HasComponent(navLaneData.m_Lane))
		{
			SlaveLane slaveLane = m_SlaveLaneData[navLaneData.m_Lane];
			if ((navLaneData.m_Flags & (WatercraftLaneFlags.FixedStart | WatercraftLaneFlags.Reserved | WatercraftLaneFlags.FixedLane)) == 0 && m_LaneData.HasComponent(m_PrevLane))
			{
				Owner owner = m_OwnerData[navLaneData.m_Lane];
				DynamicBuffer<SubLane> dynamicBuffer = m_Lanes[owner.m_Owner];
				int num = math.min(slaveLane.m_MaxIndex, dynamicBuffer.Length - 1);
				m_BufferPos -= num - slaveLane.m_MinIndex + 1;
				int num2 = 100000;
				int num3 = -100000;
				if ((navLaneData.m_Flags & WatercraftLaneFlags.GroupTarget) == 0)
				{
					Lane lane = m_LaneData[m_PrevLane];
					for (int i = slaveLane.m_MinIndex; i <= num; i++)
					{
						Lane lane2 = m_LaneData[dynamicBuffer[i].m_SubLane];
						if (lane.m_EndNode.Equals(lane2.m_StartNode))
						{
							num2 = math.min(num2, i);
							num3 = i;
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
				for (int j = slaveLane.m_MinIndex; j < num2; j++)
				{
					float num5 = m_Buffer[bufferPos++] + GetLaneSwitchCost(num2 - j);
					if (num5 < num4)
					{
						num4 = num5;
						index = j;
					}
				}
				for (int k = num2; k <= num3; k++)
				{
					float num6 = m_Buffer[bufferPos++];
					if (num6 < num4)
					{
						num4 = num6;
						index = k;
					}
				}
				for (int l = num3 + 1; l <= num; l++)
				{
					float num7 = m_Buffer[bufferPos++] + GetLaneSwitchCost(l - num3);
					if (num7 < num4)
					{
						num4 = num7;
						index = l;
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


