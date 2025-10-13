# Game.Prefabs.ServiceCompany

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ServiceCompany : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_MaxService;
    public System.Single m_MaxWorkersPerCell;
    public System.Int32 m_ServiceConsuming;

    public ServiceCompany();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_MaxService`  

```csharp
public System.Int32 m_MaxService;
```

- `public System.Single m_MaxWorkersPerCell`  

```csharp
public System.Single m_MaxWorkersPerCell;
```

- `public System.Int32 m_ServiceConsuming`  

```csharp
public System.Int32 m_ServiceConsuming;
```


## Constructors

- `public ServiceCompany()`  

```csharp
public ServiceCompany();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ServiceAvailable>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ServiceCompanyData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new ServiceCompanyData
		{
			m_MaxService = m_MaxService,
			m_WorkPerUnit = 0,
			m_MaxWorkersPerCell = m_MaxWorkersPerCell,
			m_ServiceConsuming = m_ServiceConsuming
		});
	}
```


