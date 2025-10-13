# Game.Simulation.StreetLightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StreetLightSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_StreetLightQuery;
    private Game.Simulation.StreetLightSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public StreetLightSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Net.Road road);
    public static System.Void UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Buildings.Building building);
    public static System.Void UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Vehicles.Watercraft watercraft);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_StreetLightQuery`  

```csharp
private Unity.Entities.EntityQuery m_StreetLightQuery;
```

- `private Game.Simulation.StreetLightSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.StreetLightSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public StreetLightSystem()`  

```csharp
public StreetLightSystem();
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

- `public static UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Net.Road road) : System.Void`  

```csharp
public static System.Void UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Net.Road road);
```

- `public static UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Buildings.Building building) : System.Void`  

```csharp
public static System.Void UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Buildings.Building building);
```

- `public static UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Vehicles.Watercraft watercraft) : System.Void`  

```csharp
public static System.Void UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Vehicles.Watercraft watercraft);
```


## Nested types

- `Game.Simulation.StreetLightSystem+UpdateStreetLightsJob`  
- `Game.Simulation.StreetLightSystem+TypeHandle`  

