# Game.Prefabs.Wildlife

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Wildlife : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Colossal.Mathematics.Bounds1 m_TripLength;
    public Colossal.Mathematics.Bounds1 m_IdleTime;
    public System.Int32 m_MinGroupMemberCount;
    public System.Int32 m_MaxGroupMemberCount;

    public Wildlife();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_TripLength`  

```csharp
public Colossal.Mathematics.Bounds1 m_TripLength;
```

- `public Colossal.Mathematics.Bounds1 m_IdleTime`  

```csharp
public Colossal.Mathematics.Bounds1 m_IdleTime;
```

- `public System.Int32 m_MinGroupMemberCount`  

```csharp
public System.Int32 m_MinGroupMemberCount;
```

- `public System.Int32 m_MaxGroupMemberCount`  

```csharp
public System.Int32 m_MaxGroupMemberCount;
```


## Constructors

- `public Wildlife()`  

```csharp
public Wildlife();
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


