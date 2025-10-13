# Game.Prefabs.ServiceCoverage

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ServiceCoverage : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_Range;
    public System.Single m_Capacity;
    public System.Single m_Magnitude;

    public ServiceCoverage();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_Range`  

```csharp
public System.Single m_Range;
```

- `public System.Single m_Capacity`  

```csharp
public System.Single m_Capacity;
```

- `public System.Single m_Magnitude`  

```csharp
public System.Single m_Magnitude;
```


## Constructors

- `public ServiceCoverage()`  

```csharp
public ServiceCoverage();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<CoverageServiceType>());
		components.Add(ComponentType.ReadWrite<CoverageElement>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<CoverageData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		CoverageData componentData = new CoverageData
		{
			m_Range = m_Range,
			m_Capacity = m_Capacity,
			m_Magnitude = m_Magnitude
		};
		if (entityManager.HasComponent<HospitalData>(entity))
		{
			componentData.m_Service = CoverageService.Healthcare;
		}
		else if (entityManager.HasComponent<FireStationData>(entity))
		{
			componentData.m_Service = CoverageService.FireRescue;
		}
		else if (entityManager.HasComponent<PoliceStationData>(entity))
		{
			componentData.m_Service = CoverageService.Police;
		}
		else if (entityManager.HasComponent<ParkData>(entity))
		{
			componentData.m_Service = CoverageService.Park;
		}
		else if (entityManager.HasComponent<PostFacilityData>(entity) || entityManager.HasComponent<MailBoxData>(entity))
		{
			componentData.m_Service = CoverageService.PostService;
		}
		else if (entityManager.HasComponent<SchoolData>(entity))
		{
			componentData.m_Service = CoverageService.Education;
		}
		else if (entityManager.HasComponent<EmergencyShelterData>(entity))
		{
			componentData.m_Service = CoverageService.EmergencyShelter;
		}
		else if (entityManager.HasComponent<WelfareOfficeData>(entity))
		{
			componentData.m_Service = CoverageService.Welfare;
		}
		else
		{
			ComponentBase.baseLog.ErrorFormat(base.prefab, "Unknown coverage service type: {0}", base.prefab.name);
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


