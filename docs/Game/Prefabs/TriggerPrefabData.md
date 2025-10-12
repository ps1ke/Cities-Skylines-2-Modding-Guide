# Game.Prefabs.TriggerPrefabData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `private Unity.Collections.NativeParallelMultiHashMap<Game.Prefabs.TriggerPrefabData+PrefabKey, Game.Prefabs.TriggerPrefabData+PrefabValue> m_PrefabMap`  

## Constructors

- `public TriggerPrefabData(Unity.Collections.Allocator allocator)`  

## Methods

- `public AddPrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData) : System.Void`  
- `public Dispose() : System.Void`  
- `public HasAnyPrefabs(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab) : System.Boolean`  
- `public RemovePrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData) : System.Void`  
- `public TryGetFirstPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator) : System.Boolean`  
- `public TryGetNextPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator) : System.Boolean`  

## Nested types

- `Game.Prefabs.TriggerPrefabData+PrefabKey`  
- `Game.Prefabs.TriggerPrefabData+PrefabValue`  
- `Game.Prefabs.TriggerPrefabData+Iterator`  

