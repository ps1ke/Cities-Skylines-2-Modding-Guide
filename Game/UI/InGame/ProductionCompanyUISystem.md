# Game.UI.InGame.ProductionCompanyUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProductionCompanyUISystem : Game.UI.UISystemBase
{
    private Game.Simulation.IBudgetSystem m_BudgetSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private System.Collections.Generic.Dictionary<System.String, Game.Economy.Resource> m_ResourceIDMap;
    private Colossal.UI.Binding.RawValueBinding m_ProductionCompanyInfoBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_IndustrialCompanyWealthBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CommercialCompanyWealthBinding;
    private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_CachedValues;
    private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_Values;
    private Game.Economy.Resource m_SelectedResource;
    private Unity.Collections.NativeQueue<Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo> m_ProductionCompanyInfoQueue;
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Game.UI.InGame.ProductionCompanyUISystem+TypeHandle __TypeHandle;
    private static readonly System.String kGroup;
    private static readonly System.Int32 kLevels;

    public ProductionCompanyUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnSelectResource(System.String resourceID);
    protected virtual System.Void OnUpdate();
    private System.Void Patch(System.Int32 index, System.String fieldName, System.Int32 value);
    private System.Void PatchProductionCompanyInfo();
    private System.Void RebuildResourceIDMap();
    private System.Void UpdateProductionCompanyInfo(Colossal.UI.Binding.IJsonWriter binder);
}
```


## Fields

- `private Game.Simulation.IBudgetSystem m_BudgetSystem`  

```csharp
private Game.Simulation.IBudgetSystem m_BudgetSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.Economy.Resource> m_ResourceIDMap`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.Economy.Resource> m_ResourceIDMap;
```

- `private Colossal.UI.Binding.RawValueBinding m_ProductionCompanyInfoBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ProductionCompanyInfoBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_IndustrialCompanyWealthBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_IndustrialCompanyWealthBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CommercialCompanyWealthBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CommercialCompanyWealthBinding;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_CachedValues`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_CachedValues;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_Values`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_Values;
```

- `private Game.Economy.Resource m_SelectedResource`  

```csharp
private Game.Economy.Resource m_SelectedResource;
```

- `private Unity.Collections.NativeQueue<Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo> m_ProductionCompanyInfoQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo> m_ProductionCompanyInfoQueue;
```

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Game.UI.InGame.ProductionCompanyUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.ProductionCompanyUISystem+TypeHandle __TypeHandle;
```

- `private static readonly System.String kGroup`  

```csharp
private static readonly System.String kGroup;
```

- `private static readonly System.Int32 kLevels`  

```csharp
private static readonly System.Int32 kLevels;
```


## Constructors

- `public ProductionCompanyUISystem()`  

```csharp
[Preserve]
	public ProductionCompanyUISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_BudgetSystem = base.World.GetOrCreateSystemManaged<BudgetSystem>();
		m_CompanyQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<PropertyRenter>(),
				ComponentType.ReadOnly<Employee>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<IndustrialCompany>(),
				ComponentType.ReadOnly<CommercialCompany>()
			}
		});
		m_SelectedResource = Resource.NoResource;
		m_ResourceIDMap = new Dictionary<string, Resource>();
		m_CachedValues = new NativeArray<ProductionLevelInfo>(kLevels, Allocator.Persistent);
		m_Values = new NativeArray<ProductionLevelInfo>(kLevels, Allocator.Persistent);
		m_ProductionCompanyInfoQueue = new NativeQueue<ProductionCompanyInfo>(Allocator.Persistent);
		AddBinding(m_ProductionCompanyInfoBinding = new RawValueBinding(kGroup, "productionCompanyInfo", UpdateProductionCompanyInfo));
		AddBinding(m_IndustrialCompanyWealthBinding = new ValueBinding<int>(kGroup, "industrialCompanyWealth", 0));
		AddBinding(m_CommercialCompanyWealthBinding = new ValueBinding<int>(kGroup, "commercialCompanyWealth", 0));
		AddBinding(new TriggerBinding<string>(kGroup, "selectResource", OnSelectResource));
		RebuildResourceIDMap();
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		m_CachedValues.Dispose();
		m_Values.Dispose();
		m_ProductionCompanyInfoQueue.Dispose();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		RebuildResourceIDMap();
		for (int i = 0; i < m_CachedValues.Length; i++)
		{
			m_CachedValues[i] = default(ProductionLevelInfo);
		}
		for (int j = 0; j < m_Values.Length; j++)
		{
			m_Values[j] = default(ProductionLevelInfo);
		}
		m_ProductionCompanyInfoQueue.Clear();
	}
