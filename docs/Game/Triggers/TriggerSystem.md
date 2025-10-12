# Game.Triggers.TriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Prefabs.TriggerPrefabSystem m_TriggerPrefabSystem`  
- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  
- `private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>> m_Queues`  
- `private Unity.Jobs.JobHandle m_Dependencies`  
- `private Game.Triggers.CreateChirpSystem m_CreateChirpSystem`  
- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  
- `private Game.Triggers.RadioTagSystem m_RadioTagSystem`  
- `private Game.Tutorials.TutorialEventActivationSystem m_TutorialEventActivationSystem`  
- `private System.DateTime m_LastTimedEventTime`  
- `private System.TimeSpan m_TimedEventInterval`  
- `private Unity.Entities.EntityQuery m_EDWSBuildingQuery`  
- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_TriggerFrames`  
- `private Game.Triggers.TriggerSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TriggerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddActionBufferWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public CreateActionBuffer() : Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Triggers.TriggerSystem+TriggerActionJob`  
- `Game.Triggers.TriggerSystem+TypeHandle`  

