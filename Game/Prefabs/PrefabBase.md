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
public ComponentBase AddComponent(Type type)
	{
		if (Has(type))
		{
			throw new InvalidOperationException("Component already exists");
		}
		ComponentBase componentBase = (ComponentBase)ScriptableObject.CreateInstance(type);
		componentBase.name = type.Name;
		componentBase.prefab = this;
		components.Add(componentBase);
		isDirty = true;
		return componentBase;
	}
```

- `public AddComponentFrom<T>(T from) : T`  

```csharp
public T AddComponentFrom<T>(T from);
```

- `public AddComponentFrom(Game.Prefabs.ComponentBase from) : Game.Prefabs.ComponentBase`  

```csharp
public ComponentBase AddComponentFrom(ComponentBase from)
	{
		Type type = from.GetType();
		ComponentBase componentBase = AddOrGetComponent(type);
		JsonUtility.FromJsonOverwrite(JsonUtility.ToJson(from), componentBase);
		return componentBase;
	}
```

- `public AddOrGetComponent<T>() : T`  

```csharp
public T AddOrGetComponent<T>();
```

- `public AddOrGetComponent(System.Type type) : Game.Prefabs.ComponentBase`  

```csharp
public ComponentBase AddOrGetComponent(Type type)
	{
		if (!TryGetExactly(type, out var component))
		{
			return AddComponent(type);
		}
		return component;
	}
```

- `public Clone(System.String newName = null) : Game.Prefabs.PrefabBase`  

```csharp
public PrefabBase Clone(string newName = null)
	{
		PrefabBase prefabBase = (PrefabBase)ScriptableObject.CreateInstance(GetType());
		ProxyObject proxyObject = JSON.Load(JsonUtility.ToJson(this)) as ProxyObject;
		if (proxyObject != null)
		{
			proxyObject.Remove("components");
			proxyObject.Remove("m_NameOverride");
		}
		JsonUtility.FromJsonOverwrite(proxyObject.ToJSON(), prefabBase);
		prefabBase.name = newName ?? (base.name + " (copy)");
		foreach (ComponentBase component in components)
		{
			prefabBase.AddComponentFrom(component);
		}
		return prefabBase;
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PrefabRef>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PrefabData>());
		components.Add(ComponentType.ReadWrite<LoadedIndex>());
	}
```

- `public GetPrefabID() : Game.Prefabs.PrefabID`  

```csharp
public PrefabID GetPrefabID()
	{
		return new PrefabID(this);
	}
```

- `public Has<T>() : System.Boolean`  

```csharp
public System.Boolean Has<T>();
```

- `public Has(System.Type type) : System.Boolean`  

```csharp
public bool Has(Type type)
	{
		if (GetType() == type)
		{
			return true;
		}
		foreach (ComponentBase component in components)
		{
			if (component.GetType() == type)
			{
				return true;
			}
		}
		return false;
	}
```

- `public HasSubclassOf(System.Type type) : System.Boolean`  

```csharp
public bool HasSubclassOf(Type type)
	{
		if (GetType().IsSubclassOf(type))
		{
			return true;
		}
		foreach (ComponentBase component in components)
		{
			if (component.GetType().IsSubclassOf(type))
			{
				return true;
			}
		}
		return false;
	}
```

- `public virtual OnAfterDeserialize() : System.Void`  

```csharp
public virtual void OnAfterDeserialize()
	{
		base.prefab = this;
	}
```

- `public OnBeforeSerialize() : System.Void`  

```csharp
public void OnBeforeSerialize()
	{
	}
```

- `protected virtual OnEnable() : System.Void`  

```csharp
protected override void OnEnable()
	{
		base.OnEnable();
		base.prefab = this;
		foreach (ComponentBase component in components)
		{
			if (component != null || component.prefab == component)
			{
				component.prefab = this;
				continue;
			}
			if (component == null)
			{
				ComponentBase.baseLog.ErrorFormat(base.prefab, "Null component on prefab: {0}", base.prefab.name);
			}
			if (component.prefab != component)
			{
				ComponentBase.baseLog.ErrorFormat(base.prefab, "Component on prefab {0} is referenced from another prefab prefab: {1}", base.prefab.name, component.prefab.name);
			}
		}
		components.RemoveAll((ComponentBase x) => x == null);
		thumbnailUrl = "thumbnail://ThumbnailCamera/" + Uri.EscapeDataString(GetType().Name) + "/" + Uri.EscapeDataString(base.name);
	}
```

- `public Remove<T>() : System.Void`  

```csharp
public System.Void Remove<T>();
```

- `public Remove(System.Type type) : System.Void`  

```csharp
public void Remove(Type type)
	{
		int num = -1;
		for (int i = 0; i < components.Count; i++)
		{
			if (components[i].GetType() == type)
			{
				num = i;
				break;
			}
		}
		if (num >= 0)
		{
			components.RemoveAt(num);
			isDirty = true;
		}
	}
```

- `public ReplaceComponentWith(Game.Prefabs.ComponentBase target, System.Type type) : Game.Prefabs.ComponentBase`  

```csharp
public ComponentBase ReplaceComponentWith(ComponentBase target, Type type)
	{
		ComponentBase componentBase = (ComponentBase)ScriptableObject.CreateInstance(type);
		componentBase.prefab = this;
		int index = components.IndexOf(target);
		components[index] = componentBase;
		isDirty = true;
		return componentBase;
	}
```

- `public virtual Reset() : System.Void`  

```csharp
public virtual void Reset()
	{
		isDirty = true;
	}
```

- `public TryGet<T>(T& component) : System.Boolean`  

```csharp
public System.Boolean TryGet<T>(T& component);
```

- `public TryGet(System.Type type, Game.Prefabs.ComponentBase& component) : System.Boolean`  

```csharp
public bool TryGet(Type type, out ComponentBase component)
	{
		Type type2 = GetType();
		component = null;
		if (type2 == type || type2.IsSubclassOf(type))
		{
			component = this;
			return true;
		}
		foreach (ComponentBase component2 in components)
		{
			Type type3 = component2.GetType();
			if (type3 == type || type3.IsSubclassOf(type))
			{
				component = component2;
				return true;
			}
		}
		return false;
	}
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
public bool TryGetExactly(Type type, out ComponentBase component)
	{
		component = null;
		if (GetType() == type)
		{
			component = this;
			return true;
		}
		foreach (ComponentBase component2 in components)
		{
			if (component2.GetType() == type)
			{
				component = component2;
				return true;
			}
		}
		return false;
	}
```


## Nested types

- `Game.Prefabs.PrefabBase+<>c`  

