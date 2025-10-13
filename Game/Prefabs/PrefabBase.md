# Game.Prefabs.PrefabBase

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class PrefabBase : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    private System.String <thumbnailUrl>k__BackingField;
    public System.Collections.Generic.List<Game.Prefabs.ComponentBase> components;
    public System.Boolean isDirty;
    private Colossal.IO.AssetDatabase.PrefabAsset <asset>k__BackingField;

    public System.String thumbnailUrl { get; private set; }
    public System.Boolean builtin { get; }
    public Colossal.IO.AssetDatabase.PrefabAsset asset { get; set; }
    public System.Boolean canIgnoreUnlockDependencies { get; }
    public System.String uiTag { get; }

    protected PrefabBase();

    public T AddComponent<T>();
    public Game.Prefabs.ComponentBase AddComponent(System.Type type);
    public T AddComponentFrom<T>(T from);
    public Game.Prefabs.ComponentBase AddComponentFrom(Game.Prefabs.ComponentBase from);
    public T AddOrGetComponent<T>();
    public Game.Prefabs.ComponentBase AddOrGetComponent(System.Type type);
    public Game.Prefabs.PrefabBase Clone(System.String newName);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public Game.Prefabs.PrefabID GetPrefabID();
    public System.Boolean Has<T>();
    public System.Boolean Has(System.Type type);
    public System.Boolean HasSubclassOf(System.Type type);
    public virtual System.Void OnAfterDeserialize();
    public System.Void OnBeforeSerialize();
    protected virtual System.Void OnEnable();
    public System.Void Remove<T>();
    public System.Void Remove(System.Type type);
    public Game.Prefabs.ComponentBase ReplaceComponentWith(Game.Prefabs.ComponentBase target, System.Type type);
    public virtual System.Void Reset();
    public System.Boolean TryGet<T>(T& component);
    public System.Boolean TryGet(System.Type type, Game.Prefabs.ComponentBase& component);
    public System.Boolean TryGet<T>(System.Collections.Generic.List<T> result);
    public System.Boolean TryGetExactly<T>(T& component);
    public System.Boolean TryGetExactly(System.Type type, Game.Prefabs.ComponentBase& component);
}
```


## Fields

- `private System.String <thumbnailUrl>k__BackingField`  

```csharp
private System.String <thumbnailUrl>k__BackingField;
```

- `public System.Collections.Generic.List<Game.Prefabs.ComponentBase> components`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.ComponentBase> components;
```

- `public System.Boolean isDirty`  

```csharp
public System.Boolean isDirty;
```

- `private Colossal.IO.AssetDatabase.PrefabAsset <asset>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.PrefabAsset <asset>k__BackingField;
```


## Properties

- `public System.String thumbnailUrl { get; private set }`  

```csharp
public System.String thumbnailUrl { get; private set; }
```

- `public System.Boolean builtin { get }`  

```csharp
public System.Boolean builtin { get; }
```

- `public Colossal.IO.AssetDatabase.PrefabAsset asset { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.PrefabAsset asset { get; set; }
```

- `public System.Boolean canIgnoreUnlockDependencies { get }`  

```csharp
public System.Boolean canIgnoreUnlockDependencies { get; }
```

- `public System.String uiTag { get }`  

```csharp
public System.String uiTag { get; }
```


## Constructors

- `protected PrefabBase()`  

```csharp
protected PrefabBase();
```


## Methods

- `public AddComponent<T>() : T`  

```csharp
public T AddComponent<T>();
```

- `public AddComponent(System.Type type) : Game.Prefabs.ComponentBase`  

```csharp
public Game.Prefabs.ComponentBase AddComponent(System.Type type);
```

- `public AddComponentFrom<T>(T from) : T`  

```csharp
public T AddComponentFrom<T>(T from);
```

- `public AddComponentFrom(Game.Prefabs.ComponentBase from) : Game.Prefabs.ComponentBase`  

```csharp
public Game.Prefabs.ComponentBase AddComponentFrom(Game.Prefabs.ComponentBase from);
```

- `public AddOrGetComponent<T>() : T`  

```csharp
public T AddOrGetComponent<T>();
```

- `public AddOrGetComponent(System.Type type) : Game.Prefabs.ComponentBase`  

```csharp
public Game.Prefabs.ComponentBase AddOrGetComponent(System.Type type);
```

- `public Clone(System.String newName = null) : Game.Prefabs.PrefabBase`  

```csharp
public Game.Prefabs.PrefabBase Clone(System.String newName);
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public GetPrefabID() : Game.Prefabs.PrefabID`  

```csharp
public Game.Prefabs.PrefabID GetPrefabID();
```

- `public Has<T>() : System.Boolean`  

```csharp
public System.Boolean Has<T>();
```

- `public Has(System.Type type) : System.Boolean`  

```csharp
public System.Boolean Has(System.Type type);
```

- `public HasSubclassOf(System.Type type) : System.Boolean`  

```csharp
public System.Boolean HasSubclassOf(System.Type type);
```

- `public virtual OnAfterDeserialize() : System.Void`  

```csharp
public virtual System.Void OnAfterDeserialize();
```

- `public OnBeforeSerialize() : System.Void`  

```csharp
public System.Void OnBeforeSerialize();
```

- `protected virtual OnEnable() : System.Void`  

```csharp
protected virtual System.Void OnEnable();
```

- `public Remove<T>() : System.Void`  

```csharp
public System.Void Remove<T>();
```

- `public Remove(System.Type type) : System.Void`  

```csharp
public System.Void Remove(System.Type type);
```

- `public ReplaceComponentWith(Game.Prefabs.ComponentBase target, System.Type type) : Game.Prefabs.ComponentBase`  

```csharp
public Game.Prefabs.ComponentBase ReplaceComponentWith(Game.Prefabs.ComponentBase target, System.Type type);
```

- `public virtual Reset() : System.Void`  

```csharp
public virtual System.Void Reset();
```

- `public TryGet<T>(T& component) : System.Boolean`  

```csharp
public System.Boolean TryGet<T>(T& component);
```

- `public TryGet(System.Type type, Game.Prefabs.ComponentBase& component) : System.Boolean`  

```csharp
public System.Boolean TryGet(System.Type type, Game.Prefabs.ComponentBase& component);
```

- `public TryGet<T>(System.Collections.Generic.List<T> result) : System.Boolean`  

```csharp
public System.Boolean TryGet<T>(System.Collections.Generic.List<T> result);
```

- `public TryGetExactly<T>(T& component) : System.Boolean`  

```csharp
public System.Boolean TryGetExactly<T>(T& component);
```

- `public TryGetExactly(System.Type type, Game.Prefabs.ComponentBase& component) : System.Boolean`  

```csharp
public System.Boolean TryGetExactly(System.Type type, Game.Prefabs.ComponentBase& component);
```


## Nested types

- `Game.Prefabs.PrefabBase+<>c`  

