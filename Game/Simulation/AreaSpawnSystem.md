# Game.Simulation.AreaSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaSpawnSystem : Game.GameSystemBase
{
    private System.Boolean <debugFastSpawn>k__BackingField;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_AreaQuery;
    private Unity.Entities.EntityArchetype m_DefinitionArchetype;
    private Game.Simulation.AreaSpawnSystem+TypeHandle __TypeHandle;

    public System.Boolean debugFastSpawn { get; set; }

    public AreaSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <debugFastSpawn>k__BackingField`  

```csharp
private System.Boolean <debugFastSpawn>k__BackingField;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_AreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaQuery;
```

- `private Unity.Entities.EntityArchetype m_DefinitionArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DefinitionArchetype;
```

- `private Game.Simulation.AreaSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AreaSpawnSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean debugFastSpawn { get; set }`  

```csharp
public System.Boolean debugFastSpawn { get; set; }
```


## Constructors

- `public AreaSpawnSystem()`  

```csharp
public AreaSpawnSystem();
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

- `Game.Simulation.AreaSpawnSystem+AreaSpawnJob`  
- `Game.Simulation.AreaSpawnSystem+TypeHandle`  

