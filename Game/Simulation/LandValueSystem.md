# Game.Simulation.LandValueSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.LandValueCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LandValueSystem : Game.Simulation.CellMapSystem<Game.Simulation.LandValueCell>, Colossal.Serialization.Entities.IJobSerializable
{
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Unity.Entities.EntityQuery m_NodeGroup;
    private Unity.Entities.EntityQuery m_AttractivenessParameterQuery;
    private Unity.Entities.EntityQuery m_LandValueParameterQuery;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.LandValueSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public LandValueSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static System.Int32 GetCellIndex(Unity.Mathematics.float3 pos);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Unity.Entities.EntityQuery m_NodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_NodeGroup;
```

- `private Unity.Entities.EntityQuery m_AttractivenessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_AttractivenessParameterQuery;
```

- `private Unity.Entities.EntityQuery m_LandValueParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueParameterQuery;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem`  

```csharp
private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.LandValueSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LandValueSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public LandValueSystem()`  

```csharp
public LandValueSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public static GetCellIndex(Unity.Mathematics.float3 pos) : System.Int32`  

```csharp
public static System.Int32 GetCellIndex(Unity.Mathematics.float3 pos);
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

- `Game.Simulation.LandValueSystem+NetIterator`  
- `Game.Simulation.LandValueSystem+LandValueMapUpdateJob`  
- `Game.Simulation.LandValueSystem+EdgeUpdateJob`  
- `Game.Simulation.LandValueSystem+TypeHandle`  

