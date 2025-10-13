# Game.Net.AirwaySystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AirwaySystem : Game.GameSystemBase, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_AirplaneConnectionQuery;
    private Unity.Entities.EntityQuery m_OldConnectionQuery;
    private Game.Net.AirwayHelpers+AirwayData m_AirwayData;
    private Game.Net.AirwaySystem+TypeHandle __TypeHandle;
    private static const System.Single TERRAIN_SIZE;
    private static const System.Int32 HELICOPTER_GRID_WIDTH;
    private static const System.Int32 HELICOPTER_GRID_LENGTH;
    private static const System.Single HELICOPTER_CELL_SIZE;
    private static const System.Single HELICOPTER_PATH_HEIGHT;
    private static const System.Int32 AIRPLANE_GRID_WIDTH;
    private static const System.Int32 AIRPLANE_GRID_LENGTH;
    private static const System.Single AIRPLANE_CELL_SIZE;
    private static const System.Single AIRPLANE_PATH_HEIGHT;

    public AirwaySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
    public Game.Net.AirwayHelpers+AirwayData GetAirwayData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public Unity.Jobs.JobHandle Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_AirplaneConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_AirplaneConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_OldConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OldConnectionQuery;
```

- `private Game.Net.AirwayHelpers+AirwayData m_AirwayData`  

```csharp
private Game.Net.AirwayHelpers+AirwayData m_AirwayData;
```

- `private Game.Net.AirwaySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.AirwaySystem+TypeHandle __TypeHandle;
```

- `private static const System.Single TERRAIN_SIZE`  

```csharp
private static const System.Single TERRAIN_SIZE;
```

- `private static const System.Int32 HELICOPTER_GRID_WIDTH`  

```csharp
private static const System.Int32 HELICOPTER_GRID_WIDTH;
```

- `private static const System.Int32 HELICOPTER_GRID_LENGTH`  

```csharp
private static const System.Int32 HELICOPTER_GRID_LENGTH;
```

- `private static const System.Single HELICOPTER_CELL_SIZE`  

```csharp
private static const System.Single HELICOPTER_CELL_SIZE;
```

- `private static const System.Single HELICOPTER_PATH_HEIGHT`  

```csharp
private static const System.Single HELICOPTER_PATH_HEIGHT;
```

- `private static const System.Int32 AIRPLANE_GRID_WIDTH`  

```csharp
private static const System.Int32 AIRPLANE_GRID_WIDTH;
```

- `private static const System.Int32 AIRPLANE_GRID_LENGTH`  

```csharp
private static const System.Int32 AIRPLANE_GRID_LENGTH;
```

- `private static const System.Single AIRPLANE_CELL_SIZE`  

```csharp
private static const System.Single AIRPLANE_CELL_SIZE;
```

- `private static const System.Single AIRPLANE_PATH_HEIGHT`  

```csharp
private static const System.Single AIRPLANE_PATH_HEIGHT;
```


## Constructors

- `public AirwaySystem()`  

```csharp
public AirwaySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
```

- `public GetAirwayData() : Game.Net.AirwayHelpers+AirwayData`  

```csharp
public Game.Net.AirwayHelpers+AirwayData GetAirwayData();
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

- `public Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Net.AirwaySystem+SerializeJob<TWriter>`  
- `Game.Net.AirwaySystem+DeserializeJob<TReader>`  
- `Game.Net.AirwaySystem+SetDefaultsJob`  
- `Game.Net.AirwaySystem+GenerateAirwayLanesJob`  
- `Game.Net.AirwaySystem+TypeHandle`  

