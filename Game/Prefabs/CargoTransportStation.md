# Game.Prefabs.CargoTransportStation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`, `RequireComponent`  

## Code

```csharp
public class CargoTransportStation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public Game.Economy.ResourceInEditor[] m_TradedResources;
    public System.Int32 transports;
    public Game.Vehicles.EnergyTypes m_CarRefuelTypes;
    public Game.Vehicles.EnergyTypes m_TrainRefuelTypes;
    public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes;
    public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes;
    public System.Single m_LoadingFactor;
    public System.Single m_WorkMultiplier;
    public Unity.Mathematics.int2 m_TransportInterval;

    public CargoTransportStation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Economy.ResourceInEditor[] m_TradedResources`  

```csharp
public Game.Economy.ResourceInEditor[] m_TradedResources;
```

- `public System.Int32 transports`  

```csharp
public System.Int32 transports;
```

- `public Game.Vehicles.EnergyTypes m_CarRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_CarRefuelTypes;
```

- `public Game.Vehicles.EnergyTypes m_TrainRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_TrainRefuelTypes;
```

- `public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes;
```

- `public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes;
```

- `public System.Single m_LoadingFactor`  

```csharp
public System.Single m_LoadingFactor;
```

- `public System.Single m_WorkMultiplier`  

```csharp
public System.Single m_WorkMultiplier;
```

- `public Unity.Mathematics.int2 m_TransportInterval`  

```csharp
public Unity.Mathematics.int2 m_TransportInterval;
```


## Constructors

- `public CargoTransportStation()`  

```csharp
public CargoTransportStation();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.TransportStation>());
		components.Add(ComponentType.ReadWrite<Game.Buildings.CargoTransportStation>());
		if (GetComponent<ServiceUpgrade>() == null)
		{
			if (GetComponent<CityServiceBuilding>() != null)
			{
				components.Add(ComponentType.ReadWrite<Efficiency>());
			}
			components.Add(ComponentType.ReadWrite<Game.Companies.StorageCompany>());
			components.Add(ComponentType.ReadWrite<TradeCost>());
			components.Add(ComponentType.ReadWrite<StorageTransferRequest>());
			components.Add(ComponentType.ReadWrite<Game.Economy.Resources>());
			if (transports > 0)
			{
				components.Add(ComponentType.ReadWrite<TransportCompany>());
				components.Add(ComponentType.ReadWrite<OwnedVehicle>());
			}
		}
		if (m_WorkMultiplier > 0f)
		{
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<TransportStationData>());
		components.Add(ComponentType.ReadWrite<CargoTransportStationData>());
		components.Add(ComponentType.ReadWrite<StorageCompanyData>());
		components.Add(ComponentType.ReadWrite<TransportCompanyData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.TransportStation>());
		components.Add(ComponentType.ReadWrite<Game.Buildings.CargoTransportStation>());
		components.Add(ComponentType.ReadWrite<Game.Companies.StorageCompany>());
		components.Add(ComponentType.ReadWrite<TradeCost>());
		components.Add(ComponentType.ReadWrite<StorageTransferRequest>());
		components.Add(ComponentType.ReadWrite<Game.Economy.Resources>());
		if (transports > 0)
		{
			components.Add(ComponentType.ReadWrite<TransportCompany>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		StorageCompanyData componentData = new StorageCompanyData
		{
			m_StoredResources = Resource.NoResource
		};
		if (m_TradedResources != null && m_TradedResources.Length != 0)
		{
			for (int i = 0; i < m_TradedResources.Length; i++)
			{
				componentData.m_StoredResources |= EconomyUtils.GetResource(m_TradedResources[i]);
				componentData.m_TransportInterval = m_TransportInterval;
			}
		}
		entityManager.SetComponentData(entity, componentData);
		if (transports > 0)
		{
			entityManager.SetComponentData(entity, new TransportCompanyData
			{
				m_MaxTransports = transports
			});
		}
		TransportStationData componentData2 = entityManager.GetComponentData<TransportStationData>(entity);
		componentData2.m_CarRefuelTypes |= m_CarRefuelTypes;
		componentData2.m_TrainRefuelTypes |= m_TrainRefuelTypes;
		componentData2.m_WatercraftRefuelTypes |= m_WatercraftRefuelTypes;
		componentData2.m_AircraftRefuelTypes |= m_AircraftRefuelTypes;
		componentData2.m_LoadingFactor = m_LoadingFactor;
		entityManager.SetComponentData(entity, componentData2);
		CargoTransportStationData componentData3 = default(CargoTransportStationData);
		componentData3.m_WorkMultiplier = m_WorkMultiplier;
		entityManager.SetComponentData(entity, componentData3);
		entityManager.SetComponentData(entity, new UpdateFrameData(0));
	}
```


