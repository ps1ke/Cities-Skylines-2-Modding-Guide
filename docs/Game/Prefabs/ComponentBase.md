# Game.Prefabs.ComponentBase

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `UnityEngine.ScriptableObject`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `Serializable`  

## Fields

- `public System.Boolean active`  
- `private Game.Prefabs.PrefabBase <prefab>k__BackingField`  
- `protected static Colossal.Logging.ILog baseLog`  

## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  
- `public Game.Prefabs.PrefabBase prefab { get; set }`  
- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

## Constructors

- `protected ComponentBase()`  

## Methods

- `public CompareTo(System.Object obj) : System.Int32`  
- `public abstract GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetComponent<T>() : T`  
- `public GetComponentExactly(System.Type type) : Game.Prefabs.ComponentBase`  
- `public GetComponents<T>(System.Collections.Generic.List<T> list) : System.Boolean`  
- `public virtual GetDebugString() : System.String`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public abstract GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `protected virtual OnDisable() : System.Void`  
- `protected virtual OnEnable() : System.Void`  

