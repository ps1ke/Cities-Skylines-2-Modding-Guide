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
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PathfindPedestrianData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new PathfindPedestrianData
		{
			m_WalkingCost = m_WalkingCost.ToPathfindCosts(),
			m_CrosswalkCost = m_CrosswalkCost.ToPathfindCosts(),
			m_UnsafeCrosswalkCost = m_UnsafeCrosswalkCost.ToPathfindCosts(),
			m_SpawnCost = m_SpawnCost.ToPathfindCosts()
		});
	}
```


