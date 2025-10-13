# Game.Simulation.BudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IBudgetSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BudgetSystem : Game.GameSystemBase, Game.Simulation.IBudgetSystem
{
    private System.UInt32 m_LastUpdate;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    protected Unity.Collections.NativeArray<System.Int32> m_Trade;
    protected Unity.Collections.NativeArray<System.Int32> m_TradeWorth;
    protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWealth;
    protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWealth;
    protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWealth;
    protected System.Int32 m_TotalTradeWorth;
    protected System.Int32 m_TotalTaxIncome;
    private Unity.Collections.NativeArray<System.Int32> m_HouseholdCount;
    private Unity.Collections.NativeArray<System.Int32> m_ServiceCount;
    private Unity.Collections.NativeArray<System.Int32> m_ProcessingCount;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWorkers;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWorkers;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWorkers;
    private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_CitizenWellbeing;
    private Unity.Collections.NativeArray<System.Int32> m_TouristCount;
    private Unity.Collections.NativeArray<System.Int32> m_TouristIncome;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_LodgingData;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.BudgetSystem+TypeHandle __TypeHandle;

    public System.Boolean HasData { get; }
    public System.UInt32 LastUpdate { get; }

    public BudgetSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Unity.Mathematics.float2 GetCitizenWellbeing();
    public System.Int32 GetCompanyCount(System.Boolean service, Game.Economy.Resource resource);
    public System.Int32 GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource);
    public Unity.Mathematics.int2 GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource);
    public System.Int32 GetHouseholdCount();
    public System.Int32 GetHouseholdWealth();
    public Unity.Mathematics.int2 GetHouseholdWorkers();
    public Unity.Mathematics.int2 GetLodgingData();
    public System.Int32 GetTotalTradeWorth();
    public System.Int32 GetTouristCount();
    public System.Int32 GetTouristIncome();
    public System.Int32 GetTrade(Game.Economy.Resource resource);
    public System.Int32 GetTradeWorth(Game.Economy.Resource resource);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void SetTradeWorth(Game.Economy.Resource resource, Game.Prefabs.ResourceData resourceData);
    private System.Void UpdateData();
    private System.Void UpdateTotalTradeWorth();
}
```


## Fields

- `private System.UInt32 m_LastUpdate`  

```csharp
private System.UInt32 m_LastUpdate;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_Trade`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_Trade;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_TradeWorth`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_TradeWorth;
```

- `protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWealth`  

```csharp
protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWealth;
```

- `protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWealth`  

```csharp
protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWealth;
```

- `protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWealth`  

```csharp
protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWealth;
```

- `protected System.Int32 m_TotalTradeWorth`  

```csharp
protected System.Int32 m_TotalTradeWorth;
```

- `protected System.Int32 m_TotalTaxIncome`  

```csharp
protected System.Int32 m_TotalTaxIncome;
```

- `private Unity.Collections.NativeArray<System.Int32> m_HouseholdCount`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_HouseholdCount;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ServiceCount`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ServiceCount;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ProcessingCount`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ProcessingCount;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWorkers`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWorkers;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWorkers`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWorkers;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWorkers`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWorkers;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_CitizenWellbeing`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_CitizenWellbeing;
```

- `private Unity.Collections.NativeArray<System.Int32> m_TouristCount`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TouristCount;
```

- `private Unity.Collections.NativeArray<System.Int32> m_TouristIncome`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TouristIncome;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_LodgingData`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_LodgingData;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.BudgetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BudgetSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean HasData { get }`  

```csharp
public System.Boolean HasData { get; }
```

- `public System.UInt32 LastUpdate { get }`  

```csharp
public System.UInt32 LastUpdate { get; }
```


## Constructors

- `public BudgetSystem()`  

```csharp
[Preserve]
	public BudgetSystem()
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

- `public GetCitizenWellbeing() : Unity.Mathematics.float2`  

```csharp
public float2 GetCitizenWellbeing()
	{
		return m_CitizenWellbeing[0];
	}
```

- `public GetCompanyCount(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  

```csharp
public int GetCompanyCount(bool service, Resource resource)
	{
		int resourceIndex = EconomyUtils.GetResourceIndex(resource);
		if (!service)
		{
			return m_ProcessingCount[resourceIndex];
		}
		return m_ServiceCount[resourceIndex];
	}
```

- `public GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  

```csharp
public int GetCompanyWealth(bool service, Resource resource)
	{
		int resourceIndex = EconomyUtils.GetResourceIndex(resource);
		int2 @int = (service ? m_ServiceWealth[resourceIndex] : m_ProcessingWealth[resourceIndex]);
		if (@int.y > 0)
		{
			return @int.x / @int.y;
		}
		return 0;
	}
```

