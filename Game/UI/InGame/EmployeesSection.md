# Game.UI.InGame.EmployeesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EmployeesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <employeeCount>k__BackingField;
    private System.Int32 <maxEmployees>k__BackingField;
    private Game.UI.InGame.EmploymentData <educationDataEmployees>k__BackingField;
    private Game.UI.InGame.EmploymentData <educationDataWorkplaces>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <districtBuildings>k__BackingField;
    private Unity.Entities.EntityQuery m_DistrictBuildingQuery;

    protected System.String group { protected get; }
    private System.Int32 employeeCount { private get; private set; }
    private System.Int32 maxEmployees { private get; private set; }
    private Game.UI.InGame.EmploymentData educationDataEmployees { private get; private set; }
    private Game.UI.InGame.EmploymentData educationDataWorkplaces { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> districtBuildings { private get; private set; }

    public EmployeesSection();

    private System.Void AddEmployees();
    private System.Void AddEmployees(Unity.Entities.Entity entity);
    private System.Boolean DisplayForDistrict();
    private Unity.Entities.Entity GetEntity(Unity.Entities.Entity entity);
    private System.Boolean HasEmployees(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Void UpdateForDistricts();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <employeeCount>k__BackingField`  

```csharp
private System.Int32 <employeeCount>k__BackingField;
```

- `private System.Int32 <maxEmployees>k__BackingField`  

```csharp
private System.Int32 <maxEmployees>k__BackingField;
```

- `private Game.UI.InGame.EmploymentData <educationDataEmployees>k__BackingField`  

```csharp
private Game.UI.InGame.EmploymentData <educationDataEmployees>k__BackingField;
```

- `private Game.UI.InGame.EmploymentData <educationDataWorkplaces>k__BackingField`  

```csharp
private Game.UI.InGame.EmploymentData <educationDataWorkplaces>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <districtBuildings>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <districtBuildings>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 employeeCount { private get; private set }`  

```csharp
private System.Int32 employeeCount { private get; private set; }
```

- `private System.Int32 maxEmployees { private get; private set }`  

```csharp
private System.Int32 maxEmployees { private get; private set; }
```

- `private Game.UI.InGame.EmploymentData educationDataEmployees { private get; private set }`  

```csharp
private Game.UI.InGame.EmploymentData educationDataEmployees { private get; private set; }
```

- `private Game.UI.InGame.EmploymentData educationDataWorkplaces { private get; private set }`  

```csharp
private Game.UI.InGame.EmploymentData educationDataWorkplaces { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> districtBuildings { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> districtBuildings { private get; private set; }
```


## Constructors

- `public EmployeesSection()`  

```csharp
[Preserve]
	public EmployeesSection()
	{
	}
```


## Methods

- `private AddEmployees() : System.Void`  

```csharp
private void AddEmployees(Entity entity)
	{
		Entity prefab = base.EntityManager.GetComponentData<PrefabRef>(entity).m_Prefab;
		Entity entity2 = GetEntity(entity);
		Entity prefab2 = base.EntityManager.GetComponentData<PrefabRef>(entity2).m_Prefab;
		int buildingLevel = 1;
		PropertyRenter component2;
		PrefabRef component3;
		SpawnableBuildingData component4;
		if (base.EntityManager.TryGetComponent<SpawnableBuildingData>(prefab, out var component))
		{
			buildingLevel = component.m_Level;
		}
		else if (base.EntityManager.TryGetComponent<PropertyRenter>(entity, out component2) && base.EntityManager.TryGetComponent<PrefabRef>(component2.m_Property, out component3) && base.EntityManager.TryGetComponent<SpawnableBuildingData>(component3.m_Prefab, out component4))
		{
			buildingLevel = component4.m_Level;
		}
		if (base.EntityManager.TryGetBuffer(entity2, isReadOnly: true, out DynamicBuffer<Employee> buffer) && base.EntityManager.TryGetComponent<WorkProvider>(entity2, out var component5))
		{
			employeeCount += buffer.Length;
			WorkplaceComplexity complexity = base.EntityManager.GetComponentData<WorkplaceData>(prefab2).m_Complexity;
			EmploymentData workplacesData = EmploymentData.GetWorkplacesData(component5.m_MaxWorkers, buildingLevel, complexity);
			maxEmployees += workplacesData.total;
			educationDataWorkplaces += workplacesData;
			educationDataEmployees += EmploymentData.GetEmployeesData(buffer, workplacesData.total - buffer.Length);
		}
	}
```

- `private AddEmployees(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void AddEmployees(Entity entity)
	{
		Entity prefab = base.EntityManager.GetComponentData<PrefabRef>(entity).m_Prefab;
		Entity entity2 = GetEntity(entity);
		Entity prefab2 = base.EntityManager.GetComponentData<PrefabRef>(entity2).m_Prefab;
		int buildingLevel = 1;
		PropertyRenter component2;
		PrefabRef component3;
		SpawnableBuildingData component4;
		if (base.EntityManager.TryGetComponent<SpawnableBuildingData>(prefab, out var component))
		{
			buildingLevel = component.m_Level;
		}
		else if (base.EntityManager.TryGetComponent<PropertyRenter>(entity, out component2) && base.EntityManager.TryGetComponent<PrefabRef>(component2.m_Property, out component3) && base.EntityManager.TryGetComponent<SpawnableBuildingData>(component3.m_Prefab, out component4))
		{
			buildingLevel = component4.m_Level;
		}
		if (base.EntityManager.TryGetBuffer(entity2, isReadOnly: true, out DynamicBuffer<Employee> buffer) && base.EntityManager.TryGetComponent<WorkProvider>(entity2, out var component5))
		{
			employeeCount += buffer.Length;
			WorkplaceComplexity complexity = base.EntityManager.GetComponentData<WorkplaceData>(prefab2).m_Complexity;
			EmploymentData workplacesData = EmploymentData.GetWorkplacesData(component5.m_MaxWorkers, buildingLevel, complexity);
			maxEmployees += workplacesData.total;
			educationDataWorkplaces += workplacesData;
			educationDataEmployees += EmploymentData.GetEmployeesData(buffer, workplacesData.total - buffer.Length);
		}
	}
```

- `private DisplayForDistrict() : System.Boolean`  

```csharp
private bool DisplayForDistrict()
	{
		NativeArray<Entity> nativeArray = m_DistrictBuildingQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<CurrentDistrict> nativeArray2 = m_DistrictBuildingQuery.ToComponentDataArray<CurrentDistrict>(Allocator.TempJob);
		NativeArray<PrefabRef> nativeArray3 = m_DistrictBuildingQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (!(nativeArray2[i].m_District != selectedEntity))
				{
					Entity entity = nativeArray[i];
					if (HasEmployees(entity, nativeArray3[i].m_Prefab))
					{
						return true;
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
			nativeArray2.Dispose();
			nativeArray3.Dispose();
		}
		return false;
	}
```

- `private GetEntity(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Entity GetEntity(Entity entity)
	{
		if (!base.EntityManager.HasComponent<Game.Buildings.Park>(entity) && base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<Renter> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity renter = buffer[i].m_Renter;
				if (base.EntityManager.HasComponent<CompanyData>(renter))
				{
					return renter;
				}
			}
		}
		return entity;
	}
```

- `private HasEmployees(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private bool HasEmployees(Entity entity, Entity prefab)
	{
		if (!base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<Renter> buffer) || base.EntityManager.HasComponent<Game.Buildings.Park>(entity))
		{
			if (base.EntityManager.HasComponent<Employee>(entity) && base.EntityManager.HasComponent<WorkProvider>(entity))
			{
				return base.Enabled;
			}
			return false;
		}
		if (buffer.Length == 0 && base.EntityManager.TryGetComponent<SpawnableBuildingData>(prefab, out var component))
		{
			m_PrefabSystem.TryGetPrefab<ZonePrefab>(component.m_ZonePrefab, out var prefab2);
			if (prefab2 != null)
			{
				if (prefab2.m_AreaType != Game.Zones.AreaType.Commercial)
				{
					return prefab2.m_AreaType == Game.Zones.AreaType.Industrial;
				}
				return true;
			}
			return false;
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity renter = buffer[i].m_Renter;
			if (base.EntityManager.HasComponent<CompanyData>(renter))
			{
				if (base.EntityManager.HasComponent<Employee>(renter))
				{
					return base.EntityManager.HasComponent<WorkProvider>(renter);
				}
				return false;
			}
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_DistrictBuildingQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<CurrentDistrict>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Renter>(),
				ComponentType.ReadOnly<Employee>()
			},
			None = new ComponentType[2]
			{
				ComponentType.Exclude<Temp>(),
				ComponentType.Exclude<Deleted>()
			}
		});
		districtBuildings = new NativeList<Entity>(Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		districtBuildings.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
		if (base.visible)
		{
			AddEmployees();
			base.visible = maxEmployees > 0;
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("employeeCount");
		writer.Write(employeeCount);
		writer.PropertyName("maxEmployees");
		writer.Write(maxEmployees);
		writer.PropertyName("educationDataEmployees");
		writer.Write(educationDataEmployees);
		writer.PropertyName("educationDataWorkplaces");
		writer.Write(educationDataWorkplaces);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		employeeCount = 0;
		maxEmployees = 0;
		educationDataEmployees = default(EmploymentData);
		educationDataWorkplaces = default(EmploymentData);
		districtBuildings.Clear();
	}
```

- `private UpdateForDistricts() : System.Void`  

```csharp
private void UpdateForDistricts()
	{
		NativeArray<Entity> nativeArray = m_DistrictBuildingQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<CurrentDistrict> nativeArray2 = m_DistrictBuildingQuery.ToComponentDataArray<CurrentDistrict>(Allocator.TempJob);
		NativeArray<PrefabRef> nativeArray3 = m_DistrictBuildingQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (!(nativeArray2[i].m_District != selectedEntity))
				{
					Entity entity = nativeArray[i];
					if (HasEmployees(entity, nativeArray3[i].m_Prefab))
					{
						AddEmployees(entity);
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
			nativeArray2.Dispose();
			nativeArray3.Dispose();
		}
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<District>(selectedEntity) && base.EntityManager.HasComponent<Area>(selectedEntity))
		{
			return DisplayForDistrict();
		}
		return HasEmployees(selectedEntity, selectedPrefab);
	}
```


