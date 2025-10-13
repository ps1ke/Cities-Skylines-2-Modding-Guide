# Game.UI.InGame.TaxationUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TaxationUISystem : Game.UI.UISystemBase
{
    private Game.Simulation.ITaxSystem m_TaxSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_ResourceQuery;
    private Unity.Entities.EntityQuery m_UnlockedZoneQuery;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxRate;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxIncome;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxEffect;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MinTaxRate;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxTaxRate;
    private Colossal.UI.Binding.RawValueBinding m_AreaTypes;
    private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxRates;
    private Colossal.UI.Binding.GetterMapBinding<System.Int32, Colossal.Mathematics.Bounds1> m_AreaResourceTaxRanges;
    private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxIncomes;
    private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxEffects;
    private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxRates;
    private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxIncomes;
    private Game.Prefabs.TaxParameterData m_CachedTaxParameterData;
    private System.Int32 m_CachedLockedOrderVersion;
    private System.Collections.Generic.Dictionary<System.Int32, System.String> m_ResourceIcons;
    private Game.UI.InGame.TaxationUISystem+TypeHandle __TypeHandle;
    private static readonly System.String kGroup;

    public TaxationUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Int32 GetEstimatedResourceTaxIncome(Game.Simulation.TaxAreaType type, System.Int32 resource);
    private System.String GetIcon(Game.Simulation.TaxAreaType type);
    private Unity.Mathematics.int2 GetLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits);
    private Unity.Mathematics.int2 GetResourceLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits);
    private System.Collections.Generic.IEnumerable<Game.Prefabs.ResourcePrefab> GetResources(System.Int32 areaType);
    private System.Int32 GetResourceTaxRate(Game.Simulation.TaxAreaType type, System.Int32 resource);
    private System.Boolean Locked(Game.Simulation.TaxAreaType areaType);
    private System.Boolean MatchArea(Game.Prefabs.TaxableResource data, System.Int32 areaType);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void SetAreaTaxRate(System.Int32 areaType, System.Int32 rate);
    private System.Void SetResourceTaxRate(System.Int32 resource, System.Int32 areaType, System.Int32 rate);
    private System.Void SetTaxRate(System.Int32 rate);
    private System.Void UpdateAreaResources(Colossal.UI.Binding.IJsonWriter binder, System.Int32 area);
    private Colossal.Mathematics.Bounds1 UpdateAreaResourceTaxRange(System.Int32 area);
    private System.Int32 UpdateAreaTaxEffect(System.Int32 areaType);
    private System.Int32 UpdateAreaTaxIncome(System.Int32 areaType);
    private System.Int32 UpdateAreaTaxRate(System.Int32 areaType);
    private System.Void UpdateAreaTypes(Colossal.UI.Binding.IJsonWriter binder);
    private System.Int32 UpdateMaxTaxRate();
    private System.Int32 UpdateMinTaxRate();
    private Game.UI.InGame.TaxResourceInfo UpdateResourceInfo(Game.UI.InGame.TaxResource resource);
    private System.Int32 UpdateResourceTaxIncome(Game.UI.InGame.TaxResource taxResource);
    private System.Int32 UpdateResourceTaxRate(Game.UI.InGame.TaxResource taxResource);
    private System.Int32 UpdateTaxEffect();
    private System.Int32 UpdateTaxIncome();
    private System.Int32 UpdateTaxRate();
}
```


## Fields

- `private Game.Simulation.ITaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.ITaxSystem m_TaxSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_ResourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResourceQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedZoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedZoneQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxIncome`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxIncome;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxEffect`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxEffect;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MinTaxRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MinTaxRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxTaxRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxTaxRate;
```

- `private Colossal.UI.Binding.RawValueBinding m_AreaTypes`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_AreaTypes;
```

- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxRates`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxRates;
```

- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, Colossal.Mathematics.Bounds1> m_AreaResourceTaxRanges`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<System.Int32, Colossal.Mathematics.Bounds1> m_AreaResourceTaxRanges;
```

- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxIncomes`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxIncomes;
```

- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxEffects`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxEffects;
```

- `private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxRates`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxRates;
```

- `private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxIncomes`  

```csharp
private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxIncomes;
```

- `private Game.Prefabs.TaxParameterData m_CachedTaxParameterData`  

```csharp
private Game.Prefabs.TaxParameterData m_CachedTaxParameterData;
```

- `private System.Int32 m_CachedLockedOrderVersion`  

```csharp
private System.Int32 m_CachedLockedOrderVersion;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.String> m_ResourceIcons`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.String> m_ResourceIcons;
```

- `private Game.UI.InGame.TaxationUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.TaxationUISystem+TypeHandle __TypeHandle;
```

- `private static readonly System.String kGroup`  

```csharp
private static readonly System.String kGroup;
```


## Constructors

- `public TaxationUISystem()`  

```csharp
[Preserve]
	public TaxationUISystem()
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

- `private GetEstimatedResourceTaxIncome(Game.Simulation.TaxAreaType type, System.Int32 resource) : System.Int32`  

```csharp
private int GetEstimatedResourceTaxIncome(TaxAreaType type, int resource)
	{
		NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> lookup = m_CityStatisticsSystem.GetLookup();
		BufferLookup<CityStatistic> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RO_BufferLookup, ref base.CheckedStateRef);
		return type switch
		{
			TaxAreaType.Residential => m_TaxSystem.GetEstimatedResidentialTaxIncome(resource, lookup, bufferLookup), 
			TaxAreaType.Commercial => m_TaxSystem.GetEstimatedCommercialTaxIncome(EconomyUtils.GetResource(resource), lookup, bufferLookup), 
			TaxAreaType.Industrial => m_TaxSystem.GetEstimatedIndustrialTaxIncome(EconomyUtils.GetResource(resource), lookup, bufferLookup), 
			TaxAreaType.Office => m_TaxSystem.GetEstimatedOfficeTaxIncome(EconomyUtils.GetResource(resource), lookup, bufferLookup), 
			_ => 0, 
		};
	}
```

- `private GetIcon(Game.Simulation.TaxAreaType type) : System.String`  

```csharp
private string GetIcon(TaxAreaType type)
	{
		return "Media/Game/Icons/Zone" + type.ToString() + ".svg";
	}
```

- `private GetLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits) : Unity.Mathematics.int2`  

```csharp
private int2 GetLimits(TaxAreaType type, TaxParameterData limits)
	{
		return type switch
		{
			TaxAreaType.Residential => limits.m_ResidentialTaxLimits, 
			TaxAreaType.Commercial => limits.m_CommercialTaxLimits, 
			TaxAreaType.Industrial => limits.m_IndustrialTaxLimits, 
			TaxAreaType.Office => limits.m_OfficeTaxLimits, 
			_ => default(int2), 
		};
	}
```

- `private GetResourceLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits) : Unity.Mathematics.int2`  

```csharp
private int2 GetResourceLimits(TaxAreaType type, TaxParameterData limits)
	{
		if (type == TaxAreaType.Residential)
		{
			return limits.m_JobLevelTaxLimits;
		}
		return limits.m_ResourceTaxLimits;
	}
```

- `private GetResources(System.Int32 areaType) : System.Collections.Generic.IEnumerable<Game.Prefabs.ResourcePrefab>`  

```csharp
private IEnumerable<ResourcePrefab> GetResources(int areaType)
	{
		NativeArray<Entity> entities = m_ResourceQuery.ToEntityArray(Allocator.TempJob);
		int i = 0;
		while (i < entities.Length)
		{
			ResourcePrefab prefab = m_PrefabSystem.GetPrefab<ResourcePrefab>(entities[i]);
			TaxableResource component = prefab.GetComponent<TaxableResource>();
			if (MatchArea(component, areaType))
			{
				yield return prefab;
			}
			int num = i + 1;
			i = num;
		}
		entities.Dispose();
	}