- `public GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource) : Unity.Mathematics.int2`  

```csharp
public int2 GetCompanyWorkers(bool service, Resource resource)
	{
		int resourceIndex = EconomyUtils.GetResourceIndex(resource);
		if (!service)
		{
			return m_ProcessingWorkers[resourceIndex];
		}
		return m_ServiceWorkers[resourceIndex];
	}
```

- `public GetHouseholdCount() : System.Int32`  

```csharp
public int GetHouseholdCount()
	{
		return m_HouseholdCount[0];
	}
```

- `public GetHouseholdWealth() : System.Int32`  

```csharp
public int GetHouseholdWealth()
	{
		if (m_HouseholdWealth[0].y > 0)
		{
			return m_HouseholdWealth[0].x / m_HouseholdWealth[0].y;
		}
		return 0;
	}
```

- `public GetHouseholdWorkers() : Unity.Mathematics.int2`  

```csharp
public int2 GetHouseholdWorkers()
	{
		return m_HouseholdWorkers[0];
	}
```

- `public GetLodgingData() : Unity.Mathematics.int2`  

```csharp
public int2 GetLodgingData()
	{
		return m_LodgingData[0];
	}
```

- `public GetTotalTradeWorth() : System.Int32`  

```csharp
public int GetTotalTradeWorth()
	{
		return m_TotalTradeWorth;
	}
```

- `public GetTouristCount() : System.Int32`  

```csharp
public int GetTouristCount()
	{
		return m_TouristCount[0];
	}
```

- `public GetTouristIncome() : System.Int32`  

```csharp
public int GetTouristIncome()
	{
		return m_TouristIncome[0];
	}
```

- `public GetTrade(Game.Economy.Resource resource) : System.Int32`  

```csharp
public int GetTrade(Resource resource)
	{
		int resourceIndex = EconomyUtils.GetResourceIndex(resource);
		return m_Trade[resourceIndex];
	}
```

- `public GetTradeWorth(Game.Economy.Resource resource) : System.Int32`  

```csharp
public int GetTradeWorth(Resource resource)
	{
		int resourceIndex = EconomyUtils.GetResourceIndex(resource);
		return m_TradeWorth[resourceIndex];
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 32768;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		int resourceCount = EconomyUtils.ResourceCount;
		m_Trade = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_TradeWorth = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_HouseholdWealth = new NativeArray<int2>(1, Allocator.Persistent);
		m_ServiceWealth = new NativeArray<int2>(resourceCount, Allocator.Persistent);
		m_ProcessingWealth = new NativeArray<int2>(resourceCount, Allocator.Persistent);
		m_CitizenWellbeing = new NativeArray<float2>(1, Allocator.Persistent);
		m_HouseholdCount = new NativeArray<int>(1, Allocator.Persistent);
		m_HouseholdWorkers = new NativeArray<int2>(1, Allocator.Persistent);
		m_ServiceCount = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_ServiceWorkers = new NativeArray<int2>(resourceCount, Allocator.Persistent);
		m_ProcessingCount = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_ProcessingWorkers = new NativeArray<int2>(resourceCount, Allocator.Persistent);
		m_TouristCount = new NativeArray<int>(1, Allocator.Persistent);
		m_TouristIncome = new NativeArray<int>(1, Allocator.Persistent);
		m_LodgingData = new NativeArray<int2>(1, Allocator.Persistent);
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
		m_Trade.Dispose();
		m_TradeWorth.Dispose();
		m_HouseholdWealth.Dispose();
		m_ServiceWealth.Dispose();
		m_ProcessingWealth.Dispose();
		m_CitizenWellbeing.Dispose();
		m_HouseholdCount.Dispose();
		m_HouseholdWorkers.Dispose();
		m_ServiceCount.Dispose();
		m_ServiceWorkers.Dispose();
		m_ProcessingCount.Dispose();
		m_ProcessingWorkers.Dispose();
		m_TouristCount.Dispose();
		m_TouristIncome.Dispose();
		m_LodgingData.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		UpdateData();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		UpdateData();
	}
```

- `private SetTradeWorth(Game.Economy.Resource resource, Game.Prefabs.ResourceData resourceData) : System.Void`  

```csharp
private void SetTradeWorth(Resource resource, ResourceData resourceData)
	{
		int resourceIndex = EconomyUtils.GetResourceIndex(resource);
		float marketPrice = EconomyUtils.GetMarketPrice(resourceData);
		m_TradeWorth[resourceIndex] = Mathf.RoundToInt(marketPrice * (float)m_Trade[resourceIndex]);
	}
```

- `private UpdateData() : System.Void`  

