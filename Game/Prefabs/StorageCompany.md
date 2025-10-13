# Game.Prefabs.StorageCompany

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class StorageCompany : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.IndustrialProcess process;
    public System.Int32 transports;

    public StorageCompany();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.IndustrialProcess process`  

```csharp
public Game.Prefabs.IndustrialProcess process;
```

- `public System.Int32 transports`  

```csharp
public System.Int32 transports;
```


## Constructors

- `public StorageCompany()`  

```csharp
public StorageCompany();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (transports > 0)
		{
			components.Add(ComponentType.ReadWrite<TransportCompany>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		}
		components.Add(ComponentType.ReadWrite<Game.Companies.StorageCompany>());
		components.Add(ComponentType.ReadWrite<TradeCost>());
		components.Add(ComponentType.ReadWrite<ResourceSeller>());
		components.Add(ComponentType.ReadWrite<StorageTransferRequest>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<StorageCompanyData>());
		components.Add(ComponentType.ReadWrite<IndustrialProcessData>());
		if (transports > 0)
		{
			components.Add(ComponentType.ReadWrite<TransportCompanyData>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new IndustrialProcessData
		{
			m_Input1 = 
			{
				m_Amount = process.m_Input1.m_Amount,
				m_Resource = EconomyUtils.GetResource(process.m_Input1.m_Resource)
			},
			m_Input2 = 
			{
				m_Amount = process.m_Input2.m_Amount,
				m_Resource = EconomyUtils.GetResource(process.m_Input2.m_Resource)
			},
			m_Output = 
			{
				m_Amount = process.m_Output.m_Amount,
				m_Resource = EconomyUtils.GetResource(process.m_Output.m_Resource)
			},
			m_MaxWorkersPerCell = process.m_MaxWorkersPerCell
		});
		StorageCompanyData componentData = new StorageCompanyData
		{
			m_StoredResources = EconomyUtils.GetResource(process.m_Output.m_Resource)
		};
		entityManager.SetComponentData(entity, componentData);
		if (transports > 0)
		{
			entityManager.SetComponentData(entity, new TransportCompanyData
			{
				m_MaxTransports = transports
			});
		}
	}
```


