# Game.Simulation.SimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ISimulationSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.UInt32 <frameIndex>k__BackingField`  
- `private System.Single <frameTime>k__BackingField`  
- `private System.Single <smoothSpeed>k__BackingField`  
- `private System.Single <frameDuration>k__BackingField`  
- `private Game.Simulation.SimulationSystem+PerformancePreference <performancePreference>k__BackingField`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Pathfind.PathfindResultSystem m_PathfindResultSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private System.Single m_Timer`  
- `private System.Single m_LastSpeed`  
- `private System.Single m_SelectedSpeed`  
- `private System.Int32 m_LoadingCount`  
- `private System.Int32 m_StepCount`  
- `private System.Boolean m_IsLoading`  
- `private Unity.Jobs.JobHandle m_WatchDeps`  
- `private System.Diagnostics.Stopwatch m_Stopwatch`  
- `public static const System.Single PENDING_FRAMES_SPEED_FACTOR`  
- `private static const System.Int32 LOADING_COUNT`  
- `public static const System.String kLoadingTask`  

## Properties

- `public System.UInt32 frameIndex { get; private set }`  
- `public System.Single frameTime { get; private set }`  
- `public System.Single selectedSpeed { get; set }`  
- `public System.Single smoothSpeed { get; private set }`  
- `public System.Single loadingProgress { get; private set }`  
- `public System.Single frameDuration { get; private set }`  
- `public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set }`  

## Constructors

- `public SimulationSystem()`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private UpdateLoadingProgress() : System.Void`  

## Nested types

- `Game.Simulation.SimulationSystem+PerformancePreference`  
- `Game.Simulation.SimulationSystem+SimulationEndTimeJob`  

