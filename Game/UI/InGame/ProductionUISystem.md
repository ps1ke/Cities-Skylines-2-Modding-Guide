# Game.UI.InGame.ProductionUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProductionUISystem : Game.UI.UISystemBase
{
    private Game.UI.UIUpdateState m_UpdateState;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Unity.Entities.EntityQuery m_ResourceCategoryQuery;
    private Unity.Entities.EntityQuery m_IndustrialCompanyQuery;
    private Unity.Entities.EntityQuery m_CommercialCompanyQuery;
    private Unity.Entities.EntityQuery m_ServiceUpkeepQuery;
    private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> m_ProductionChain;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxProgressBinding;
    private Colossal.UI.Binding.RawValueBinding m_ResourceCategoriesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceDetailsBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_DataBinding;
    private Unity.Collections.NativeList<System.Int32> m_ProductionCache;
    private Unity.Collections.NativeList<System.Int32> m_CommercialConsumptionCache;
    private Unity.Collections.NativeList<System.Int32> m_IndustrialConsumptionCache;
    private static const System.String kGroup;

    public ProductionUISystem();

    private System.Void BuildProductionChain(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap);
    private System.Void FindOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeKeyValueArrays<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> keyValueArrays);
    private System.Void FindServiceOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeArray<Unity.Entities.Entity> serviceUpkeeps);
    private System.ValueTuple<System.Int32, System.Int32, System.Int32> GetData(Unity.Entities.Entity entity);
    private System.Int32 GetMaxProgress();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void ProcessProductionChainDatas(Unity.Collections.NativeArray<Game.Prefabs.IndustrialProcessData> datas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap);
    private static System.Void TryAddUniqueValue(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap, Unity.Entities.Entity key, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity> value);
    private System.Void UpdateCache();
    private System.Void WriteData(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    private System.Void WriteProductionLink(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UIProductionLinkPrefab prefab);
    public System.Void WriteResource(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    private System.Void WriteResourceCategories(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteResourceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    private System.Void WriteService(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
}
```


## Fields

- `private Game.UI.UIUpdateState m_UpdateState`  

```csharp
private Game.UI.UIUpdateState m_UpdateState;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Unity.Entities.EntityQuery m_ResourceCategoryQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResourceCategoryQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialCompanyQuery;
```

- `private Unity.Entities.EntityQuery m_CommercialCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialCompanyQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceUpkeepQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceUpkeepQuery;
```

- `private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> m_ProductionChain`  

```csharp
private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> m_ProductionChain;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxProgressBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxProgressBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_ResourceCategoriesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResourceCategoriesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceDetailsBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ResourceBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_DataBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_DataBinding;
```

- `private Unity.Collections.NativeList<System.Int32> m_ProductionCache`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_ProductionCache;
```

- `private Unity.Collections.NativeList<System.Int32> m_CommercialConsumptionCache`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_CommercialConsumptionCache;
```

- `private Unity.Collections.NativeList<System.Int32> m_IndustrialConsumptionCache`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_IndustrialConsumptionCache;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public ProductionUISystem()`  

```csharp
[Preserve]
	public ProductionUISystem()
	{
	}
```


## Methods

- `private BuildProductionChain(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap) : System.Void`  

```csharp
private System.Void BuildProductionChain(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap);
```

- `private FindOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeKeyValueArrays<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> keyValueArrays) : System.Void`  

```csharp
private System.Void FindOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeKeyValueArrays<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> keyValueArrays);
```

- `private FindServiceOutputs(Unity.Entities.Entity entity, Unity.Collections.NativeList<Unity.Entities.Entity> outputs, Unity.Collections.NativeArray<Unity.Entities.Entity> serviceUpkeeps) : System.Void`  

```csharp
private void FindServiceOutputs(Entity entity, NativeList<Entity> outputs, NativeArray<Entity> serviceUpkeeps)
	{
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		for (int i = 0; i < serviceUpkeeps.Length; i++)
		{
			Entity entity2 = serviceUpkeeps[i];
			DynamicBuffer<ServiceUpkeepData> buffer = base.EntityManager.GetBuffer<ServiceUpkeepData>(entity2, isReadOnly: true);
			for (int j = 0; j < buffer.Length; j++)
			{
				Resource resource = buffer[j].m_Upkeep.m_Resource;
				if (resource == Resource.NoResource)
				{
					continue;
				}
				Entity entity3 = prefabs[resource];
				if (entity == entity3)
				{
					Entity value = base.EntityManager.GetComponentData<ServiceObjectData>(entity2).m_Service;
					if (!outputs.Contains(value))
					{
						outputs.Add(in value);
					}
				}
			}
		}
	}
```

- `private GetData(Unity.Entities.Entity entity) : System.ValueTuple<System.Int32, System.Int32, System.Int32>`  

```csharp
private System.ValueTuple<System.Int32, System.Int32, System.Int32> GetData(Unity.Entities.Entity entity);
```

- `private GetMaxProgress() : System.Int32`  

```csharp
private int GetMaxProgress()
	{
		int num = 0;
		ResourceIterator iterator = ResourceIterator.GetIterator();
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		while (iterator.Next())
		{
			Entity entity = prefabs[iterator.resource];
			ResourcePrefab prefab = m_PrefabSystem.GetPrefab<ResourcePrefab>(entity);
			if (prefab.m_IsLeisure || prefab.m_IsMaterial || prefab.m_IsProduceable)
			{
				(int, int, int) data = GetData(entity);
				int item = data.Item1;
				int item2 = data.Item2;
				int item3 = data.Item3;
				num = math.max(num, math.max(item, item2 + item3));
			}
		}
		return num;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdateState = UIUpdateState.Create(base.World, 256);
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_CommercialDemandSystem = base.World.GetOrCreateSystemManaged<CommercialDemandSystem>();
		m_IndustrialDemandSystem = base.World.GetOrCreateSystemManaged<IndustrialDemandSystem>();
		m_CountCompanyDataSystem = base.World.GetOrCreateSystemManaged<CountCompanyDataSystem>();
		m_ResourceCategoryQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<UIGroupElement>(), ComponentType.ReadOnly<UIResourceCategoryData>(), ComponentType.ReadOnly<UIObjectData>());
		m_IndustrialCompanyQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.Exclude<ServiceCompanyData>(), ComponentType.Exclude<StorageCompanyData>());
		m_CommercialCompanyQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.ReadOnly<ServiceCompanyData>(), ComponentType.Exclude<StorageCompanyData>());
		m_ServiceUpkeepQuery = GetEntityQuery(ComponentType.ReadWrite<ServiceUpkeepData>(), ComponentType.ReadOnly<ServiceObjectData>());
		AddBinding(m_MaxProgressBinding = new GetterValueBinding<int>("production", "maxProgress", GetMaxProgress));
		AddBinding(m_ResourceCategoriesBinding = new RawValueBinding("production", "resourceCategories", WriteResourceCategories));
		AddBinding(m_ResourceBinding = new RawMapBinding<Entity>("production", "resources", WriteResource));
		AddBinding(m_ResourceDetailsBinding = new RawMapBinding<Entity>("production", "resourceDetails", WriteResourceDetails));
		AddBinding(m_ServiceBinding = new RawMapBinding<Entity>("production", "services", WriteService));
		AddBinding(m_DataBinding = new RawMapBinding<Entity>("production", "data", WriteData));
		m_ProductionChain = new NativeParallelMultiHashMap<Entity, (Entity, Entity)>(50, Allocator.Persistent);
		m_ProductionCache = new NativeList<int>(Allocator.Persistent);
		m_CommercialConsumptionCache = new NativeList<int>(Allocator.Persistent);
		m_IndustrialConsumptionCache = new NativeList<int>(Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_ProductionChain.Dispose();
		m_ProductionCache.Dispose();
		m_CommercialConsumptionCache.Dispose();
		m_IndustrialConsumptionCache.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (GameManager.instance.gameMode == GameMode.Game)
		{
			BuildProductionChain(m_ProductionChain);
			UpdateCache();
			m_MaxProgressBinding.Update();
			m_ResourceCategoriesBinding.Update();
			m_ResourceBinding.Update();
			m_ResourceDetailsBinding.Update();
			m_ServiceBinding.Update();
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		if (GameManager.instance.gameMode == GameMode.Game && m_UpdateState.Advance())
		{
			UpdateCache();
			m_DataBinding.Update();
			m_MaxProgressBinding.Update();
		}
	}
```

- `private ProcessProductionChainDatas(Unity.Collections.NativeArray<Game.Prefabs.IndustrialProcessData> datas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap) : System.Void`  

```csharp
private System.Void ProcessProductionChainDatas(Unity.Collections.NativeArray<Game.Prefabs.IndustrialProcessData> datas, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap);
```

- `private static TryAddUniqueValue(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap, Unity.Entities.Entity key, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity> value) : System.Void`  

```csharp
private static System.Void TryAddUniqueValue(Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity>> multiHashMap, Unity.Entities.Entity key, System.ValueTuple<Unity.Entities.Entity, Unity.Entities.Entity> value);
```

- `private UpdateCache() : System.Void`  

```csharp
private void UpdateCache()
	{
		JobHandle deps;
		NativeArray<int> other = m_CountCompanyDataSystem.GetProduction(out deps);
		JobHandle deps2;
		CountCompanyDataSystem.CommercialCompanyDatas commercialCompanyDatas = m_CountCompanyDataSystem.GetCommercialCompanyDatas(out deps2);
		JobHandle deps3;
		NativeArray<int> other2 = m_IndustrialDemandSystem.GetConsumption(out deps3);
		JobHandle deps4;
		NativeArray<int> other3 = m_CommercialDemandSystem.GetConsumption(out deps4);
		JobHandle.CompleteAll(ref deps, ref deps3, ref deps4);
		deps2.Complete();
		m_ProductionCache.CopyFrom(in other);
		m_IndustrialConsumptionCache.CopyFrom(in other2);
		m_CommercialConsumptionCache.CopyFrom(in other3);
		for (int i = 0; i < m_ProductionCache.Length; i++)
		{
			ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
			if (!base.EntityManager.GetComponentData<ResourceData>(prefabs[EconomyUtils.GetResource(i)]).m_IsProduceable)
			{
				m_ProductionCache[i] = commercialCompanyDatas.m_ProduceCapacity[i];
			}
		}
	}
```

- `private WriteData(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void WriteData(IJsonWriter writer, Entity entity)
	{
		var (value, value2, value3) = GetData(entity);
		writer.TypeBegin("production.ResourceData");
		writer.PropertyName("production");
		writer.Write(value);
		writer.PropertyName("surplus");
		writer.Write(value2);
		writer.PropertyName("deficit");
		writer.Write(value3);
		writer.TypeEnd();
	}
```

- `private WriteProductionLink(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UIProductionLinkPrefab prefab) : System.Void`  

```csharp
private void WriteProductionLink(IJsonWriter writer, UIProductionLinkPrefab prefab)
	{
		writer.TypeBegin("ProductionLink");
		writer.PropertyName("name");
		writer.Write(prefab.m_Type.ToString());
		writer.PropertyName("icon");
		writer.Write(prefab.m_Icon);
		writer.TypeEnd();
	}
```

- `public WriteResource(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
public void WriteResource(IJsonWriter writer, Entity entity)
	{
		ResourcePrefab prefab = m_PrefabSystem.GetPrefab<ResourcePrefab>(entity);
		UIProductionLinks component = prefab.GetComponent<UIProductionLinks>();
		Resource resource = EconomyUtils.GetResource(prefab.m_Resource);
		try
		{
			writer.TypeBegin("production.Resource");
			writer.PropertyName("entity");
			writer.Write(entity);
			writer.PropertyName("name");
			writer.Write(resource.ToString());
			writer.PropertyName("icon");
			writer.Write(ImageSystem.GetIcon(prefab));
			writer.PropertyName("tradable");
			writer.Write(prefab.m_IsTradable);
			writer.PropertyName("producer");
			WriteProductionLink(writer, component.m_Producer);
			writer.PropertyName("consumers");
			if (component.m_FinalConsumers != null)
			{
				writer.ArrayBegin(component.m_FinalConsumers.Length);
				for (int i = 0; i < component.m_FinalConsumers.Length; i++)
				{
					WriteProductionLink(writer, component.m_FinalConsumers[i]);
				}
				writer.ArrayEnd();
			}
			else
			{
				writer.WriteEmptyArray();
			}
			writer.TypeEnd();
		}
		catch (Exception message)
		{
			writer.WriteNull();
			UnityEngine.Debug.LogError(message);
		}
	}
```

- `private WriteResourceCategories(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void WriteResourceCategories(IJsonWriter writer)
	{
		NativeList<UIObjectInfo> sortedObjects = UIObjectInfo.GetSortedObjects(m_ResourceCategoryQuery, Allocator.TempJob);
		try
		{
			writer.ArrayBegin(sortedObjects.Length);
			for (int i = 0; i < sortedObjects.Length; i++)
			{
				Entity entity = sortedObjects[i].entity;
				UIResourceCategoryPrefab prefab = m_PrefabSystem.GetPrefab<UIResourceCategoryPrefab>(sortedObjects[i].prefabData);
				NativeList<UIObjectInfo> objects = UIObjectInfo.GetObjects(base.EntityManager, base.EntityManager.GetBuffer<UIGroupElement>(entity, isReadOnly: true), Allocator.TempJob);
				objects.Sort();
				try
				{
					writer.TypeBegin("production.ResourceCategory");
					writer.PropertyName("entity");
					writer.Write(entity);
					writer.PropertyName("name");
					writer.Write(prefab.name);
					writer.PropertyName("resources");
					writer.ArrayBegin(objects.Length);
					for (int j = 0; j < objects.Length; j++)
					{
						WriteResource(writer, objects[j].entity);
					}
					writer.ArrayEnd();
					writer.TypeEnd();
				}
				finally
				{
					objects.Dispose();
				}
			}
			writer.ArrayEnd();
		}
		finally
		{
			sortedObjects.Dispose();
		}
	}
```

- `private WriteResourceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void WriteResourceDetails(IJsonWriter writer, Entity entity)
	{
		NativeList<Entity> outputs = new NativeList<Entity>(Allocator.TempJob);
		NativeList<Entity> outputs2 = new NativeList<Entity>(Allocator.TempJob);
		NativeKeyValueArrays<Entity, (Entity, Entity)> keyValueArrays = m_ProductionChain.GetKeyValueArrays(Allocator.TempJob);
		NativeArray<Entity> serviceUpkeeps = m_ServiceUpkeepQuery.ToEntityArray(Allocator.TempJob);
		try
		{
			writer.TypeBegin("production.ResourceDetails");
			writer.PropertyName("inputs");
			writer.ArrayBegin(m_ProductionChain.CountValuesForKey(entity));
			foreach (var item in m_ProductionChain.GetValuesForKey(entity))
			{
				int num = 0;
				if (item.Item1 != Entity.Null)
				{
					num++;
				}
				if (item.Item2 != Entity.Null)
				{
					num++;
				}
				writer.ArrayBegin(num);
				if (item.Item1 != Entity.Null)
				{
					writer.Write(item.Item1);
				}
				if (item.Item2 != Entity.Null)
				{
					writer.Write(item.Item2);
				}
				writer.ArrayEnd();
			}
			writer.ArrayEnd();
			FindOutputs(entity, outputs, keyValueArrays);
			writer.PropertyName("outputs");
			writer.ArrayBegin(outputs.Length);
			for (int i = 0; i < outputs.Length; i++)
			{
				writer.Write(outputs[i]);
			}
			writer.ArrayEnd();
			FindServiceOutputs(entity, outputs2, serviceUpkeeps);
			writer.PropertyName("serviceOutputs");
			writer.ArrayBegin(outputs2.Length);
			for (int j = 0; j < outputs2.Length; j++)
			{
				writer.Write(outputs2[j]);
			}
			writer.ArrayEnd();
			writer.TypeEnd();
		}
		finally
		{
			keyValueArrays.Dispose();
			outputs.Dispose();
			outputs2.Dispose();
			serviceUpkeeps.Dispose();
		}
	}
```

- `private WriteService(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void WriteService(IJsonWriter writer, Entity entity)
	{
		if (base.EntityManager.TryGetComponent<PrefabData>(entity, out var component))
		{
			ServicePrefab prefab = m_PrefabSystem.GetPrefab<ServicePrefab>(component);
			writer.TypeBegin("production.Service");
			writer.PropertyName("entity");
			writer.Write(entity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("icon");
			writer.Write(ImageSystem.GetIcon(prefab));
			writer.TypeEnd();
		}
		else
		{
			writer.WriteNull();
		}
	}
```


