# Game.Prefabs.ProcessingCompany

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ProcessingCompany : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.IndustrialProcess process;
    public System.Int32 transports;

    public ProcessingCompany();

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

- `public ProcessingCompany()`  

```csharp
public ProcessingCompany();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Companies.ProcessingCompany>());
		components.Add(ComponentType.ReadWrite<TaxPayer>());
		if (process.m_Input1.m_Resource != ResourceInEditor.NoResource || process.m_Input2.m_Resource != ResourceInEditor.NoResource)
		{
			components.Add(ComponentType.ReadWrite<BuyingCompany>());
		}
		if (process.m_Output.m_Resource == ResourceInEditor.Lodging)
		{
			components.Add(ComponentType.ReadWrite<LodgingProvider>());
			components.Add(ComponentType.ReadWrite<Renter>());
		}
		components.Add(ComponentType.ReadWrite<ResourceSeller>());
		components.Add(ComponentType.ReadWrite<Profitability>());
		components.Add(ComponentType.ReadWrite<TradeCost>());
		if (transports > 0)
		{
			components.Add(ComponentType.ReadWrite<TransportCompany>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
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
		if (transports > 0)
		{
			entityManager.SetComponentData(entity, new TransportCompanyData
			{
				m_MaxTransports = transports
			});
		}
	}
```


