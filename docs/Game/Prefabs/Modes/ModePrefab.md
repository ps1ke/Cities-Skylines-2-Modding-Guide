# Game.Prefabs.Modes.ModePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Fields

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo>> <modeDebugUILogs>k__BackingField`  

## Properties

- `public System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo>> modeDebugUILogs { get; private set }`  

## Constructors

- `protected ModePrefab()`  

## Methods

- `public ClearLog() : System.Void`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `protected RecordLog<T>(Unity.Entities.Entity entity, T& value) : System.Void`  
- `protected RecordLog<T>(Unity.Entities.Entity entity, DynamicBuffer`1& value) : System.Void`  

## Nested types

- `Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo`  
- `Game.Prefabs.Modes.ModePrefab+<>c__DisplayClass7_0<T>`  
- `Game.Prefabs.Modes.ModePrefab+<>c__DisplayClass8_0<T>`  

