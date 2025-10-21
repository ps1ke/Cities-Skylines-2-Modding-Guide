# Game.Simulation.WaterPumpingStationAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPumpingStationAISystem : Game.GameSystemBase
{
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_PumpQuery;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Game.Simulation.WaterPumpingStationAISystem+TypeHandle __TypeHandle;

    public WaterPumpingStationAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetSurfaceWaterAvailability(Unity.Mathematics.float3 position, Game.Prefabs.AllowedWaterTypes allowedTypes, Game.Simulation.WaterSurfaceData waterSurfaceData, System.Single effectiveDepth);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_PumpQuery`  

```csharp
private Unity.Entities.EntityQuery m_PumpQuery;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Game.Simulation.WaterPumpingStationAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPumpingStationAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPumpingStationAISystem()`  

```csharp
public WaterPumpingStationAISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetSurfaceWaterAvailability(Unity.Mathematics.float3 position, Game.Prefabs.AllowedWaterTypes allowedTypes, Game.Simulation.WaterSurfaceData waterSurfaceData, System.Single effectiveDepth) : System.Single`  

```csharp
public static System.Single GetSurfaceWaterAvailability(Unity.Mathematics.float3 position, Game.Prefabs.AllowedWaterTypes allowedTypes, Game.Simulation.WaterSurfaceData waterSurfaceData, System.Single effectiveDepth);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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


## Nested types

- `Game.Simulation.WaterPumpingStationAISystem+PumpTickJob`  
- `Game.Simulation.WaterPumpingStationAISystem+TypeHandle`  

