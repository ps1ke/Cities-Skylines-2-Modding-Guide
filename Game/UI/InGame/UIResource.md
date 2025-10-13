# Game.UI.InGame.UIResource

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IComparable<Game.UI.InGame.UIResource>`, `System.IEquatable<Game.UI.InGame.UIResource>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct UIResource : Colossal.UI.Binding.IJsonWritable, System.IComparable<Game.UI.InGame.UIResource>, System.IEquatable<Game.UI.InGame.UIResource>
{
    private readonly Game.Economy.Resource <key>k__BackingField;
    private readonly System.Int32 <amount>k__BackingField;
    private readonly Game.UI.InGame.UIResource+ResourceStatus <status>k__BackingField;
    private readonly System.Boolean <isRawMaterial>k__BackingField;

    public Game.Economy.Resource key { get; }
    public System.Int32 amount { get; }
    public Game.UI.InGame.UIResource+ResourceStatus status { get; }
    public System.Boolean isRawMaterial { get; }

    public UIResource(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs);
    public UIResource(Game.Economy.Resources resource, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs);
    public UIResource(Game.Economy.Resource resource, System.Int32 amount, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs);
    public UIResource(Game.Economy.Resources resource, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs);

    public static System.Void CategorizeResources(Game.Economy.Resource resource, System.Int32 amount, Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials, Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods, Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.UI.InGame.UIResource+StorageType storageType);
    public System.Int32 CompareTo(Game.UI.InGame.UIResource other);
    public System.Boolean Equals(Game.UI.InGame.UIResource other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly Game.Economy.Resource <key>k__BackingField`  

```csharp
private readonly Game.Economy.Resource <key>k__BackingField;
```

- `private readonly System.Int32 <amount>k__BackingField`  

```csharp
private readonly System.Int32 <amount>k__BackingField;
```

- `private readonly Game.UI.InGame.UIResource+ResourceStatus <status>k__BackingField`  

```csharp
private readonly Game.UI.InGame.UIResource+ResourceStatus <status>k__BackingField;
```

- `private readonly System.Boolean <isRawMaterial>k__BackingField`  

```csharp
private readonly System.Boolean <isRawMaterial>k__BackingField;
```


## Properties

- `public Game.Economy.Resource key { get }`  

```csharp
public Game.Economy.Resource key { get; }
```

- `public System.Int32 amount { get }`  

```csharp
public System.Int32 amount { get; }
```

- `public Game.UI.InGame.UIResource+ResourceStatus status { get }`  

```csharp
public Game.UI.InGame.UIResource+ResourceStatus status { get; }
```

- `public System.Boolean isRawMaterial { get }`  

```csharp
public System.Boolean isRawMaterial { get; }
```


## Constructors

- `public UIResource(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  

```csharp
public UIResource(Resource resource, int amount, EntityManager entityManager, ResourcePrefabs prefabs)
	{
		key = resource;
		this.amount = amount;
		status = ResourceStatus.None;
		if (entityManager.TryGetComponent<ResourceData>(prefabs[resource], out var component))
		{
			isRawMaterial = component.m_IsMaterial;
		}
		else
		{
			isRawMaterial = false;
		}
	}
```

- `public UIResource(Game.Economy.Resources resource, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  

```csharp
public UIResource(Resource resource, int amount, EntityManager entityManager, ResourcePrefabs prefabs)
	{
		key = resource;
		this.amount = amount;
		status = ResourceStatus.None;
		if (entityManager.TryGetComponent<ResourceData>(prefabs[resource], out var component))
		{
			isRawMaterial = component.m_IsMaterial;
		}
		else
		{
			isRawMaterial = false;
		}
	}
```

- `public UIResource(Game.Economy.Resource resource, System.Int32 amount, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  

```csharp
public UIResource(Resource resource, int amount, EntityManager entityManager, ResourcePrefabs prefabs)
	{
		key = resource;
		this.amount = amount;
		status = ResourceStatus.None;
		if (entityManager.TryGetComponent<ResourceData>(prefabs[resource], out var component))
		{
			isRawMaterial = component.m_IsMaterial;
		}
		else
		{
			isRawMaterial = false;
		}
	}
```

- `public UIResource(Game.Economy.Resources resource, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  

```csharp
public UIResource(Resource resource, int amount, EntityManager entityManager, ResourcePrefabs prefabs)
	{
		key = resource;
		this.amount = amount;
		status = ResourceStatus.None;
		if (entityManager.TryGetComponent<ResourceData>(prefabs[resource], out var component))
		{
			isRawMaterial = component.m_IsMaterial;
		}
		else
		{
			isRawMaterial = false;
		}
	}
```


## Methods

- `public static CategorizeResources(Game.Economy.Resource resource, System.Int32 amount, Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials, Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods, Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.UI.InGame.UIResource+StorageType storageType = None) : System.Void`  

```csharp
public static void CategorizeResources(Resource resource, int amount, NativeList<UIResource> rawMaterials, NativeList<UIResource> processedGoods, NativeList<UIResource> mail, EntityManager entityManager, ResourcePrefabs resourcePrefabs, StorageType storageType = StorageType.None)
	{
		ResourceData component;
		if ((resource & (Resource)28672uL) != Resource.NoResource)
		{
			mail.Add(new UIResource(resource, amount, storageType, entityManager, resourcePrefabs));
		}
		else if (entityManager.TryGetComponent<ResourceData>(resourcePrefabs[resource], out component) && component.m_IsMaterial)
		{
			rawMaterials.Add(new UIResource(resource, amount, storageType, entityManager, resourcePrefabs));
		}
		else
		{
			processedGoods.Add(new UIResource(resource, amount, storageType, entityManager, resourcePrefabs));
		}
	}
```

- `public CompareTo(Game.UI.InGame.UIResource other) : System.Int32`  

```csharp
public int CompareTo(UIResource other)
	{
		if ((other.key & (Resource)28672uL) != Resource.NoResource && (key & (Resource)28672uL) == Resource.NoResource)
		{
			return -1;
		}
		if ((key & (Resource)28672uL) != Resource.NoResource && (other.key & (Resource)28672uL) == Resource.NoResource)
		{
			return 1;
		}
		int num = other.isRawMaterial.CompareTo(isRawMaterial);
		if (num != 0)
		{
			return num;
		}
		return other.amount.CompareTo(amount);
	}
```

- `public Equals(Game.UI.InGame.UIResource other) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is UIResource other)
		{
			return Equals(other);
		}
		return false;
	}
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is UIResource other)
		{
			return Equals(other);
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return key.GetHashCode();
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("key");
		writer.Write(Enum.GetName(typeof(Resource), key));
		writer.PropertyName("amount");
		writer.Write(amount);
		writer.PropertyName("status");
		writer.Write(Enum.GetName(typeof(ResourceStatus), status));
		writer.TypeEnd();
	}
```


## Nested types

- `Game.UI.InGame.UIResource+ResourceStatus`  
- `Game.UI.InGame.UIResource+StorageType`  

