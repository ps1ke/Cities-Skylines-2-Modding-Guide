# Game.Prefabs.ExtractorArea

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ExtractorArea : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Areas.MapFeature m_MapFeature;
    public System.Single m_ObjectSpawnFactor;
    public System.Single m_MaxObjectArea;
    public System.Boolean m_RequireNaturalResource;
    public System.Single m_WorkAmountFactor;

    public ExtractorArea();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Areas.MapFeature m_MapFeature`  

```csharp
public Game.Areas.MapFeature m_MapFeature;
```

- `public System.Single m_ObjectSpawnFactor`  

```csharp
public System.Single m_ObjectSpawnFactor;
```

- `public System.Single m_MaxObjectArea`  

```csharp
public System.Single m_MaxObjectArea;
```

- `public System.Boolean m_RequireNaturalResource`  

```csharp
public System.Boolean m_RequireNaturalResource;
```

- `public System.Single m_WorkAmountFactor`  

```csharp
public System.Single m_WorkAmountFactor;
```


## Constructors

- `public ExtractorArea()`  

```csharp
public ExtractorArea();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


