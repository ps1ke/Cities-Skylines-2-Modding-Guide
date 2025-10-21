# Game.Simulation.SimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ISimulationSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SimulationSystem : Game.GameSystemBase, Game.Simulation.ISimulationSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private System.UInt32 <frameIndex>k__BackingField;
    private System.Single <frameTime>k__BackingField;
    private System.Single <smoothSpeed>k__BackingField;
    private System.Single <frameDuration>k__BackingField;
    private Game.Simulation.SimulationSystem+PerformancePreference <performancePreference>k__BackingField;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Pathfind.PathfindResultSystem m_PathfindResultSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private System.Single m_Timer;
    private System.Single m_LastSpeed;
    private System.Single m_SelectedSpeed;
    private System.Int32 m_LoadingCount;
    private System.Int32 m_StepCount;
    private System.Boolean m_IsLoading;
    private Unity.Jobs.JobHandle m_WatchDeps;
    private System.Diagnostics.Stopwatch m_Stopwatch;
    public static const System.Single PENDING_FRAMES_SPEED_FACTOR;
    private static const System.Int32 LOADING_COUNT;
    public static const System.String kLoadingTask;

    public System.UInt32 frameIndex { get; private set; }
    public System.Single frameTime { get; private set; }
    public System.Single selectedSpeed { get; set; }
    public System.Single smoothSpeed { get; private set; }
    public System.Single loadingProgress { get; private set; }
    public System.Single frameDuration { get; private set; }
    public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set; }

    public SimulationSystem();

    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateLoadingProgress();
}
```


## Fields

- `private System.UInt32 <frameIndex>k__BackingField`  

```csharp
private System.UInt32 <frameIndex>k__BackingField;
```

- `private System.Single <frameTime>k__BackingField`  

```csharp
private System.Single <frameTime>k__BackingField;
```

- `private System.Single <smoothSpeed>k__BackingField`  

```csharp
private System.Single <smoothSpeed>k__BackingField;
```

- `private System.Single <frameDuration>k__BackingField`  

```csharp
private System.Single <frameDuration>k__BackingField;
```

- `private Game.Simulation.SimulationSystem+PerformancePreference <performancePreference>k__BackingField`  

```csharp
private Game.Simulation.SimulationSystem+PerformancePreference <performancePreference>k__BackingField;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Pathfind.PathfindResultSystem m_PathfindResultSystem`  

```csharp
private Game.Pathfind.PathfindResultSystem m_PathfindResultSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private System.Single m_Timer`  

```csharp
private System.Single m_Timer;
```

- `private System.Single m_LastSpeed`  

```csharp
private System.Single m_LastSpeed;
```

- `private System.Single m_SelectedSpeed`  

```csharp
private System.Single m_SelectedSpeed;
```

- `private System.Int32 m_LoadingCount`  

```csharp
private System.Int32 m_LoadingCount;
```

- `private System.Int32 m_StepCount`  

```csharp
private System.Int32 m_StepCount;
```

- `private System.Boolean m_IsLoading`  

```csharp
private System.Boolean m_IsLoading;
```

- `private Unity.Jobs.JobHandle m_WatchDeps`  

```csharp
private Unity.Jobs.JobHandle m_WatchDeps;
```

- `private System.Diagnostics.Stopwatch m_Stopwatch`  

```csharp
private System.Diagnostics.Stopwatch m_Stopwatch;
```

- `public static const System.Single PENDING_FRAMES_SPEED_FACTOR`  

```csharp
public static const System.Single PENDING_FRAMES_SPEED_FACTOR;
```

- `private static const System.Int32 LOADING_COUNT`  

```csharp
private static const System.Int32 LOADING_COUNT;
```

- `public static const System.String kLoadingTask`  

```csharp
public static const System.String kLoadingTask;
```


## Properties

- `public System.UInt32 frameIndex { get; private set }`  

```csharp
public System.UInt32 frameIndex { get; private set; }
```

- `public System.Single frameTime { get; private set }`  

```csharp
public System.Single frameTime { get; private set; }
```

- `public System.Single selectedSpeed { get; set }`  

```csharp
public System.Single selectedSpeed { get; set; }
```

- `public System.Single smoothSpeed { get; private set }`  

```csharp
public System.Single smoothSpeed { get; private set; }
```

- `public System.Single loadingProgress { get; private set }`  

```csharp
public System.Single loadingProgress { get; private set; }
```

- `public System.Single frameDuration { get; private set }`  

```csharp
public System.Single frameDuration { get; private set; }
```

- `public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set }`  

```csharp
public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set; }
```


## Constructors

- `public SimulationSystem()`  

```csharp
public SimulationSystem();
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private UpdateLoadingProgress() : System.Void`  

```csharp
private System.Void UpdateLoadingProgress();
```


## Nested types

- `Game.Simulation.SimulationSystem+PerformancePreference`  
- `Game.Simulation.SimulationSystem+SimulationEndTimeJob`  