```csharp
private void UpdateData()
	{
		m_LastUpdate = m_SimulationSystem.frameIndex;
		InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RO_BufferLookup, ref base.CheckedStateRef);
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		ResourceIterator iterator = ResourceIterator.GetIterator();
		while (iterator.Next())
		{
			if (base.EntityManager.HasComponent<ResourceData>(prefabs[iterator.resource]) && base.EntityManager.GetComponentData<ResourceData>(prefabs[iterator.resource]).m_IsTradable)
			{
				m_Trade[EconomyUtils.GetResourceIndex(iterator.resource)] = m_CityStatisticsSystem.GetStatisticValue(StatisticType.Trade, EconomyUtils.GetResourceIndex(iterator.resource));
			}
		}
		iterator = ResourceIterator.GetIterator();
		while (iterator.Next())
		{
			if (base.EntityManager.HasComponent<ResourceData>(prefabs[iterator.resource]))
			{
				ResourceData componentData = base.EntityManager.GetComponentData<ResourceData>(prefabs[iterator.resource]);
				if (componentData.m_IsTradable)
				{
					SetTradeWorth(iterator.resource, componentData);
				}
			}
		}
		int statisticValue = m_CityStatisticsSystem.GetStatisticValue(StatisticType.HouseholdCount);
		m_HouseholdWealth[0] = new int2(m_CityStatisticsSystem.GetStatisticValue(StatisticType.HouseholdWealth), statisticValue);
		m_HouseholdCount[0] = statisticValue;
		int statisticValue2 = m_CityStatisticsSystem.GetStatisticValue(StatisticType.Population);
		if (statisticValue2 > 0)
		{
			m_CitizenWellbeing[0] = new float2((float)m_CityStatisticsSystem.GetStatisticValue(StatisticType.WellbeingLevel) / (float)statisticValue2, (float)m_CityStatisticsSystem.GetStatisticValue(StatisticType.HealthLevel) / (float)statisticValue2);
		}
		statisticValue = m_CityStatisticsSystem.GetStatisticValue(StatisticType.WorkerCount);
		m_HouseholdWorkers[0] = new int2(statisticValue, statisticValue + m_CityStatisticsSystem.GetStatisticValue(StatisticType.Unemployed));
		iterator = ResourceIterator.GetIterator();
		while (iterator.Next())
		{
			int resourceIndex = EconomyUtils.GetResourceIndex(iterator.resource);
			m_ServiceWealth[resourceIndex] = new int2(m_CityStatisticsSystem.GetStatisticValue(StatisticType.ServiceWealth, resourceIndex), m_CityStatisticsSystem.GetStatisticValue(StatisticType.ServiceCount, resourceIndex));
			m_ProcessingWealth[resourceIndex] = new int2(m_CityStatisticsSystem.GetStatisticValue(StatisticType.ProcessingWealth, resourceIndex), m_CityStatisticsSystem.GetStatisticValue(StatisticType.ProcessingCount, resourceIndex));
			m_ServiceCount[resourceIndex] = m_CityStatisticsSystem.GetStatisticValue(StatisticType.ServiceCount, resourceIndex);
			m_ServiceWorkers[resourceIndex] = new int2(m_CityStatisticsSystem.GetStatisticValue(StatisticType.ServiceWorkers, resourceIndex), m_CityStatisticsSystem.GetStatisticValue(StatisticType.ServiceMaxWorkers, resourceIndex));
			m_ProcessingCount[resourceIndex] = m_CityStatisticsSystem.GetStatisticValue(StatisticType.ProcessingCount, resourceIndex);
			m_ProcessingWorkers[resourceIndex] = new int2(m_CityStatisticsSystem.GetStatisticValue(StatisticType.ProcessingWorkers, resourceIndex), m_CityStatisticsSystem.GetStatisticValue(StatisticType.ProcessingMaxWorkers, resourceIndex));
		}
		m_TouristIncome[0] = m_CityStatisticsSystem.GetStatisticValue(StatisticType.TouristIncome);
		m_LodgingData[0] = new int2(m_CityStatisticsSystem.GetStatisticValue(StatisticType.LodgingUsed), m_CityStatisticsSystem.GetStatisticValue(StatisticType.LodgingTotal));
		UpdateTotalTradeWorth();
	}
```

- `private UpdateTotalTradeWorth() : System.Void`  

```csharp
private void UpdateTotalTradeWorth()
	{
		m_TotalTradeWorth = 0;
		for (int i = 0; i < m_TradeWorth.Length; i++)
		{
			m_TotalTradeWorth += m_TradeWorth[i];
		}
	}
```


## Nested types

- `Game.Simulation.BudgetSystem+TypeHandle`  

