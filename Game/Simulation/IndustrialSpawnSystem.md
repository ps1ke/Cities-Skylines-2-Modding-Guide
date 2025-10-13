# Game.Simulation.IndustrialSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IndustrialSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_StorageCompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_ExtractorQuery;
    private Unity.Entities.EntityQuery m_ExtractorCompanyQuery;
    private Unity.Entities.EntityQuery m_ExistingIndustrialQuery;
    private Unity.Entities.EntityQuery m_ExistingExtractorQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.IndustrialSpawnSystem+TypeHandle __TypeHandle;

    public IndustrialSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_StorageCompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_StorageCompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorCompanyQuery;
```

- `private Unity.Entities.EntityQuery m_ExistingIndustrialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExistingIndustrialQuery;
```

- `private Unity.Entities.EntityQuery m_ExistingExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExistingExtractorQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.IndustrialSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.IndustrialSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public IndustrialSpawnSystem()`  

```csharp
public IndustrialSpawnSystem();
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


## Nested types

- `Game.Simulation.IndustrialSpawnSystem+CheckSpawnJob`  
- `Game.Simulation.IndustrialSpawnSystem+TypeHandle`  

