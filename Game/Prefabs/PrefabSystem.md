# Game.Prefabs.PrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrefabSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Colossal.Logging.ILog m_UnlockingLog;
    private Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged onContentAvailabilityChanged;
    private Game.UpdateSystem m_UpdateSystem;
    private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs;
    private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+ObsoleteData> m_ObsoleteIDs;
    private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+LoadedIndexData> m_LoadedIndexData;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_UpdateMap;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_Entities;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, System.Boolean> m_IsUnlockable;
    private System.Collections.Generic.Dictionary<Game.Prefabs.ContentPrefab, System.Boolean> m_IsAvailable;
    private System.Collections.Generic.Dictionary<System.Int32, Game.Prefabs.PrefabID> m_LoadedObsoleteIDs;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabID, System.Int32> m_PrefabIndices;
    private Unity.Entities.ComponentTypeSet m_UnlockableTypes;

    internal System.Collections.Generic.IEnumerable<Game.Prefabs.PrefabBase> prefabs { internal get; }

    public PrefabSystem();

    public System.Void AddComponentData<T>(Game.Prefabs.PrefabBase prefab, T componentData);
    public System.Void AddObsoleteID(Unity.Entities.Entity entity, Game.Prefabs.PrefabID id);
    public System.Boolean AddPrefab(Game.Prefabs.PrefabBase prefab, System.String parentName, Game.Prefabs.PrefabBase parentPrefab, Game.Prefabs.ComponentBase parentComponent);
    public System.Void AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase unlocked);
    public System.Void AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase[] unlocked);
    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Prefabs.PrefabBase DuplicatePrefab(Game.Prefabs.PrefabBase template, System.String name);
    public System.Collections.Generic.IEnumerable<Game.Prefabs.ContentPrefab> GetAvailableContentPrefabs();
    public System.String[] GetAvailablePrerequisitesNames();
    public Unity.Entities.DynamicBuffer<T> GetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly);
    public T GetComponentData<T>(Game.Prefabs.PrefabBase prefab);
    public Unity.Entities.Entity GetEntity(Game.Prefabs.PrefabBase prefab);
    public Game.Prefabs.PrefabID GetLoadedObsoleteID(System.Int32 loadedIndex);
    public Game.Prefabs.PrefabID GetObsoleteID(Game.Prefabs.PrefabData prefabData);
    public Game.Prefabs.PrefabID GetObsoleteID(Unity.Entities.Entity entity);
    public T GetPrefab<T>(Game.Prefabs.PrefabData prefabData);
    public T GetPrefab<T>(Unity.Entities.Entity entity);
    public T GetPrefab<T>(Game.Prefabs.PrefabRef refData);
    public System.String GetPrefabName(Unity.Entities.Entity entity);
    public T GetSingletonPrefab<T>(Unity.Entities.EntityQuery group);
    public System.Boolean HasComponent<T>(Game.Prefabs.PrefabBase prefab);
    public System.Boolean HasEnabledComponent<T>(Game.Prefabs.PrefabBase prefab);
    public System.Boolean IsAvailable(Game.Prefabs.PrefabBase prefab);
    public System.Boolean IsUnlockable(Game.Prefabs.PrefabBase prefab);
    private System.Boolean IsUnlockableImpl(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void RemoveComponent<T>(Game.Prefabs.PrefabBase prefab);
    public System.Boolean RemovePrefab(Game.Prefabs.PrefabBase prefab);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Boolean TryGetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly, DynamicBuffer`1& buffer);
    public System.Boolean TryGetComponentData<T>(Game.Prefabs.PrefabBase prefab, T& component);
    public System.Boolean TryGetEntity(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity& entity);
    public System.Boolean TryGetPrefab<T>(Game.Prefabs.PrefabData prefabData, T& prefab);
    public System.Boolean TryGetPrefab<T>(Unity.Entities.Entity entity, T& prefab);
    public System.Boolean TryGetPrefab<T>(Game.Prefabs.PrefabRef refData, T& prefab);
    public System.Boolean TryGetPrefab(Game.Prefabs.PrefabID id, Game.Prefabs.PrefabBase& prefab);
    public System.Boolean TryGetSingletonPrefab<T>(Unity.Entities.EntityQuery group, T& prefab);
    public System.Void UpdateAvailabilityCache();
    public System.Void UpdateLoadedIndices();
    public System.Void UpdatePrefab(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity sourceInstance);
    private System.Boolean UpdatePrefabs();
}
```


## Fields

- `private Colossal.Logging.ILog m_UnlockingLog`  

```csharp
private Colossal.Logging.ILog m_UnlockingLog;
```

- `private Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged onContentAvailabilityChanged`  

```csharp
private Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged onContentAvailabilityChanged;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs;
```

- `private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+ObsoleteData> m_ObsoleteIDs`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+ObsoleteData> m_ObsoleteIDs;
```

- `private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+LoadedIndexData> m_LoadedIndexData`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+LoadedIndexData> m_LoadedIndexData;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_UpdateMap`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_UpdateMap;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_Entities`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_Entities;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, System.Boolean> m_IsUnlockable`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, System.Boolean> m_IsUnlockable;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.ContentPrefab, System.Boolean> m_IsAvailable`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.ContentPrefab, System.Boolean> m_IsAvailable;
```

- `private System.Collections.Generic.Dictionary<System.Int32, Game.Prefabs.PrefabID> m_LoadedObsoleteIDs`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, Game.Prefabs.PrefabID> m_LoadedObsoleteIDs;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabID, System.Int32> m_PrefabIndices`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabID, System.Int32> m_PrefabIndices;
```

- `private Unity.Entities.ComponentTypeSet m_UnlockableTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_UnlockableTypes;
```


## Properties

- `internal System.Collections.Generic.IEnumerable<Game.Prefabs.PrefabBase> prefabs { internal get }`  

```csharp
internal System.Collections.Generic.IEnumerable<Game.Prefabs.PrefabBase> prefabs { internal get; }
```


## Constructors

- `public PrefabSystem()`  

```csharp
public PrefabSystem();
```


## Methods

- `public AddComponentData<T>(Game.Prefabs.PrefabBase prefab, T componentData) : System.Void`  

```csharp
public System.Void AddComponentData<T>(Game.Prefabs.PrefabBase prefab, T componentData);
```

- `public AddObsoleteID(Unity.Entities.Entity entity, Game.Prefabs.PrefabID id) : System.Void`  

```csharp
public System.Void AddObsoleteID(Unity.Entities.Entity entity, Game.Prefabs.PrefabID id);
```

- `public AddPrefab(Game.Prefabs.PrefabBase prefab, System.String parentName = null, Game.Prefabs.PrefabBase parentPrefab = null, Game.Prefabs.ComponentBase parentComponent = null) : System.Boolean`  

```csharp
public System.Boolean AddPrefab(Game.Prefabs.PrefabBase prefab, System.String parentName, Game.Prefabs.PrefabBase parentPrefab, Game.Prefabs.ComponentBase parentComponent);
```

- `public AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase unlocked) : System.Void`  

```csharp
public System.Void AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase unlocked);
```

- `public AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase[] unlocked) : System.Void`  

```csharp
public System.Void AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase[] unlocked);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public DuplicatePrefab(Game.Prefabs.PrefabBase template, System.String name = null) : Game.Prefabs.PrefabBase`  

```csharp
public Game.Prefabs.PrefabBase DuplicatePrefab(Game.Prefabs.PrefabBase template, System.String name);
```

- `public GetAvailableContentPrefabs() : System.Collections.Generic.IEnumerable<Game.Prefabs.ContentPrefab>`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Prefabs.ContentPrefab> GetAvailableContentPrefabs();
```

- `public GetAvailablePrerequisitesNames() : System.String[]`  

```csharp
public System.String[] GetAvailablePrerequisitesNames();
```

- `public GetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly) : Unity.Entities.DynamicBuffer<T>`  

```csharp
public Unity.Entities.DynamicBuffer<T> GetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly);
```

- `public GetComponentData<T>(Game.Prefabs.PrefabBase prefab) : T`  

```csharp
public T GetComponentData<T>(Game.Prefabs.PrefabBase prefab);
```

- `public GetEntity(Game.Prefabs.PrefabBase prefab) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity GetEntity(Game.Prefabs.PrefabBase prefab);
```

- `public GetLoadedObsoleteID(System.Int32 loadedIndex) : Game.Prefabs.PrefabID`  

```csharp
public Game.Prefabs.PrefabID GetLoadedObsoleteID(System.Int32 loadedIndex);
```

- `public GetObsoleteID(Game.Prefabs.PrefabData prefabData) : Game.Prefabs.PrefabID`  

```csharp
public Game.Prefabs.PrefabID GetObsoleteID(Game.Prefabs.PrefabData prefabData);
```

- `public GetObsoleteID(Unity.Entities.Entity entity) : Game.Prefabs.PrefabID`  

```csharp
public Game.Prefabs.PrefabID GetObsoleteID(Unity.Entities.Entity entity);
```

- `public GetPrefab<T>(Game.Prefabs.PrefabData prefabData) : T`  

```csharp
public T GetPrefab<T>(Game.Prefabs.PrefabData prefabData);
```

- `public GetPrefab<T>(Unity.Entities.Entity entity) : T`  

```csharp
public T GetPrefab<T>(Unity.Entities.Entity entity);
```

- `public GetPrefab<T>(Game.Prefabs.PrefabRef refData) : T`  

```csharp
public T GetPrefab<T>(Game.Prefabs.PrefabRef refData);
```

- `public GetPrefabName(Unity.Entities.Entity entity) : System.String`  

```csharp
public System.String GetPrefabName(Unity.Entities.Entity entity);
```

- `public GetSingletonPrefab<T>(Unity.Entities.EntityQuery group) : T`  

```csharp
public T GetSingletonPrefab<T>(Unity.Entities.EntityQuery group);
```

- `public HasComponent<T>(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public System.Boolean HasComponent<T>(Game.Prefabs.PrefabBase prefab);
```

- `public HasEnabledComponent<T>(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public System.Boolean HasEnabledComponent<T>(Game.Prefabs.PrefabBase prefab);
```

- `public IsAvailable(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public System.Boolean IsAvailable(Game.Prefabs.PrefabBase prefab);
```

- `public IsUnlockable(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public System.Boolean IsUnlockable(Game.Prefabs.PrefabBase prefab);
```

- `private IsUnlockableImpl(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components) : System.Boolean`  

```csharp
private System.Boolean IsUnlockableImpl(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public RemoveComponent<T>(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
public System.Void RemoveComponent<T>(Game.Prefabs.PrefabBase prefab);
```

- `public RemovePrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public System.Boolean RemovePrefab(Game.Prefabs.PrefabBase prefab);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `public TryGetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly, DynamicBuffer`1& buffer) : System.Boolean`  

```csharp
public System.Boolean TryGetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly, DynamicBuffer`1& buffer);
```

- `public TryGetComponentData<T>(Game.Prefabs.PrefabBase prefab, T& component) : System.Boolean`  

```csharp
public System.Boolean TryGetComponentData<T>(Game.Prefabs.PrefabBase prefab, T& component);
```

- `public TryGetEntity(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
public System.Boolean TryGetEntity(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity& entity);
```

- `public TryGetPrefab<T>(Game.Prefabs.PrefabData prefabData, T& prefab) : System.Boolean`  

```csharp
public System.Boolean TryGetPrefab<T>(Game.Prefabs.PrefabData prefabData, T& prefab);
```

- `public TryGetPrefab<T>(Unity.Entities.Entity entity, T& prefab) : System.Boolean`  

```csharp
public System.Boolean TryGetPrefab<T>(Unity.Entities.Entity entity, T& prefab);
```

- `public TryGetPrefab<T>(Game.Prefabs.PrefabRef refData, T& prefab) : System.Boolean`  

```csharp
public System.Boolean TryGetPrefab<T>(Game.Prefabs.PrefabRef refData, T& prefab);
```

- `public TryGetPrefab(Game.Prefabs.PrefabID id, Game.Prefabs.PrefabBase& prefab) : System.Boolean`  

```csharp
public System.Boolean TryGetPrefab(Game.Prefabs.PrefabID id, Game.Prefabs.PrefabBase& prefab);
```

- `public TryGetSingletonPrefab<T>(Unity.Entities.EntityQuery group, T& prefab) : System.Boolean`  

```csharp
public System.Boolean TryGetSingletonPrefab<T>(Unity.Entities.EntityQuery group, T& prefab);
```

- `public UpdateAvailabilityCache() : System.Void`  

```csharp
public System.Void UpdateAvailabilityCache();
```

- `public UpdateLoadedIndices() : System.Void`  

```csharp
public System.Void UpdateLoadedIndices();
```

- `public UpdatePrefab(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity sourceInstance = null) : System.Void`  

```csharp
public System.Void UpdatePrefab(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity sourceInstance);
```

- `private UpdatePrefabs() : System.Boolean`  

```csharp
private System.Boolean UpdatePrefabs();
```


## Events

- `onContentAvailabilityChanged` : `Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged`  

```csharp
public event Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged onContentAvailabilityChanged;
```


## Nested types

- `Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged`  
- `Game.Prefabs.PrefabSystem+ObsoleteData`  
- `Game.Prefabs.PrefabSystem+LoadedIndexData`  
- `Game.Prefabs.PrefabSystem+<>c`  

