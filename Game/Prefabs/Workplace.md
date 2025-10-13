# Game.Prefabs.Workplace

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Workplace : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_Workplaces;
    public System.Int32 m_MinimumWorkersLimit;
    public Game.Prefabs.WorkplaceComplexity m_Complexity;
    public System.Single m_EveningShiftProbability;
    public System.Single m_NightShiftProbability;

    public Workplace();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_Workplaces`  

```csharp
public System.Int32 m_Workplaces;
```

- `public System.Int32 m_MinimumWorkersLimit`  

```csharp
public System.Int32 m_MinimumWorkersLimit;
```

- `public Game.Prefabs.WorkplaceComplexity m_Complexity`  

```csharp
public Game.Prefabs.WorkplaceComplexity m_Complexity;
```

- `public System.Single m_EveningShiftProbability`  

```csharp
public System.Single m_EveningShiftProbability;
```

- `public System.Single m_NightShiftProbability`  

```csharp
public System.Single m_NightShiftProbability;
```


## Constructors

- `public Workplace()`  

```csharp
public Workplace();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (GetComponent<ServiceUpgrade>() == null && m_Workplaces > 0)
		{
			components.Add(ComponentType.ReadWrite<WorkProvider>());
			components.Add(ComponentType.ReadWrite<Employee>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<WorkplaceData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		if (m_Workplaces > 0)
		{
			components.Add(ComponentType.ReadWrite<WorkProvider>());
			components.Add(ComponentType.ReadWrite<Employee>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new WorkplaceData
		{
			m_MaxWorkers = m_Workplaces,
			m_MinimumWorkersLimit = m_MinimumWorkersLimit,
			m_Complexity = m_Complexity,
			m_EveningShiftProbability = m_EveningShiftProbability,
			m_NightShiftProbability = m_NightShiftProbability
		});
	}
```


