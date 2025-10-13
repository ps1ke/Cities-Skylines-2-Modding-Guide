# Game.Simulation.WindSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.Wind>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Code

```csharp
public class WindSystem : Game.Simulation.CellMapSystem<Game.Simulation.Wind>, Colossal.Serialization.Entities.IJobSerializable
{
    public Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
    public Game.Rendering.WindTextureSystem m_WindTextureSystem;
    public Game.Simulation.TerrainSystem m_TerrainSystem;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdateInterval;

    public Unity.Mathematics.int2 TextureSize { get; }

    public WindSystem();

    public virtual Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static Game.Simulation.Wind GetWind(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.Wind> windMap);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `public Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  

```csharp
public Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
```

- `public Game.Rendering.WindTextureSystem m_WindTextureSystem`  

```csharp
public Game.Rendering.WindTextureSystem m_WindTextureSystem;
```

- `public Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
public Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static readonly System.Int32 kUpdateInterval`  

```csharp
public static readonly System.Int32 kUpdateInterval;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public WindSystem()`  

```csharp
public WindSystem();
```


## Methods

- `public virtual Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static GetWind(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.Wind> windMap) : Game.Simulation.Wind`  

```csharp
public static Game.Simulation.Wind GetWind(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.Wind> windMap);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.WindSystem+WindCopyJob`  

