# Game.Prefabs.Hospital

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Hospital : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_AmbulanceCapacity;
    public System.Int32 m_MedicalHelicopterCapacity;
    public System.Int32 m_PatientCapacity;
    public System.Int32 m_TreatmentBonus;
    public Unity.Mathematics.int2 m_HealthRange;
    public System.Boolean m_TreatDiseases;
    public System.Boolean m_TreatInjuries;

    public Hospital();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_AmbulanceCapacity`  

```csharp
public System.Int32 m_AmbulanceCapacity;
```

- `public System.Int32 m_MedicalHelicopterCapacity`  

```csharp
public System.Int32 m_MedicalHelicopterCapacity;
```

- `public System.Int32 m_PatientCapacity`  

```csharp
public System.Int32 m_PatientCapacity;
```

- `public System.Int32 m_TreatmentBonus`  

```csharp
public System.Int32 m_TreatmentBonus;
```

- `public Unity.Mathematics.int2 m_HealthRange`  

```csharp
public Unity.Mathematics.int2 m_HealthRange;
```

- `public System.Boolean m_TreatDiseases`  

```csharp
public System.Boolean m_TreatDiseases;
```

- `public System.Boolean m_TreatInjuries`  

```csharp
public System.Boolean m_TreatInjuries;
```


## Constructors

- `public Hospital()`  

```csharp
public Hospital();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (GetComponent<ServiceUpgrade>() == null)
		{
			components.Add(ComponentType.ReadWrite<Game.Buildings.Hospital>());
			if (GetComponent<CityServiceBuilding>() != null)
			{
				components.Add(ComponentType.ReadWrite<Efficiency>());
				components.Add(ComponentType.ReadWrite<ServiceUsage>());
			}
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
			if (GetComponent<UniqueObject>() == null)
			{
				components.Add(ComponentType.ReadWrite<ServiceDistrict>());
			}
			if (m_PatientCapacity != 0)
			{
				components.Add(ComponentType.ReadWrite<Patient>());
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<HospitalData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.Hospital>());
		components.Add(ComponentType.ReadWrite<ServiceDispatch>());
		components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		components.Add(ComponentType.ReadWrite<ServiceUsage>());
		if (m_PatientCapacity != 0)
		{
			components.Add(ComponentType.ReadWrite<Patient>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new HospitalData
		{
			m_AmbulanceCapacity = m_AmbulanceCapacity,
			m_MedicalHelicopterCapacity = m_MedicalHelicopterCapacity,
			m_PatientCapacity = m_PatientCapacity,
			m_TreatmentBonus = m_TreatmentBonus,
			m_HealthRange = m_HealthRange,
			m_TreatDiseases = m_TreatDiseases,
			m_TreatInjuries = m_TreatInjuries
		});
		entityManager.SetComponentData(entity, new UpdateFrameData(1));
	}
```


