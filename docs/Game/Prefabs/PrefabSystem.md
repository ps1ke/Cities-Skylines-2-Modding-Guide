# Game.Prefabs.PrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Colossal.Logging.ILog m_UnlockingLog`  
- `private Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged onContentAvailabilityChanged`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs`  
- `private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+ObsoleteData> m_ObsoleteIDs`  
- `private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+LoadedIndexData> m_LoadedIndexData`  
- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_UpdateMap`  
- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_Entities`  
- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, System.Boolean> m_IsUnlockable`  
- `private System.Collections.Generic.Dictionary<Game.Prefabs.ContentPrefab, System.Boolean> m_IsAvailable`  
- `private System.Collections.Generic.Dictionary<System.Int32, Game.Prefabs.PrefabID> m_LoadedObsoleteIDs`  
- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabID, System.Int32> m_PrefabIndices`  
- `private Unity.Entities.ComponentTypeSet m_UnlockableTypes`  

## Properties

- `internal System.Collections.Generic.IEnumerable<Game.Prefabs.PrefabBase> prefabs { internal get }`  

## Constructors

- `public PrefabSystem()`  

## Methods

- `public AddComponentData<T>(Game.Prefabs.PrefabBase prefab, T componentData) : System.Void`  
- `public AddObsoleteID(Unity.Entities.Entity entity, Game.Prefabs.PrefabID id) : System.Void`  
- `public AddPrefab(Game.Prefabs.PrefabBase prefab, System.String parentName = null, Game.Prefabs.PrefabBase parentPrefab = null, Game.Prefabs.ComponentBase parentComponent = null) : System.Boolean`  
- `public AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase unlocked) : System.Void`  
- `public AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase[] unlocked) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public DuplicatePrefab(Game.Prefabs.PrefabBase template, System.String name = null) : Game.Prefabs.PrefabBase`  
- `public GetAvailableContentPrefabs() : System.Collections.Generic.IEnumerable<Game.Prefabs.ContentPrefab>`  
- `public GetAvailablePrerequisitesNames() : System.String[]`  
- `public GetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly) : Unity.Entities.DynamicBuffer<T>`  
- `public GetComponentData<T>(Game.Prefabs.PrefabBase prefab) : T`  
- `public GetEntity(Game.Prefabs.PrefabBase prefab) : Unity.Entities.Entity`  
- `public GetLoadedObsoleteID(System.Int32 loadedIndex) : Game.Prefabs.PrefabID`  
- `public GetObsoleteID(Game.Prefabs.PrefabData prefabData) : Game.Prefabs.PrefabID`  
- `public GetObsoleteID(Unity.Entities.Entity entity) : Game.Prefabs.PrefabID`  
- `public GetPrefab<T>(Game.Prefabs.PrefabData prefabData) : T`  
- `public GetPrefab<T>(Unity.Entities.Entity entity) : T`  
- `public GetPrefab<T>(Game.Prefabs.PrefabRef refData) : T`  
- `public GetPrefabName(Unity.Entities.Entity entity) : System.String`  
- `public GetSingletonPrefab<T>(Unity.Entities.EntityQuery group) : T`  
- `public HasComponent<T>(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `public HasEnabledComponent<T>(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `public IsAvailable(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `public IsUnlockable(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private IsUnlockableImpl(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public RemoveComponent<T>(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `public RemovePrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public TryGetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly, DynamicBuffer`1& buffer) : System.Boolean`  
- `public TryGetComponentData<T>(Game.Prefabs.PrefabBase prefab, T& component) : System.Boolean`  
- `public TryGetEntity(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity& entity) : System.Boolean`  
- `public TryGetPrefab<T>(Game.Prefabs.PrefabData prefabData, T& prefab) : System.Boolean`  
- `public TryGetPrefab<T>(Unity.Entities.Entity entity, T& prefab) : System.Boolean`  
- `public TryGetPrefab<T>(Game.Prefabs.PrefabRef refData, T& prefab) : System.Boolean`  
- `public TryGetPrefab(Game.Prefabs.PrefabID id, Game.Prefabs.PrefabBase& prefab) : System.Boolean`  
- `public TryGetSingletonPrefab<T>(Unity.Entities.EntityQuery group, T& prefab) : System.Boolean`  
- `public UpdateAvailabilityCache() : System.Void`  
- `public UpdateLoadedIndices() : System.Void`  
- `public UpdatePrefab(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity sourceInstance = null) : System.Void`  
- `private UpdatePrefabs() : System.Boolean`  

## Events

- `onContentAvailabilityChanged` : `Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged`  

## Nested types

- `Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged`  
- `Game.Prefabs.PrefabSystem+ObsoleteData`  
- `Game.Prefabs.PrefabSystem+LoadedIndexData`  
- `Game.Prefabs.PrefabSystem+<>c`  

