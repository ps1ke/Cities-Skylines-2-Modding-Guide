# Game.Tools.ObjectToolBaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class abstract public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public abstract class ObjectToolBaseSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    protected Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    protected Game.Objects.SearchSystem m_ObjectSearchSystem;
    protected Game.Simulation.WaterSystem m_WaterSystem;
    protected Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Tools.ObjectToolBaseSystem+TypeHandle __TypeHandle;

    protected ObjectToolBaseSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected Unity.Jobs.JobHandle CreateDefinitions(Unity.Entities.Entity objectPrefab, Unity.Entities.Entity transformPrefab, Unity.Entities.Entity brushPrefab, Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity laneEditor, Unity.Entities.Entity theme, Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeReference<Game.Tools.ObjectToolBaseSystem+AttachmentData> attachmentPrefab, System.Boolean editorMode, System.Boolean lefthandTraffic, System.Boolean removing, System.Boolean stamping, System.Single brushSize, System.Single brushAngle, System.Single brushStrength, System.Single distance, System.Single deltaTime, Game.Common.RandomSeed randomSeed, Game.Tools.Snap snap, Game.Tools.AgeMask ageMask, Unity.Jobs.JobHandle inputDeps);
    public static System.Int32 GetFirstNodeIndex(Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> nodes, Unity.Mathematics.int2 range);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
}
```


## Fields

- `protected Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
protected Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `protected Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
protected Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `protected Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
protected Game.Simulation.WaterSystem m_WaterSystem;
```

- `protected Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
protected Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Tools.ObjectToolBaseSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ObjectToolBaseSystem+TypeHandle __TypeHandle;
```


## Constructors

- `protected ObjectToolBaseSystem()`  

```csharp
protected ObjectToolBaseSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected CreateDefinitions(Unity.Entities.Entity objectPrefab, Unity.Entities.Entity transformPrefab, Unity.Entities.Entity brushPrefab, Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity laneEditor, Unity.Entities.Entity theme, Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeReference<Game.Tools.ObjectToolBaseSystem+AttachmentData> attachmentPrefab, System.Boolean editorMode, System.Boolean lefthandTraffic, System.Boolean removing, System.Boolean stamping, System.Single brushSize, System.Single brushAngle, System.Single brushStrength, System.Single distance, System.Single deltaTime, Game.Common.RandomSeed randomSeed, Game.Tools.Snap snap, Game.Tools.AgeMask ageMask, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected Unity.Jobs.JobHandle CreateDefinitions(Unity.Entities.Entity objectPrefab, Unity.Entities.Entity transformPrefab, Unity.Entities.Entity brushPrefab, Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity laneEditor, Unity.Entities.Entity theme, Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeReference<Game.Tools.ObjectToolBaseSystem+AttachmentData> attachmentPrefab, System.Boolean editorMode, System.Boolean lefthandTraffic, System.Boolean removing, System.Boolean stamping, System.Single brushSize, System.Single brushAngle, System.Single brushStrength, System.Single distance, System.Single deltaTime, Game.Common.RandomSeed randomSeed, Game.Tools.Snap snap, Game.Tools.AgeMask ageMask, Unity.Jobs.JobHandle inputDeps);
```

- `public static GetFirstNodeIndex(Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> nodes, Unity.Mathematics.int2 range) : System.Int32`  

```csharp
public static System.Int32 GetFirstNodeIndex(Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> nodes, Unity.Mathematics.int2 range);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```


## Nested types

- `Game.Tools.ObjectToolBaseSystem+AttachmentData`  
- `Game.Tools.ObjectToolBaseSystem+CreateDefinitionsJob`  
- `Game.Tools.ObjectToolBaseSystem+TypeHandle`  

