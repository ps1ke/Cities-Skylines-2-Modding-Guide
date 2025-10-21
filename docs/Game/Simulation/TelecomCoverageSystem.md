# Game.Simulation.TelecomCoverageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TelecomCoverage>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TelecomCoverageSystem : Game.Simulation.CellMapSystem<Game.Simulation.TelecomCoverage>, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_DensityQuery;
    private Unity.Entities.EntityQuery m_FacilityQuery;
    private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status;
    private Game.Simulation.TelecomCoverageSystem+TypeHandle __TypeHandle;
    public static const System.Int32 TEXTURE_SIZE;

    public Unity.Mathematics.int2 TextureSize { get; }

    public TelecomCoverageSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_DensityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DensityQuery;
```

- `private Unity.Entities.EntityQuery m_FacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_FacilityQuery;
```

- `private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status`  

```csharp
private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status;
```

- `private Game.Simulation.TelecomCoverageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TelecomCoverageSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 TEXTURE_SIZE`  

```csharp
public static const System.Int32 TEXTURE_SIZE;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public TelecomCoverageSystem()`  

```csharp
public TelecomCoverageSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.TelecomCoverageSystem+CellDensityData`  
- `Game.Simulation.TelecomCoverageSystem+CellFacilityData`  
- `Game.Simulation.TelecomCoverageSystem+TelecomCoverageJob`  
- `Game.Simulation.TelecomCoverageSystem+TypeHandle`  

