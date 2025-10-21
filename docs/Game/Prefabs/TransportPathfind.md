# Game.Prefabs.TransportPathfind

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportPathfind : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.PathfindCostInfo m_OrderingCost;
    public Game.Prefabs.PathfindCostInfo m_StartingCost;
    public Game.Prefabs.PathfindCostInfo m_TravelCost;

    public TransportPathfind();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PathfindCostInfo m_OrderingCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_OrderingCost;
```

- `public Game.Prefabs.PathfindCostInfo m_StartingCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_StartingCost;
```

- `public Game.Prefabs.PathfindCostInfo m_TravelCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_TravelCost;
```


## Constructors

- `public TransportPathfind()`  

```csharp
public TransportPathfind();
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