```

- `private GetResourceTaxRate(Game.Simulation.TaxAreaType type, System.Int32 resource) : System.Int32`  

```csharp
private int GetResourceTaxRate(TaxAreaType type, int resource)
	{
		return type switch
		{
			TaxAreaType.Residential => m_TaxSystem.GetResidentialTaxRate(resource), 
			TaxAreaType.Commercial => m_TaxSystem.GetCommercialTaxRate(EconomyUtils.GetResource(resource)), 
			TaxAreaType.Industrial => m_TaxSystem.GetIndustrialTaxRate(EconomyUtils.GetResource(resource)), 
			TaxAreaType.Office => m_TaxSystem.GetOfficeTaxRate(EconomyUtils.GetResource(resource)), 
			_ => 0, 
		};
	}
```

- `private Locked(Game.Simulation.TaxAreaType areaType) : System.Boolean`  

```csharp
private bool Locked(TaxAreaType areaType)
	{
		NativeArray<ZoneData> nativeArray = m_UnlockedZoneQuery.ToComponentDataArray<ZoneData>(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if ((areaType == TaxAreaType.Residential && nativeArray[i].m_AreaType == AreaType.Residential) || (areaType == TaxAreaType.Commercial && nativeArray[i].m_AreaType == AreaType.Commercial) || (areaType == TaxAreaType.Industrial && nativeArray[i].m_AreaType == AreaType.Industrial) || (areaType == TaxAreaType.Office && (nativeArray[i].m_ZoneFlags & ZoneFlags.Office) != 0))
			{
				nativeArray.Dispose();
				return false;
			}
		}
		nativeArray.Dispose();
		return true;
	}
