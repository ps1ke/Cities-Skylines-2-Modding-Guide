# Game.Prefabs.OutsideConnection

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class OutsideConnection : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Economy.ResourceInEditor[] m_TradedResources;
    public System.Boolean m_Commuting;
    public Game.Prefabs.OutsideConnectionTransferType m_TransferType;
    public System.Single m_Remoteness;

    public OutsideConnection();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Economy.ResourceInEditor[] m_TradedResources`  

```csharp
public Game.Economy.ResourceInEditor[] m_TradedResources;
```

- `public System.Boolean m_Commuting`  

```csharp
public System.Boolean m_Commuting;
```

- `public Game.Prefabs.OutsideConnectionTransferType m_TransferType`  

```csharp
public Game.Prefabs.OutsideConnectionTransferType m_TransferType;
```

- `public System.Single m_Remoteness`  

```csharp
public System.Single m_Remoteness;
```


## Constructors

- `public OutsideConnection()`  

```csharp
public OutsideConnection();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Objects.OutsideConnection>());
		components.Add(ComponentType.ReadWrite<Resources>());
		components.Add(ComponentType.ReadWrite<Game.Companies.StorageCompany>());
		components.Add(ComponentType.ReadWrite<TradeCost>());
		components.Add(ComponentType.ReadWrite<StorageTransferRequest>());
		components.Add(ComponentType.ReadWrite<TripNeeded>());
		components.Add(ComponentType.ReadWrite<ResourceSeller>());
		components.Add(ComponentType.ReadWrite<TransportCompany>());
		components.Add(ComponentType.ReadWrite<OwnedVehicle>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<OutsideConnectionData>());
		components.Add(ComponentType.ReadWrite<StorageCompanyData>());
		components.Add(ComponentType.ReadWrite<TransportCompanyData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new OutsideConnectionData
		{
			m_Type = m_TransferType,
			m_Remoteness = m_Remoteness
		});
		StorageCompanyData componentData = new StorageCompanyData
		{
			m_StoredResources = Resource.NoResource
		};
		if (m_TradedResources != null && m_TradedResources.Length != 0)
		{
			for (int i = 0; i < m_TradedResources.Length; i++)
			{
				componentData.m_StoredResources |= EconomyUtils.GetResource(m_TradedResources[i]);
			}
		}
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, new TransportCompanyData
		{
			m_MaxTransports = int.MaxValue
		});
	}
```


