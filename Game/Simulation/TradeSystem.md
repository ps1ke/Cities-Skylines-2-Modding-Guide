# Game.Simulation.TradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ITradeSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TradeSystem : Game.GameSystemBase, Game.Simulation.ITradeSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_StorageGroup;
    private Unity.Entities.EntityQuery m_TradeParameterQuery;
    private Unity.Entities.EntityQuery m_CityQuery;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Jobs.JobHandle m_DebugTradeBalanceDeps;
    private Unity.Collections.NativeArray<System.Int32> m_TradeBalances;
    private Unity.Collections.NativeArray<System.Single> m_CachedCosts;
    private Game.Simulation.TradeSystem+TypeHandle __TypeHandle;
    private static readonly System.Single kRefreshRate;
    public static readonly System.Int32 kUpdatesPerDay;

    public TradeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static Game.Companies.TradeCost CalculateTradeCost(Game.Economy.Resource resource, System.Int32 tradeBalance, Game.Prefabs.OutsideConnectionTransferType type, System.Single weight, Game.Prefabs.OutsideTradeParameterData& tradeParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
    public System.Void Deserialize<TReader>(TReader reader);
    private static System.Int32 GetCacheIndex(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import);
    public System.Single GetTradePrice(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context context);
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults();
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_StorageGroup`  

```csharp
private Unity.Entities.EntityQuery m_StorageGroup;
```

- `private Unity.Entities.EntityQuery m_TradeParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_TradeParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CityQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityQuery;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Jobs.JobHandle m_DebugTradeBalanceDeps`  

```csharp
private Unity.Jobs.JobHandle m_DebugTradeBalanceDeps;
```

- `private Unity.Collections.NativeArray<System.Int32> m_TradeBalances`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TradeBalances;
```

- `private Unity.Collections.NativeArray<System.Single> m_CachedCosts`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_CachedCosts;
```

- `private Game.Simulation.TradeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TradeSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single kRefreshRate`  

```csharp
private static readonly System.Single kRefreshRate;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public TradeSystem()`  

```csharp
[Preserve]
	public TradeSystem()
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

- `private static CalculateTradeCost(Game.Economy.Resource resource, System.Int32 tradeBalance, Game.Prefabs.OutsideConnectionTransferType type, System.Single weight, Game.Prefabs.OutsideTradeParameterData& tradeParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : Game.Companies.TradeCost`  

```csharp
private static TradeCost CalculateTradeCost(Resource resource, int tradeBalance, OutsideConnectionTransferType type, float weight, ref OutsideTradeParameterData tradeParameters, DynamicBuffer<CityModifier> cityEffects)
	{
		float value = tradeParameters.GetWeightCost(type) * weight;
		if ((float)tradeBalance < 0f)
		{
			value *= 1f + tradeParameters.GetDistanceCost(type) * math.max(50f, math.sqrt(-tradeBalance));
		}
		CityUtils.ApplyModifier(ref value, cityEffects, CityModifierType.ImportCost);
		float value2 = tradeParameters.GetWeightCost(type) * weight;
		if ((float)tradeBalance > 0f)
		{
			value2 *= 1f + tradeParameters.GetDistanceCost(type) * math.max(50f, math.sqrt(tradeBalance));
		}
		CityUtils.ApplyModifier(ref value2, cityEffects, CityModifierType.ExportCost);
		return new TradeCost
		{
			m_Resource = resource,
			m_BuyCost = value,
			m_SellCost = value2
		};
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private static GetCacheIndex(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import) : System.Int32`  

```csharp
private static int GetCacheIndex(Resource resource, OutsideConnectionTransferType type, bool import)
	{
		return Mathf.RoundToInt(math.log2((float)type) * 2f * (float)EconomyUtils.ResourceCount + (float)(2 * EconomyUtils.GetResourceIndex(resource)) + (float)(import ? 1 : 0));
	}
```

- `public GetTradePrice(Game.Economy.Resource resource, Game.Prefabs.OutsideConnectionTransferType type, System.Boolean import, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Single`  

```csharp
public float GetTradePrice(Resource resource, OutsideConnectionTransferType type, bool import, DynamicBuffer<CityModifier> cityEffects)
	{
		OutsideConnectionTransferType outsideConnectionTransferType = OutsideConnectionTransferType.Road;
		float value = float.MaxValue;
		while (outsideConnectionTransferType != OutsideConnectionTransferType.Last)
		{
			if ((outsideConnectionTransferType & type) != OutsideConnectionTransferType.None)
			{
				value = math.min(value, m_CachedCosts[GetCacheIndex(resource, type, import)]);
			}
			outsideConnectionTransferType = (OutsideConnectionTransferType)((int)outsideConnectionTransferType << 1);
		}
		if (import)
		{
			CityUtils.ApplyModifier(ref value, cityEffects, CityModifierType.ImportCost);
		}
		else
		{
			CityUtils.ApplyModifier(ref value, cityEffects, CityModifierType.ExportCost);
		}
		return value;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / kUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_TradeBalances = new NativeArray<int>(EconomyUtils.ResourceCount, Allocator.Persistent);
		m_CachedCosts = new NativeArray<float>(2 * EconomyUtils.ResourceCount * Mathf.RoundToInt(math.log2(32f)), Allocator.Persistent);
		m_StorageGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Game.Economy.Resources>(), ComponentType.ReadOnly<TradeCost>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_TradeParameterQuery = GetEntityQuery(ComponentType.ReadOnly<OutsideTradeParameterData>());
		m_CityQuery = GetEntityQuery(ComponentType.ReadOnly<Game.City.City>());
		RequireForUpdate(m_StorageGroup);
		RequireForUpdate(m_TradeParameterQuery);
		RequireForUpdate(m_CityQuery);
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
		m_CachedCosts.Dispose();
		m_TradeBalances.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
protected override void OnGameLoaded(Context context)
	{
		if (context.purpose != Purpose.NewGame)
		{
			return;
		}
		NativeArray<Entity> nativeArray = m_StorageGroup.ToEntityArray(Allocator.Temp);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			if (!base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component) || !base.EntityManager.TryGetBuffer(entity, isReadOnly: false, out DynamicBuffer<Game.Economy.Resources> buffer) || !base.EntityManager.TryGetComponent<StorageCompanyData>(component, out var component2) || !base.EntityManager.TryGetComponent<StorageLimitData>(component, out var component3))
			{
				continue;
			}
			ResourceIterator iterator = ResourceIterator.GetIterator();
			int num = EconomyUtils.CountResources(component2.m_StoredResources);
			while (iterator.Next())
			{
				if ((component2.m_StoredResources & iterator.resource) != Resource.NoResource)
				{
					if (iterator.resource == Resource.OutgoingMail)
					{
						EconomyUtils.SetResources(Resource.OutgoingMail, buffer, 0);
						continue;
					}
					int resources = EconomyUtils.GetResources(iterator.resource, buffer);
					int amount = component3.m_Limit / num / 2 - resources;
					EconomyUtils.AddResources(iterator.resource, amount, buffer);
				}
			}
		}
		nativeArray.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle deps;
		JobHandle jobHandle = IJobExtensions.Schedule(new TradeJob
		{
			m_Chunks = m_StorageGroup.ToArchetypeChunkArray(Allocator.TempJob),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TradeCostType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_TradeCost_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_Limits = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageFacilityDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GarbageFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityEffects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_City = m_CityQuery.GetSingletonEntity(),
			m_TradeBalances = m_TradeBalances,
			m_CachedCosts = m_CachedCosts,
			m_TradeParameters = m_TradeParameterQuery.GetSingleton<OutsideTradeParameterData>(),
			m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps).AsParallelWriter()
		}, JobHandle.CombineDependencies(base.Dependency, deps));
		m_CityStatisticsSystem.AddWriter(jobHandle);
		m_ResourceSystem.AddPrefabsReader(jobHandle);
		m_DebugTradeBalanceDeps = jobHandle;
		base.Dependency = jobHandle;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults() : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		SetDefaults();
	}
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		SetDefaults();
	}
```


## Nested types

- `Game.Simulation.TradeSystem+TradeJob`  
- `Game.Simulation.TradeSystem+TypeHandle`  