```

- `private MatchArea(Game.Prefabs.TaxableResource data, System.Int32 areaType) : System.Boolean`  

```csharp
private bool MatchArea(TaxableResource data, int areaType)
	{
		if (data.m_TaxAreas == null || data.m_TaxAreas.Length == 0)
		{
			return true;
		}
		for (int i = 0; i < data.m_TaxAreas.Length; i++)
		{
			if ((int)data.m_TaxAreas[i] == areaType)
			{
				return true;
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
		m_ResourceQuery = GetEntityQuery(ComponentType.ReadOnly<ResourceData>(), ComponentType.ReadOnly<TaxableResourceData>());
		m_UnlockedZoneQuery = GetEntityQuery(ComponentType.ReadOnly<ZoneData>(), ComponentType.Exclude<Locked>());
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		AddBinding(m_TaxRate = new GetterValueBinding<int>(kGroup, "taxRate", UpdateTaxRate));
		AddBinding(m_TaxIncome = new GetterValueBinding<int>(kGroup, "taxIncome", UpdateTaxIncome));
		AddBinding(m_TaxEffect = new GetterValueBinding<int>(kGroup, "taxEffect", UpdateTaxEffect));
		AddBinding(m_MinTaxRate = new GetterValueBinding<int>(kGroup, "minTaxRate", UpdateMinTaxRate));
		AddBinding(m_MaxTaxRate = new GetterValueBinding<int>(kGroup, "maxTaxRate", UpdateMaxTaxRate));
		AddBinding(m_AreaTypes = new RawValueBinding(kGroup, "areaTypes", UpdateAreaTypes));
		AddBinding(m_AreaTaxRates = new GetterMapBinding<int, int>(kGroup, "areaTaxRates", UpdateAreaTaxRate));
		AddBinding(m_AreaResourceTaxRanges = new GetterMapBinding<int, Bounds1>(kGroup, "areaResourceTaxRanges", UpdateAreaResourceTaxRange));
		AddBinding(m_AreaTaxIncomes = new GetterMapBinding<int, int>(kGroup, "areaTaxIncomes", UpdateAreaTaxIncome));
		AddBinding(m_AreaTaxEffects = new GetterMapBinding<int, int>(kGroup, "areaTaxEffects", UpdateAreaTaxEffect));
		AddBinding(new RawMapBinding<int>(kGroup, "areaResources", UpdateAreaResources));
		AddBinding(m_ResourceTaxRates = new GetterMapBinding<TaxResource, int>(kGroup, "resourceTaxRates", UpdateResourceTaxRate, new ValueReader<TaxResource>(), new ValueWriter<TaxResource>()));
		AddBinding(m_ResourceTaxIncomes = new GetterMapBinding<TaxResource, int>(kGroup, "resourceTaxIncomes", UpdateResourceTaxIncome, new ValueReader<TaxResource>(), new ValueWriter<TaxResource>()));
		AddBinding(new GetterMapBinding<TaxResource, TaxResourceInfo>(kGroup, "taxResourceInfos", UpdateResourceInfo, new ValueReader<TaxResource>(), new ValueWriter<TaxResource>(), new ValueWriter<TaxResourceInfo>()));
		AddBinding(new TriggerBinding<int>(kGroup, "setTaxRate", SetTaxRate));
		AddBinding(new TriggerBinding<int, int>(kGroup, "setAreaTaxRate", SetAreaTaxRate));
		AddBinding(new TriggerBinding<int, int, int>(kGroup, "setResourceTaxRate", SetResourceTaxRate));
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_ResourceIcons.Clear();
		NativeArray<Entity> nativeArray = m_ResourceQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			ResourcePrefab prefab = m_PrefabSystem.GetPrefab<ResourcePrefab>(nativeArray[i]);
			UIObject component = prefab.GetComponent<UIObject>();
			m_ResourceIcons[(int)(prefab.m_Resource - 1)] = (component ? component.m_Icon : string.Empty);
		}
		nativeArray.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_AreaTaxIncomes.UpdateAll();
		m_AreaTaxEffects.UpdateAll();
		m_TaxIncome.Update();
		m_TaxEffect.Update();
		m_ResourceTaxIncomes.UpdateAll();
		TaxParameterData taxParameterData = m_TaxSystem.GetTaxParameterData();
		int componentOrderVersion = base.EntityManager.GetComponentOrderVersion<Locked>();
		bool flag = componentOrderVersion != m_CachedLockedOrderVersion;
		m_CachedLockedOrderVersion = componentOrderVersion;
		if (!m_CachedTaxParameterData.Equals(taxParameterData))
		{
			m_AreaTypes.Update();
			m_MinTaxRate.Update();
			m_MaxTaxRate.Update();
		}
		else if (flag)
		{
			m_AreaTypes.Update();
		}
	}
```

- `private SetAreaTaxRate(System.Int32 areaType, System.Int32 rate) : System.Void`  

```csharp
private void SetAreaTaxRate(int areaType, int rate)
	{
		m_TaxSystem.Readers.Complete();
		m_TaxSystem.SetTaxRate((TaxAreaType)areaType, rate);
		m_AreaTaxRates.Update(areaType);
		m_ResourceTaxRates.UpdateAll();
		m_AreaResourceTaxRanges.UpdateAll();
	}
```

- `private SetResourceTaxRate(System.Int32 resource, System.Int32 areaType, System.Int32 rate) : System.Void`  

```csharp
private void SetResourceTaxRate(int resource, int areaType, int rate)
	{
		m_TaxSystem.Readers.Complete();
		if ((byte)areaType == 1)
		{
			m_TaxSystem.SetResidentialTaxRate(resource, rate);
		}
		if ((byte)areaType == 2)
		{
			m_TaxSystem.SetCommercialTaxRate(EconomyUtils.GetResource(resource), rate);
		}
		else if ((byte)areaType == 3)
		{
			m_TaxSystem.SetIndustrialTaxRate(EconomyUtils.GetResource(resource), rate);
		}
		else if ((byte)areaType == 4)
		{
			m_TaxSystem.SetOfficeTaxRate(EconomyUtils.GetResource(resource), rate);
		}
		m_AreaTaxRates.Update(areaType);
		m_ResourceTaxRates.Update(new TaxResource
		{
			m_AreaType = areaType,
			m_Resource = resource
		});
		m_AreaResourceTaxRanges.UpdateAll();
	}
```

- `private SetTaxRate(System.Int32 rate) : System.Void`  

```csharp
private void SetTaxRate(int rate)
	{
		m_TaxSystem.Readers.Complete();
		m_TaxSystem.TaxRate = rate;
		m_TaxRate.Update();
		m_AreaTaxRates.UpdateAll();
		m_ResourceTaxRates.UpdateAll();
		m_AreaResourceTaxRanges.UpdateAll();
	}
```

- `private UpdateAreaResources(Colossal.UI.Binding.IJsonWriter binder, System.Int32 area) : System.Void`  

```csharp
private void UpdateAreaResources(IJsonWriter binder, int area)
	{
		if ((byte)area == 1)
		{
			binder.ArrayBegin(5u);
			for (int i = 0; i < 5; i++)
			{
				binder.Write(new TaxResource
				{
					m_Resource = i,
					m_AreaType = 1
				});
			}
			binder.ArrayEnd();
			return;
		}
		int num = 0;
		foreach (ResourcePrefab resource in GetResources(area))
		{
			_ = resource;
			num++;
		}
		binder.ArrayBegin(num);
		foreach (ResourcePrefab resource2 in GetResources(area))
		{
			binder.Write(new TaxResource
			{
				m_Resource = (int)(resource2.m_Resource - 1),
				m_AreaType = area
			});
		}
		binder.ArrayEnd();
	}
```

- `private UpdateAreaResourceTaxRange(System.Int32 area) : Colossal.Mathematics.Bounds1`  

```csharp
private Bounds1 UpdateAreaResourceTaxRange(int area)
	{
		return new Bounds1(m_TaxSystem.GetTaxRateRange((TaxAreaType)area));
	}
```

- `private UpdateAreaTaxEffect(System.Int32 areaType) : System.Int32`  

```csharp
private int UpdateAreaTaxEffect(int areaType)
	{
		return m_TaxSystem.GetTaxRateEffect((TaxAreaType)areaType, m_TaxSystem.GetTaxRate((TaxAreaType)areaType));
	}
```

- `private UpdateAreaTaxIncome(System.Int32 areaType) : System.Int32`  

```csharp
private int UpdateAreaTaxIncome(int areaType)
	{
		NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> lookup = m_CityStatisticsSystem.GetLookup();
		BufferLookup<CityStatistic> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RO_BufferLookup, ref base.CheckedStateRef);
		return m_TaxSystem.GetEstimatedTaxAmount((TaxAreaType)areaType, TaxResultType.Any, lookup, bufferLookup);
	}