```

- `private OnSelectResource(System.String resourceID) : System.Void`  

```csharp
private void OnSelectResource(string resourceID)
	{
		if (m_ResourceIDMap.TryGetValue(resourceID, out var value))
		{
			m_SelectedResource = value;
		}
		else
		{
			m_SelectedResource = Resource.NoResource;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ProductionCompanyInfoBinding.active)
		{
			PatchProductionCompanyInfo();
		}
		if (m_IndustrialCompanyWealthBinding.active)
		{
			m_IndustrialCompanyWealthBinding.Update((m_SelectedResource != Resource.NoResource) ? m_BudgetSystem.GetCompanyWealth(service: false, m_SelectedResource) : 0);
		}
		if (m_CommercialCompanyWealthBinding.active)
		{
			m_CommercialCompanyWealthBinding.Update((m_SelectedResource != Resource.NoResource) ? m_BudgetSystem.GetCompanyWealth(service: true, m_SelectedResource) : 0);
		}
	}
```

- `private Patch(System.Int32 index, System.String fieldName, System.Int32 value) : System.Void`  

```csharp
private void Patch(int index, string fieldName, int value)
	{
		IJsonWriter jsonWriter = m_ProductionCompanyInfoBinding.PatchBegin();
		jsonWriter.ArrayBegin(2u);
		jsonWriter.Write(index);
		jsonWriter.Write(fieldName);
		jsonWriter.ArrayEnd();
		jsonWriter.Write(value);
		m_ProductionCompanyInfoBinding.PatchEnd();
	}
```

- `private PatchProductionCompanyInfo() : System.Void`  

```csharp
private void PatchProductionCompanyInfo()
	{
		m_ProductionCompanyInfoQueue.Clear();
		for (int i = 0; i < m_Values.Length; i++)
		{
			m_Values[i] = default(ProductionLevelInfo);
		}
		if (m_SelectedResource != Resource.NoResource)
		{
			MapCompanyStatisticsJob jobData = new MapCompanyStatisticsJob
			{
				m_IndustrialCompanyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_IndustrialCompany_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PropertyRenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EmployeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_Employee_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Resource = m_SelectedResource,
				m_Queue = m_ProductionCompanyInfoQueue.AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CompanyQuery, base.Dependency);
			base.Dependency.Complete();
			ProductionCompanyInfo item;
			while (m_ProductionCompanyInfoQueue.TryDequeue(out item))
			{
				ProductionLevelInfo value = m_Values[item.m_Level - 1];
				if (item.m_Industrial)
				{
					value.m_IndustrialCompanies++;
					value.m_IndustrialWorkers += item.m_Workers;
				}
				else
				{
					value.m_CommercialCompanies++;
					value.m_CommercialWorkers += item.m_Workers;
				}
				m_Values[item.m_Level - 1] = value;
			}
		}
		for (int j = 0; j < m_CachedValues.Length; j++)
		{
			ProductionLevelInfo productionLevelInfo = m_CachedValues[j];
			ProductionLevelInfo value2 = m_Values[j];
			m_CachedValues[j] = value2;
			if (productionLevelInfo.m_IndustrialCompanies != value2.m_IndustrialCompanies)
			{
				Patch(j, "industrialCompanies", value2.m_IndustrialCompanies);
			}
			if (productionLevelInfo.m_IndustrialWorkers != value2.m_IndustrialWorkers)
			{
				Patch(j, "industrialWorkers", value2.m_IndustrialWorkers);
			}
			if (productionLevelInfo.m_CommercialCompanies != value2.m_CommercialCompanies)
			{
				Patch(j, "commercialCompanies", value2.m_CommercialCompanies);
			}
			if (productionLevelInfo.m_CommercialWorkers != value2.m_CommercialWorkers)
			{
				Patch(j, "commercialWorkers", value2.m_CommercialWorkers);
			}
		}
	}
```

- `private RebuildResourceIDMap() : System.Void`  

```csharp
private void RebuildResourceIDMap()
	{
		m_ResourceIDMap.Clear();
		ResourceIterator iterator = ResourceIterator.GetIterator();
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		while (iterator.Next())
		{
			Entity entity = prefabs[iterator.resource];
			if (entity != Entity.Null)
			{
				ResourcePrefab prefab = m_PrefabSystem.GetPrefab<ResourcePrefab>(entity);
				m_ResourceIDMap[prefab.name] = iterator.resource;
			}
		}
	}
```

- `private UpdateProductionCompanyInfo(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateProductionCompanyInfo(IJsonWriter binder)
	{
		binder.ArrayBegin(kLevels);
		for (int i = 0; i < kLevels; i++)
		{
			binder.TypeBegin("production.ProductionCompanyInfo");
			binder.PropertyName("industrialCompanies");
			binder.Write(0);
			binder.PropertyName("industrialWorkers");
			binder.Write(0);
			binder.PropertyName("commercialCompanies");
			binder.Write(0);
			binder.PropertyName("commercialWorkers");
			binder.Write(0);
			binder.TypeEnd();
		}
		binder.ArrayEnd();
	}
```


## Nested types

- `Game.UI.InGame.ProductionCompanyUISystem+MapCompanyStatisticsJob`  
- `Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo`  
- `Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo`  
- `Game.UI.InGame.ProductionCompanyUISystem+TypeHandle`  

