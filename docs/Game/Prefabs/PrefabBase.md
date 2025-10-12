# Game.Prefabs.PrefabBase

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Fields

- `private System.String <thumbnailUrl>k__BackingField`  
- `public System.Collections.Generic.List<Game.Prefabs.ComponentBase> components`  
- `public System.Boolean isDirty`  
- `private Colossal.IO.AssetDatabase.PrefabAsset <asset>k__BackingField`  

## Properties

- `public System.String thumbnailUrl { get; private set }`  
- `public System.Boolean builtin { get }`  
- `public Colossal.IO.AssetDatabase.PrefabAsset asset { get; set }`  
- `public System.Boolean canIgnoreUnlockDependencies { get }`  
- `public System.String uiTag { get }`  

## Constructors

- `protected PrefabBase()`  

## Methods

- `public AddComponent<T>() : T`  
- `public AddComponent(System.Type type) : Game.Prefabs.ComponentBase`  
- `public AddComponentFrom<T>(T from) : T`  
- `public AddComponentFrom(Game.Prefabs.ComponentBase from) : Game.Prefabs.ComponentBase`  
- `public AddOrGetComponent<T>() : T`  
- `public AddOrGetComponent(System.Type type) : Game.Prefabs.ComponentBase`  
- `public Clone(System.String newName = null) : Game.Prefabs.PrefabBase`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetPrefabID() : Game.Prefabs.PrefabID`  
- `public Has<T>() : System.Boolean`  
- `public Has(System.Type type) : System.Boolean`  
- `public HasSubclassOf(System.Type type) : System.Boolean`  
- `public virtual OnAfterDeserialize() : System.Void`  
- `public OnBeforeSerialize() : System.Void`  
- `protected virtual OnEnable() : System.Void`  
- `public Remove<T>() : System.Void`  
- `public Remove(System.Type type) : System.Void`  
- `public ReplaceComponentWith(Game.Prefabs.ComponentBase target, System.Type type) : Game.Prefabs.ComponentBase`  
- `public virtual Reset() : System.Void`  
- `public TryGet<T>(T& component) : System.Boolean`  
- `public TryGet(System.Type type, Game.Prefabs.ComponentBase& component) : System.Boolean`  
- `public TryGet<T>(System.Collections.Generic.List<T> result) : System.Boolean`  
- `public TryGetExactly<T>(T& component) : System.Boolean`  
- `public TryGetExactly(System.Type type, Game.Prefabs.ComponentBase& component) : System.Boolean`  

## Nested types

- `Game.Prefabs.PrefabBase+<>c`  

