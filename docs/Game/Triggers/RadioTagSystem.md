# Game.Triggers.RadioTagSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_RecentTags`  
- `private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_InputQueue`  
- `private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_EmergencyInputQueue`  
- `private Unity.Collections.NativeQueue<Game.Triggers.RadioTag> m_EmergencyQueue`  
- `private System.Collections.Generic.Dictionary<Game.Audio.Radio.Radio+SegmentType, System.Collections.Generic.List<Game.Triggers.RadioTag>> m_Events`  
- `private Unity.Jobs.JobHandle m_InputDependencies`  
- `private Unity.Jobs.JobHandle m_EmergencyInputDependencies`  
- `private Unity.Jobs.JobHandle m_EmergencyDependencies`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private static readonly System.Int32 kFrameDelay`  
- `private static readonly System.Int32 kMaxBufferSize`  

## Constructors

- `public RadioTagSystem()`  

## Methods

- `public AddEmergencyInputQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddInputQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `private Clear() : System.Void`  
- `private EnsureList(Game.Audio.Radio.Radio+SegmentType segmentType) : System.Collections.Generic.List<Game.Triggers.RadioTag>`  
- `public FlushEvents(Game.Audio.Radio.Radio+SegmentType segmentType) : System.Void`  
- `public GetEmergencyInputQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.RadioTag>`  
- `public GetEmergencyQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.RadioTag>`  
- `public GetInputQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.RadioTag>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public TryPopEvent(Game.Audio.Radio.Radio+SegmentType segmentType, System.Boolean newestFirst, Game.Triggers.RadioTag& radioTag) : System.Boolean`  

