# Game.Prefabs.FireStation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class FireStation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_FireEngineCapacity;
    public System.Int32 m_FireHelicopterCapacity;
    public System.Int32 m_DisasterResponseCapacity;
    public System.Single m_VehicleEfficiency;

    public FireStation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_FireEngineCapacity`  

```csharp
public System.Int32 m_FireEngineCapacity;
```

- `public System.Int32 m_FireHelicopterCapacity`  

```csharp
public System.Int32 m_FireHelicopterCapacity;
```

- `public System.Int32 m_DisasterResponseCapacity`  

```csharp
public System.Int32 m_DisasterResponseCapacity;
```

- `public System.Single m_VehicleEfficiency`  

```csharp
public System.Single m_VehicleEfficiency;
```


## Constructors

- `public FireStation()`  

```csharp
public FireStation();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.FireStation>());
		if (GetComponent<ServiceUpgrade>() == null)
		{
			if (GetComponent<CityServiceBuilding>() != null)
			{
				components.Add(ComponentType.ReadWrite<Efficiency>());
			}
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
			if (GetComponent<UniqueObject>() == null)
			{
				components.Add(ComponentType.ReadWrite<ServiceDistrict>());
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<FireStationData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.FireStation>());
		components.Add(ComponentType.ReadWrite<ServiceDispatch>());
		components.Add(ComponentType.ReadWrite<OwnedVehicle>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new FireStationData
		{
			m_FireEngineCapacity = m_FireEngineCapacity,
			m_FireHelicopterCapacity = m_FireHelicopterCapacity,
			m_DisasterResponseCapacity = m_DisasterResponseCapacity,
			m_VehicleEfficiency = m_VehicleEfficiency
		});
		entityManager.SetComponentData(entity, new UpdateFrameData(7));
	}
```


