# Game.Simulation.TrafficLightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficLightSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_TrafficLightQuery;
    private Game.Simulation.TrafficLightSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public TrafficLightSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void UpdateLaneSignal(Game.Net.TrafficLights trafficLights, Game.Net.LaneSignal& laneSignal);
    public static System.Void UpdateMoveableBridge(Game.Net.TrafficLights trafficLights, Game.Objects.Transform transform, Game.Prefabs.MoveableBridgeData moveableBridgeData, Game.Common.PointOfInterest& pointOfInterest);
    public static System.Void UpdateTrafficLightState(Game.Net.TrafficLights trafficLights, Game.Objects.TrafficLight& trafficLight);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_TrafficLightQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrafficLightQuery;
```

- `private Game.Simulation.TrafficLightSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrafficLightSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public TrafficLightSystem()`  

```csharp
public TrafficLightSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public static UpdateLaneSignal(Game.Net.TrafficLights trafficLights, Game.Net.LaneSignal& laneSignal) : System.Void`  

```csharp
public static System.Void UpdateLaneSignal(Game.Net.TrafficLights trafficLights, Game.Net.LaneSignal& laneSignal);
```

- `public static UpdateMoveableBridge(Game.Net.TrafficLights trafficLights, Game.Objects.Transform transform, Game.Prefabs.MoveableBridgeData moveableBridgeData, Game.Common.PointOfInterest& pointOfInterest) : System.Void`  

```csharp
public static System.Void UpdateMoveableBridge(Game.Net.TrafficLights trafficLights, Game.Objects.Transform transform, Game.Prefabs.MoveableBridgeData moveableBridgeData, Game.Common.PointOfInterest& pointOfInterest);
```

- `public static UpdateTrafficLightState(Game.Net.TrafficLights trafficLights, Game.Objects.TrafficLight& trafficLight) : System.Void`  

```csharp
public static System.Void UpdateTrafficLightState(Game.Net.TrafficLights trafficLights, Game.Objects.TrafficLight& trafficLight);
```


## Nested types

- `Game.Simulation.TrafficLightSystem+UpdateTrafficLightsJob`  
- `Game.Simulation.TrafficLightSystem+TypeHandle`  

