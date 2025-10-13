# Game.Prefabs.TriggerPrefabData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct TriggerPrefabData : System.IDisposable
{
    private Unity.Collections.NativeParallelMultiHashMap<Game.Prefabs.TriggerPrefabData+PrefabKey, Game.Prefabs.TriggerPrefabData+PrefabValue> m_PrefabMap;

    public TriggerPrefabData(Unity.Collections.Allocator allocator);

    public System.Void AddPrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData);
    public System.Void Dispose();
    public System.Boolean HasAnyPrefabs(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab);
    public System.Void RemovePrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData);
    public System.Boolean TryGetFirstPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator);
    public System.Boolean TryGetNextPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator);
}
```


## Fields

- `private Unity.Collections.NativeParallelMultiHashMap<Game.Prefabs.TriggerPrefabData+PrefabKey, Game.Prefabs.TriggerPrefabData+PrefabValue> m_PrefabMap`  

```csharp
private Unity.Collections.NativeParallelMultiHashMap<Game.Prefabs.TriggerPrefabData+PrefabKey, Game.Prefabs.TriggerPrefabData+PrefabValue> m_PrefabMap;
```


## Constructors

- `public TriggerPrefabData(Unity.Collections.Allocator allocator)`  

```csharp
public TriggerPrefabData(Unity.Collections.Allocator allocator);
```


## Methods

- `public AddPrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData) : System.Void`  

```csharp
public System.Void AddPrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public HasAnyPrefabs(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab) : System.Boolean`  

```csharp
public System.Boolean HasAnyPrefabs(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab);
```

- `public RemovePrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData) : System.Void`  

```csharp
public System.Void RemovePrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData);
```

- `public TryGetFirstPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator) : System.Boolean`  

```csharp
public System.Boolean TryGetFirstPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator);
```

- `public TryGetNextPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator) : System.Boolean`  

```csharp
public System.Boolean TryGetNextPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator);
```


## Nested types

- `Game.Prefabs.TriggerPrefabData+PrefabKey`  
- `Game.Prefabs.TriggerPrefabData+PrefabValue`  
- `Game.Prefabs.TriggerPrefabData+Iterator`  

