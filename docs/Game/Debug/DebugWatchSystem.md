# Game.Debug.DebugWatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+ManagedSystemState> m_ManagedSystemStates`  
- `private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> m_Watches`  
- `private System.UInt32 m_LastFrameIndex`  
- `private System.Boolean m_WatchesChanged`  
- `private static readonly System.String[] colors`  

## Properties

- `public System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> watches { get }`  
- `public System.Boolean watchesChanged { get }`  

## Constructors

- `public DebugWatchSystem()`  

## Methods

- `internal static <BuildSystemFoldouts>g__Value|15_3(System.String name, Game.Reflection.IValueAccessor accessor) : UnityEngine.Rendering.DebugUI+Widget`  
- `internal static <BuildSystemFoldouts>g__ValueContainer|15_2(System.String name, Game.Reflection.IValueAccessor accessor) : UnityEngine.Rendering.DebugUI+Widget`  
- `public BuildSystemFoldouts() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  
- `public ClearWatches() : System.Void`  
- `public ClearWatchesChanged() : System.Void`  
- `public static CreateTypedAccessor(Game.Reflection.IValueAccessor accessor) : Game.Reflection.IValueAccessor`  
- `private static GetArrayItemName(System.Reflection.MemberInfo member, System.Int32 index) : System.String`  
- `private static GetWatchDepsFields(System.Type systemType) : System.Reflection.FieldInfo[]`  
- `private static GetWatchValueMembers(System.Type systemType) : System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Debug.DebugWatchSystem+ManagedSystemState`  
- `Game.Debug.DebugWatchSystem+Watch`  
- `Game.Debug.DebugWatchSystem+HistoryWatch<T>`  
- `Game.Debug.DebugWatchSystem+DistributionWatch`  
- `Game.Debug.DebugWatchSystem+<>c`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass11_0`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_0`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_1`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_2`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_3`  

