# Game.Prefabs.RenterObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RenterObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_RequireEmpty;
    public System.Boolean m_RequireRenter;
    public System.Boolean m_RequireGoodWealth;
    public System.Boolean m_RequireDogs;
    public System.Boolean m_RequireHomeless;
    public System.Boolean m_RequireChildren;
    public System.Boolean m_RequireTeens;

    public RenterObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Boolean m_RequireEmpty`  

```csharp
public System.Boolean m_RequireEmpty;
```

- `public System.Boolean m_RequireRenter`  

```csharp
public System.Boolean m_RequireRenter;
```

- `public System.Boolean m_RequireGoodWealth`  

```csharp
public System.Boolean m_RequireGoodWealth;
```

- `public System.Boolean m_RequireDogs`  

```csharp
public System.Boolean m_RequireDogs;
```

- `public System.Boolean m_RequireHomeless`  

```csharp
public System.Boolean m_RequireHomeless;
```

- `public System.Boolean m_RequireChildren`  

```csharp
public System.Boolean m_RequireChildren;
```

- `public System.Boolean m_RequireTeens`  

```csharp
public System.Boolean m_RequireTeens;
```


## Constructors

- `public RenterObject()`  

```csharp
public RenterObject();
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

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


