# Game.Prefabs.BuildingPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.StaticObjectPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingPrefab : Game.Prefabs.StaticObjectPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.BuildingAccessType m_AccessType;
    public System.Int32 m_LotWidth;
    public System.Int32 m_LotDepth;

    public System.Int32 lotSize { get; }

    public BuildingPrefab();

    public System.Void AddUpgrade(Unity.Entities.EntityManager entityManager, Game.Prefabs.ServiceUpgrade upgrade);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    protected virtual System.Void RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.BuildingAccessType m_AccessType`  

```csharp
public Game.Prefabs.BuildingAccessType m_AccessType;
```

- `public System.Int32 m_LotWidth`  

```csharp
public System.Int32 m_LotWidth;
```

- `public System.Int32 m_LotDepth`  

```csharp
public System.Int32 m_LotDepth;
```


## Properties

- `public System.Int32 lotSize { get }`  

```csharp
public System.Int32 lotSize { get; }
```


## Constructors

- `public BuildingPrefab()`  

```csharp
public BuildingPrefab();
```


## Methods

- `public AddUpgrade(Unity.Entities.EntityManager entityManager, Game.Prefabs.ServiceUpgrade upgrade) : System.Void`  

```csharp
public System.Void AddUpgrade(Unity.Entities.EntityManager entityManager, Game.Prefabs.ServiceUpgrade upgrade);
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `protected virtual RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected virtual System.Void RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


