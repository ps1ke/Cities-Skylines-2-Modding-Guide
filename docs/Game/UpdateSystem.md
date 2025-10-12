# Game.UpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private System.Collections.Generic.List<Game.IGPUSystem> m_GPUSystems`  
- `private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Systems`  
- `private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Updates`  
- `private System.Collections.Generic.List<Unity.Mathematics.int2> m_UpdateRanges`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.ComponentSystemBase, System.Collections.Generic.List<Game.UpdateSystem+SystemData>> m_RefMap`  
- `private System.Int32 m_AddIndex`  
- `private System.Boolean m_IsDirty`  
- `private Game.SystemUpdatePhase <currentPhase>k__BackingField`  

## Properties

- `public Game.SystemUpdatePhase currentPhase { get; private set }`  

## Constructors

- `public UpdateSystem()`  

## Methods

- `private AddSystemUpdate(System.Collections.Generic.List<Game.UpdateSystem+IntervalData> intervalList, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety) : System.Void`  
- `public static GetInterval(Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase, System.Int32& interval, System.Int32& offset) : System.Void`  
- `protected virtual OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Camera[] cameras) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private PatchSystemOffset(System.Int32& updateIndex, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety) : System.Void`  
- `private Refresh() : System.Void`  
- `private Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase) : System.Void`  
- `private Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Unity.Entities.ComponentSystemBase other, Game.SystemUpdatePhase phase) : System.Void`  
- `public RegisterGPUSystem<SystemType>() : System.Void`  
- `public RegisterGPUSystem(Game.IGPUSystem system) : System.Void`  
- `public Update(Game.SystemUpdatePhase phase) : System.Void`  
- `public Update(Game.SystemUpdatePhase phase, System.UInt32 updateIndex, System.Int32 iterationIndex) : System.Void`  
- `public UpdateAfter<SystemType>(Game.SystemUpdatePhase phase) : System.Void`  
- `public UpdateAfter<SystemType, OtherType>(Game.SystemUpdatePhase phase) : System.Void`  
- `public UpdateAt<SystemType>(Game.SystemUpdatePhase phase) : System.Void`  
- `public UpdateBefore<SystemType>(Game.SystemUpdatePhase phase) : System.Void`  
- `public UpdateBefore<SystemType, OtherType>(Game.SystemUpdatePhase phase) : System.Void`  

## Nested types

- `Game.UpdateSystem+SystemData`  
- `Game.UpdateSystem+IntervalData`  

