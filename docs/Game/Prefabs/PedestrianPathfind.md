# Game.Prefabs.PedestrianPathfind

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PedestrianPathfind : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.PathfindCostInfo m_WalkingCost;
    public Game.Prefabs.PathfindCostInfo m_CrosswalkCost;
    public Game.Prefabs.PathfindCostInfo m_UnsafeCrosswalkCost;
    public Game.Prefabs.PathfindCostInfo m_SpawnCost;

    public PedestrianPathfind();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PathfindCostInfo m_WalkingCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_WalkingCost;
```

- `public Game.Prefabs.PathfindCostInfo m_CrosswalkCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_CrosswalkCost;
```

- `public Game.Prefabs.PathfindCostInfo m_UnsafeCrosswalkCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_UnsafeCrosswalkCost;
```

- `public Game.Prefabs.PathfindCostInfo m_SpawnCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_SpawnCost;
```


## Constructors

- `public PedestrianPathfind()`  

```csharp
public PedestrianPathfind();
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