```

- `private UpdateAreaTaxRate(System.Int32 areaType) : System.Int32`  

```csharp
private int UpdateAreaTaxRate(int areaType)
	{
		return m_TaxSystem.GetTaxRate((TaxAreaType)areaType);
	}
```

- `private UpdateAreaTypes(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateAreaTypes(IJsonWriter binder)
	{
		TaxParameterData limits = (m_CachedTaxParameterData = m_TaxSystem.GetTaxParameterData());
		binder.ArrayBegin(4u);
		TaxAreaType taxAreaType = TaxAreaType.Residential;
		while ((int)taxAreaType <= 4)
		{
			binder.TypeBegin("taxation.TaxAreaType");
			binder.PropertyName("index");
			binder.Write((int)taxAreaType);
			binder.PropertyName("id");
			binder.Write(taxAreaType.ToString());
			binder.PropertyName("icon");
			binder.Write(GetIcon(taxAreaType));
			int2 limits2 = GetLimits(taxAreaType, limits);
			binder.PropertyName("taxRateMin");
			binder.Write(limits2.x);
			binder.PropertyName("taxRateMax");
			binder.Write(limits2.y);
			int2 resourceLimits = GetResourceLimits(taxAreaType, limits);
			binder.PropertyName("resourceTaxRateMin");
			binder.Write(resourceLimits.x);
			binder.PropertyName("resourceTaxRateMax");
			binder.Write(resourceLimits.y);
			binder.PropertyName("locked");
			binder.Write(Locked(taxAreaType));
			binder.TypeEnd();
			taxAreaType++;
		}
		binder.ArrayEnd();
	}
```

- `private UpdateMaxTaxRate() : System.Int32`  

```csharp
private int UpdateMaxTaxRate()
	{
		return m_TaxSystem.GetTaxParameterData().m_TotalTaxLimits.y;
	}
```

- `private UpdateMinTaxRate() : System.Int32`  

```csharp
private int UpdateMinTaxRate()
	{
		return m_TaxSystem.GetTaxParameterData().m_TotalTaxLimits.x;
	}
```

- `private UpdateResourceInfo(Game.UI.InGame.TaxResource resource) : Game.UI.InGame.TaxResourceInfo`  

```csharp
private TaxResourceInfo UpdateResourceInfo(TaxResource resource)
	{
		if (resource.m_AreaType == 1)
		{
			return new TaxResourceInfo
			{
				m_ID = string.Empty,
				m_Icon = "Media/Game/Icons/ZoneResidential.svg"
			};
		}
		return new TaxResourceInfo
		{
			m_ID = EconomyUtils.GetResource(resource.m_Resource).ToString(),
			m_Icon = m_ResourceIcons[resource.m_Resource]
		};
	}
```

- `private UpdateResourceTaxIncome(Game.UI.InGame.TaxResource taxResource) : System.Int32`  

```csharp
private int UpdateResourceTaxIncome(TaxResource taxResource)
	{
		return GetEstimatedResourceTaxIncome((TaxAreaType)taxResource.m_AreaType, taxResource.m_Resource);
	}
```

- `private UpdateResourceTaxRate(Game.UI.InGame.TaxResource taxResource) : System.Int32`  

```csharp
private int UpdateResourceTaxRate(TaxResource taxResource)
	{
		return GetResourceTaxRate((TaxAreaType)taxResource.m_AreaType, taxResource.m_Resource);
	}
```

- `private UpdateTaxEffect() : System.Int32`  

```csharp
private int UpdateTaxEffect()
	{
		return m_TaxSystem.GetTaxRateEffect(TaxAreaType.Residential, m_TaxSystem.GetTaxRate(TaxAreaType.Residential)) + m_TaxSystem.GetTaxRateEffect(TaxAreaType.Commercial, m_TaxSystem.GetTaxRate(TaxAreaType.Commercial)) + m_TaxSystem.GetTaxRateEffect(TaxAreaType.Industrial, m_TaxSystem.GetTaxRate(TaxAreaType.Industrial)) + m_TaxSystem.GetTaxRateEffect(TaxAreaType.Office, m_TaxSystem.GetTaxRate(TaxAreaType.Office));
	}
```

- `private UpdateTaxIncome() : System.Int32`  

```csharp
private int UpdateTaxIncome()
	{
		NativeParallelHashMap<CityStatisticsSystem.StatisticsKey, Entity> lookup = m_CityStatisticsSystem.GetLookup();
		BufferLookup<CityStatistic> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RO_BufferLookup, ref base.CheckedStateRef);
		return m_TaxSystem.GetEstimatedTaxAmount(TaxAreaType.Residential, TaxResultType.Any, lookup, bufferLookup) + m_TaxSystem.GetEstimatedTaxAmount(TaxAreaType.Commercial, TaxResultType.Any, lookup, bufferLookup) + m_TaxSystem.GetEstimatedTaxAmount(TaxAreaType.Industrial, TaxResultType.Any, lookup, bufferLookup) + m_TaxSystem.GetEstimatedTaxAmount(TaxAreaType.Office, TaxResultType.Any, lookup, bufferLookup);
	}
```

- `private UpdateTaxRate() : System.Int32`  

```csharp
private int UpdateTaxRate()
	{
		return m_TaxSystem.TaxRate;
	}
```


## Nested types

- `Game.UI.InGame.TaxationUISystem+TypeHandle`  
- `Game.UI.InGame.TaxationUISystem+<GetResources>d__46`  

