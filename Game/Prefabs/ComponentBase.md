# Game.Prefabs.ComponentBase

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `UnityEngine.ScriptableObject`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `Serializable`  

## Code

```csharp
public abstract class ComponentBase : UnityEngine.ScriptableObject, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean active;
    private Game.Prefabs.PrefabBase <prefab>k__BackingField;
    protected static Colossal.Logging.ILog baseLog;

    public System.Boolean ignoreUnlockDependencies { get; }
    public Game.Prefabs.PrefabBase prefab { get; set; }
    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    protected ComponentBase();

    public System.Int32 CompareTo(System.Object obj);
    public abstract System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public T GetComponent<T>();
    public Game.Prefabs.ComponentBase GetComponentExactly(System.Type type);
    public System.Boolean GetComponents<T>(System.Collections.Generic.List<T> list);
    public virtual System.String GetDebugString();
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public abstract System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    protected virtual System.Void OnDisable();
    protected virtual System.Void OnEnable();
}
```


## Fields

- `public System.Boolean active`  

```csharp
public System.Boolean active;
```

- `private Game.Prefabs.PrefabBase <prefab>k__BackingField`  

```csharp
private Game.Prefabs.PrefabBase <prefab>k__BackingField;
```

- `protected static Colossal.Logging.ILog baseLog`  

```csharp
protected static Colossal.Logging.ILog baseLog;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```

- `public Game.Prefabs.PrefabBase prefab { get; set }`  

```csharp
public Game.Prefabs.PrefabBase prefab { get; set; }
```

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `protected ComponentBase()`  

```csharp
protected ComponentBase();
```


## Methods

- `public CompareTo(System.Object obj) : System.Int32`  

```csharp
public int CompareTo(object obj)
	{
		if (obj == null)
		{
			return 1;
		}
		ComponentBase componentBase = obj as ComponentBase;
		if (componentBase != null)
		{
			return base.name.CompareTo(componentBase.name);
		}
		throw new ArgumentException("Object is not a ComponentBase");
	}
```

- `public abstract GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public abstract System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public GetComponent<T>() : T`  

```csharp
public T GetComponent<T>();
```

- `public GetComponentExactly(System.Type type) : Game.Prefabs.ComponentBase`  

```csharp
public ComponentBase GetComponentExactly(Type type)
	{
		if (prefab == null)
		{
			throw new NullReferenceException($"GetComponentExactly<{type}>() -> prefab is null");
		}
		if (prefab.TryGetExactly(type, out var component))
		{
			return component;
		}
		return null;
	}
```

- `public GetComponents<T>(System.Collections.Generic.List<T> list) : System.Boolean`  

```csharp
public System.Boolean GetComponents<T>(System.Collections.Generic.List<T> list);
```

- `public virtual GetDebugString() : System.String`  

```csharp
public virtual string GetDebugString()
	{
		return GetType().Name;
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual void GetDependencies(List<PrefabBase> prefabs)
	{
	}
```

- `public abstract GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public abstract System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual void Initialize(EntityManager entityManager, Entity entity)
	{
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual void LateInitialize(EntityManager entityManager, Entity entity)
	{
	}
```

- `protected virtual OnDisable() : System.Void`  

```csharp
protected virtual void OnDisable()
	{
	}
```

- `protected virtual OnEnable() : System.Void`  

```csharp
protected virtual void OnEnable()
	{
		baseLog = LogManager.GetLogger("SceneFlow");
	}
```


