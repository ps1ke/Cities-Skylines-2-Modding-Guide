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
public UIResource(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs);
```

- `public UIResource(Game.Economy.Resources resource, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  

```csharp
public UIResource(Game.Economy.Resources resource, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs);
```

- `public UIResource(Game.Economy.Resource resource, System.Int32 amount, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  

```csharp
public UIResource(Game.Economy.Resource resource, System.Int32 amount, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs);
```

- `public UIResource(Game.Economy.Resources resource, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  

```csharp
public UIResource(Game.Economy.Resources resource, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs);
```


## Methods

- `public static CategorizeResources(Game.Economy.Resource resource, System.Int32 amount, Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials, Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods, Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.UI.InGame.UIResource+StorageType storageType = None) : System.Void`  

```csharp
public static System.Void CategorizeResources(Game.Economy.Resource resource, System.Int32 amount, Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials, Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods, Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.UI.InGame.UIResource+StorageType storageType);
```

- `public CompareTo(Game.UI.InGame.UIResource other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.UIResource other);
```

- `public Equals(Game.UI.InGame.UIResource other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.InGame.UIResource other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.InGame.UIResource+ResourceStatus`  
- `Game.UI.InGame.UIResource+StorageType`  

