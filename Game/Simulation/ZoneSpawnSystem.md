# Game.Simulation.ZoneSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneSpawnSystem : Game.GameSystemBase
{
    private System.Boolean <debugFastSpawn>k__BackingField;
    private Game.Prefabs.ZoneSystem m_ZoneSystem;
    private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.GroundPollutionSystem m_PollutionSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Zones.SearchSystem m_SearchSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_LotQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_ProcessQuery;
    private Unity.Entities.EntityQuery m_BuildingConfigurationQuery;
    private Unity.Entities.EntityArchetype m_DefinitionArchetype;
    private Game.Simulation.ZoneSpawnSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1944910157_0;

    public System.Boolean debugFastSpawn { get; set; }

    public ZoneSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `private Game.Prefabs.ZoneSystem m_ZoneSystem`  

```csharp
private Game.Prefabs.ZoneSystem m_ZoneSystem;
```

- `private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem`  

```csharp
private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
```

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_PollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_PollutionSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Zones.SearchSystem m_SearchSystem`  

```csharp
private Game.Zones.SearchSystem m_SearchSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_LotQuery`  

```csharp
private Unity.Entities.EntityQuery m_LotQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ProcessQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingConfigurationQuery;
```

- `private Unity.Entities.EntityArchetype m_DefinitionArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DefinitionArchetype;
```

- `private Game.Simulation.ZoneSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ZoneSpawnSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1944910157_0`  

```csharp
private Unity.Entities.EntityQuery __query_1944910157_0;
```


## Properties

- `public System.Boolean debugFastSpawn { get; set }`  

```csharp
public System.Boolean debugFastSpawn { get; set; }
```


## Constructors

- `public ZoneSpawnSystem()`  

```csharp
public ZoneSpawnSystem();
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

- `Game.Simulation.ZoneSpawnSystem+SpawnLocation`  
- `Game.Simulation.ZoneSpawnSystem+EvaluateSpawnAreas`  
- `Game.Simulation.ZoneSpawnSystem+SpawnBuildingJob`  
- `Game.Simulation.ZoneSpawnSystem+TypeHandle`  

