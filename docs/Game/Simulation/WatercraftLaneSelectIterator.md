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
public System.Void CalculateLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, System.Int32 index);
```

- `public CalculateLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, System.Int32 index) : System.Void`  

```csharp
public System.Void CalculateLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, System.Int32 index);
```

- `private CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.WatercraftLaneFlags laneFlags) : System.Single`  

```csharp
private System.Single CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.WatercraftLaneFlags laneFlags);
```

- `private CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.WatercraftLaneFlags laneFlags) : System.Single`  

```csharp
private System.Single CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.WatercraftLaneFlags laneFlags);
```

- `private CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.WatercraftLaneFlags laneFlags) : System.Single`  

```csharp
private System.Single CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.WatercraftLaneFlags laneFlags);
```

- `private DrawLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePos, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher, System.Single cost) : System.Void`  

```csharp
private System.Void DrawLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePos, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher, System.Single cost);
```

- `public DrawLaneCosts(Game.Vehicles.WatercraftCurrentLane currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  

```csharp
public System.Void DrawLaneCosts(Game.Vehicles.WatercraftCurrentLane currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher);
```

- `public DrawLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  

```csharp
public System.Void DrawLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher);
```

- `private GetLanePriorityCost(System.Int32 lanePriority) : System.Single`  

```csharp
private System.Single GetLanePriorityCost(System.Int32 lanePriority);
```

- `private GetLaneSwitchCost(System.Int32 numLanes) : System.Single`  

```csharp
private System.Single GetLaneSwitchCost(System.Int32 numLanes);
```

- `public SetBuffer(Game.Simulation.WatercraftLaneSelectBuffer& buffer) : System.Void`  

```csharp
public System.Void SetBuffer(Game.Simulation.WatercraftLaneSelectBuffer& buffer);
```

- `public UpdateOptimalLane(Game.Vehicles.WatercraftCurrentLane& currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData) : System.Void`  

```csharp
public System.Void UpdateOptimalLane(Game.Vehicles.WatercraftCurrentLane& currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData);
```

- `public UpdateOptimalLane(Game.Vehicles.WatercraftNavigationLane& navLaneData) : System.Void`  

```csharp
public System.Void UpdateOptimalLane(Game.Vehicles.WatercraftNavigationLane& navLaneData);
```


