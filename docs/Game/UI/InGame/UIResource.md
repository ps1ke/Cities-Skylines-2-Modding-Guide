# Game.UI.InGame.UIResource

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IComparable<Game.UI.InGame.UIResource>`, `System.IEquatable<Game.UI.InGame.UIResource>`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly Game.Economy.Resource <key>k__BackingField`  
- `private readonly System.Int32 <amount>k__BackingField`  
- `private readonly Game.UI.InGame.UIResource+ResourceStatus <status>k__BackingField`  
- `private readonly System.Boolean <isRawMaterial>k__BackingField`  

## Properties

- `public Game.Economy.Resource key { get }`  
- `public System.Int32 amount { get }`  
- `public Game.UI.InGame.UIResource+ResourceStatus status { get }`  
- `public System.Boolean isRawMaterial { get }`  

## Constructors

- `public UIResource(Game.Economy.Resource resource, System.Int32 amount, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  
- `public UIResource(Game.Economy.Resources resource, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  
- `public UIResource(Game.Economy.Resource resource, System.Int32 amount, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  
- `public UIResource(Game.Economy.Resources resource, Game.UI.InGame.UIResource+StorageType storageType, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs prefabs)`  

## Methods

- `public static CategorizeResources(Game.Economy.Resource resource, System.Int32 amount, Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials, Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods, Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail, Unity.Entities.EntityManager entityManager, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.UI.InGame.UIResource+StorageType storageType = None) : System.Void`  
- `public CompareTo(Game.UI.InGame.UIResource other) : System.Int32`  
- `public Equals(Game.UI.InGame.UIResource other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.InGame.UIResource+ResourceStatus`  
- `Game.UI.InGame.UIResource+StorageType`  

