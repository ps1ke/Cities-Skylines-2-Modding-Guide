# Game.Simulation.LodgingProviderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LodgingProviderSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityQuery m_ProviderQuery;
    private Unity.Entities.EntityQuery m_LeisureParameterQuery;
    private Game.Simulation.LodgingProviderSystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kUpdatesPerDay;

    public LodgingProviderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetRoomCount(Unity.Mathematics.int2 lotSize, System.Int32 level, Game.Prefabs.BuildingPropertyData buildingPropertyData);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
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

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityQuery m_ProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProviderQuery;
```

- `private Unity.Entities.EntityQuery m_LeisureParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureParameterQuery;
```

- `private Game.Simulation.LodgingProviderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LodgingProviderSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kUpdatesPerDay`  

```csharp
private static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public LodgingProviderSystem()`  

```csharp
public LodgingProviderSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetRoomCount(Unity.Mathematics.int2 lotSize, System.Int32 level, Game.Prefabs.BuildingPropertyData buildingPropertyData) : System.Int32`  

```csharp
public static System.Int32 GetRoomCount(Unity.Mathematics.int2 lotSize, System.Int32 level, Game.Prefabs.BuildingPropertyData buildingPropertyData);
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


## Nested types

- `Game.Simulation.LodgingProviderSystem+LodgingProviderJob`  
- `Game.Simulation.LodgingProviderSystem+TypeHandle`  

