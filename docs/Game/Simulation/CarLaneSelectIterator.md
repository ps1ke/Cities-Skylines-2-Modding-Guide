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
public System.Void CalculateLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, System.Int32 index);
```

- `public CalculateLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, System.Int32 index) : System.Void`  

```csharp
public System.Void CalculateLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, System.Int32 index);
```

- `private CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.CarLaneFlags laneFlags) : System.Single`  

```csharp
private System.Single CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.CarLaneFlags laneFlags);
```

- `private CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.CarLaneFlags laneFlags) : System.Single`  

```csharp
private System.Single CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.CarLaneFlags laneFlags);
```

- `private CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.CarLaneFlags laneFlags) : System.Single`  

```csharp
private System.Single CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.CarLaneFlags laneFlags);
```

- `private DrawLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePos, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher, System.Single cost) : System.Void`  

```csharp
private System.Void DrawLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePos, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher, System.Single cost);
```

- `public DrawLaneCosts(Game.Vehicles.CarCurrentLane currentLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  

```csharp
public System.Void DrawLaneCosts(Game.Vehicles.CarCurrentLane currentLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher);
```

- `public DrawLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  

```csharp
public System.Void DrawLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher);
```

- `private GetLaneDriveCost(Game.Net.CarLaneFlags flags) : System.Single`  

```csharp
private System.Single GetLaneDriveCost(Game.Net.CarLaneFlags flags);
```

- `private GetLanePriorityCost(System.Int32 lanePriority) : System.Single`  

```csharp
private System.Single GetLanePriorityCost(System.Int32 lanePriority);
```

- `private GetLaneSwitchCost(System.Int32 numLanes) : System.Single`  

```csharp
private System.Single GetLaneSwitchCost(System.Int32 numLanes);
```

- `private GetTurnFlags(Unity.Entities.Entity currentLane, System.Int32 currentIndex, System.Int32 changeIndex) : Game.Vehicles.CarLaneFlags`  

```csharp
private Game.Vehicles.CarLaneFlags GetTurnFlags(Unity.Entities.Entity currentLane, System.Int32 currentIndex, System.Int32 changeIndex);
```

- `public SetBuffer(Game.Simulation.CarLaneSelectBuffer& buffer) : System.Void`  

```csharp
public System.Void SetBuffer(Game.Simulation.CarLaneSelectBuffer& buffer);
```

- `public UpdateOptimalLane(Game.Vehicles.CarCurrentLane& currentLane, Game.Vehicles.CarNavigationLane nextNavLaneData) : System.Void`  

```csharp
public System.Void UpdateOptimalLane(Game.Vehicles.CarCurrentLane& currentLane, Game.Vehicles.CarNavigationLane nextNavLaneData);
```

- `public UpdateOptimalLane(Game.Vehicles.CarNavigationLane& navLaneData) : System.Void`  

```csharp
public System.Void UpdateOptimalLane(Game.Vehicles.CarNavigationLane& navLaneData);
```


