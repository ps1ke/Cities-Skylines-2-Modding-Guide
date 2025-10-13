# Game.Prefabs.ExtractorFacility

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ExtractorFacility : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Colossal.Mathematics.Bounds1 m_RotationRange;
    public Colossal.Mathematics.Bounds1 m_HeightOffset;
    public System.Boolean m_RouteNeeded;
    public System.Boolean m_NetNeeded;

    public ExtractorFacility();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_RotationRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_RotationRange;
```

- `public Colossal.Mathematics.Bounds1 m_HeightOffset`  

```csharp
public Colossal.Mathematics.Bounds1 m_HeightOffset;
```

- `public System.Boolean m_RouteNeeded`  

```csharp
public System.Boolean m_RouteNeeded;
```

- `public System.Boolean m_NetNeeded`  

```csharp
public System.Boolean m_NetNeeded;
```


## Constructors

- `public ExtractorFacility()`  

```csharp
public ExtractorFacility();
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


