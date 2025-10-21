# Game.Simulation.GroundHeightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GroundHeightSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Areas.GeometrySystem m_AreaGeometrySystem;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_NewUpdates;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_PendingUpdates;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadingUpdates;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadyUpdates;
    private Unity.Jobs.JobHandle m_UpdateDeps;
    private Game.Simulation.GroundHeightSystem+LoadHeightsState m_LoadHeightsState;
    private Game.Simulation.GroundHeightSystem+TypeHandle __TypeHandle;

    public GroundHeightSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AfterReadHeights();
    public System.Void BeforeReadHeights();
    public System.Void BeforeUpdateHeights();
    public Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdateBuffer();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public Unity.Jobs.JobHandle Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Areas.GeometrySystem m_AreaGeometrySystem`  

```csharp
private Game.Areas.GeometrySystem m_AreaGeometrySystem;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_NewUpdates`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_NewUpdates;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_PendingUpdates`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_PendingUpdates;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadingUpdates`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadingUpdates;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadyUpdates`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadyUpdates;
```

- `private Unity.Jobs.JobHandle m_UpdateDeps`  

```csharp
private Unity.Jobs.JobHandle m_UpdateDeps;
```

- `private Game.Simulation.GroundHeightSystem+LoadHeightsState m_LoadHeightsState`  

```csharp
private Game.Simulation.GroundHeightSystem+LoadHeightsState m_LoadHeightsState;
```

- `private Game.Simulation.GroundHeightSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.GroundHeightSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GroundHeightSystem()`  

```csharp
public GroundHeightSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AfterReadHeights() : System.Void`  

```csharp
public System.Void AfterReadHeights();
```

- `public BeforeReadHeights() : System.Void`  

```csharp
public System.Void BeforeReadHeights();
```

- `public BeforeUpdateHeights() : System.Void`  

```csharp
public System.Void BeforeUpdateHeights();
```

- `public Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
```

- `public GetUpdateBuffer() : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdateBuffer();
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
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

- `Game.Simulation.GroundHeightSystem+LoadHeightsState`  
- `Game.Simulation.GroundHeightSystem+SerializeJob<TWriter>`  
- `Game.Simulation.GroundHeightSystem+DeserializeJob<TReader>`  
- `Game.Simulation.GroundHeightSystem+SetDefaultsJob`  
- `Game.Simulation.GroundHeightSystem+BoundsFindJob`  
- `Game.Simulation.GroundHeightSystem+DequeueJob`  
- `Game.Simulation.GroundHeightSystem+UpdateHeightsJob`  
- `Game.Simulation.GroundHeightSystem+TypeHandle`  

