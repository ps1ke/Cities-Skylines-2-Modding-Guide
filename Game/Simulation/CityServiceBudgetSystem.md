# Game.Simulation.CityServiceBudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ICityServiceBudgetSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityServiceBudgetSystem : Game.GameSystemBase, Game.Simulation.ICityServiceBudgetSystem
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GameModeGovernmentSubsidiesSystem;
    private Unity.Entities.EntityQuery m_BudgetDataQuery;
    private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
    private Unity.Entities.EntityQuery m_ServiceQuery;
    private Unity.Entities.EntityQuery m_UpkeepGroup;
    private Unity.Entities.EntityQuery m_ServiceObjectQuery;
    private Unity.Entities.EntityQuery m_NetUpkeepQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_OutsideTradeParameterQuery;
    private Unity.Entities.EntityQuery m_HealthcareFacilityQuery;
    private Unity.Entities.EntityQuery m_DeathcareFacilityQuery;
    private Unity.Entities.EntityQuery m_GarbageFacilityQuery;
    private Unity.Entities.EntityQuery m_FireStationQuery;
    private Unity.Entities.EntityQuery m_PoliceStationQuery;
    protected Unity.Collections.NativeArray<System.Int32> m_Income;
    protected Unity.Collections.NativeArray<System.Int32> m_IncomeTemp;
    protected Unity.Collections.NativeArray<System.Int32> m_TotalIncome;
    protected Unity.Collections.NativeArray<System.Int32> m_Expenses;
    protected Unity.Collections.NativeArray<System.Int32> m_ExpensesTemp;
    private System.Int32 m_TotalTaxIncome;
    private Unity.Collections.NativeReference<System.Int32> m_TotalTaxes;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> m_CityServiceBudgets;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> m_CityServiceUpkeepIndices;
    private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> m_CityServiceUpkeeps;
    private Unity.Jobs.JobHandle m_TempArrayDeps;
    private Game.Simulation.CityServiceBudgetSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_844909884_0;

    public CityServiceBudgetSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddArrayReader(Unity.Jobs.JobHandle deps);
    public System.Int32 GetBalance();
    public static System.Int32 GetBalance(Unity.Collections.NativeArray<System.Int32> income, Unity.Collections.NativeArray<System.Int32> expenses);
    public System.Void GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep);
    public static System.Void GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> upkeepIndices, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas);
    private static System.Int32 GetEstimatedServiceUpkeep(Game.Simulation.CollectedCityServiceBudgetData data, Unity.Mathematics.int2 indices, System.Int32 budget, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps);
    public System.Int32 GetExpense(Game.City.ExpenseSource source);
    public static System.Int32 GetExpense(Game.City.ExpenseSource source, Unity.Collections.NativeArray<System.Int32> expenses);
    public Unity.Collections.NativeArray<System.Int32> GetExpenseArray(Unity.Jobs.JobHandle& deps);
    public System.Int32 GetIncome(Game.City.IncomeSource source);
    public static System.Int32 GetIncome(Game.City.IncomeSource source, Unity.Collections.NativeArray<System.Int32> income);
    public Unity.Collections.NativeArray<System.Int32> GetIncomeArray(Unity.Jobs.JobHandle& deps);
    public System.Int32 GetMoneyDelta();
    public System.Int32 GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab);
    public System.Int32 GetServiceBudget(Unity.Entities.Entity servicePrefab);
    public static System.Int32 GetServiceBudget(Unity.Entities.Entity servicePrefab, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas);
    public Unity.Entities.Entity[] GetServiceBuildings(Unity.Entities.Entity servicePrefab);
    public System.Int32 GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget);
    public System.Int32 GetTotalExpenses();
    public static System.Int32 GetTotalExpenses(Unity.Collections.NativeArray<System.Int32> expenses);
    public System.Int32 GetTotalIncome();
    public static System.Int32 GetTotalIncome(Unity.Collections.NativeArray<System.Int32> income);
    public System.Int32 GetTotalIncome(Game.City.IncomeSource source);
    public System.Int32 GetTotalTaxIncome();
    private static System.Int32 GetTotalTaxIncome(Unity.Collections.NativeArray<System.Int32> income);
    public Unity.Mathematics.int2 GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage);
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  

```csharp
private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GameModeGovernmentSubsidiesSystem`  

```csharp
private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GameModeGovernmentSubsidiesSystem;
```

- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_BudgetDataQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceQuery;
```

- `private Unity.Entities.EntityQuery m_UpkeepGroup`  

```csharp
private Unity.Entities.EntityQuery m_UpkeepGroup;
```

- `private Unity.Entities.EntityQuery m_ServiceObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceObjectQuery;
```

- `private Unity.Entities.EntityQuery m_NetUpkeepQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetUpkeepQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideTradeParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideTradeParameterQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_DeathcareFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeathcareFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_FireStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireStationQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceStationQuery;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_Income`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_Income;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_IncomeTemp`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_IncomeTemp;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_TotalIncome`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_TotalIncome;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_Expenses`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_Expenses;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_ExpensesTemp`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_ExpensesTemp;
```

- `private System.Int32 m_TotalTaxIncome`  

```csharp
private System.Int32 m_TotalTaxIncome;
```

- `private Unity.Collections.NativeReference<System.Int32> m_TotalTaxes`  

```csharp
private Unity.Collections.NativeReference<System.Int32> m_TotalTaxes;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> m_CityServiceBudgets`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> m_CityServiceBudgets;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> m_CityServiceUpkeepIndices`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> m_CityServiceUpkeepIndices;
```

- `private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> m_CityServiceUpkeeps`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> m_CityServiceUpkeeps;
```

- `private Unity.Jobs.JobHandle m_TempArrayDeps`  

```csharp
private Unity.Jobs.JobHandle m_TempArrayDeps;
```

- `private Game.Simulation.CityServiceBudgetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CityServiceBudgetSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_844909884_0`  

```csharp
private Unity.Entities.EntityQuery __query_844909884_0;
```


## Constructors

- `public CityServiceBudgetSystem()`  

```csharp
[Preserve]
	public CityServiceBudgetSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<BuildingEfficiencyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_844909884_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public AddArrayReader(Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
public void AddArrayReader(JobHandle deps)
	{
		m_TempArrayDeps = JobHandle.CombineDependencies(m_TempArrayDeps, deps);
	}
```

- `public GetBalance() : System.Int32`  

```csharp
public static int GetBalance(NativeArray<int> income, NativeArray<int> expenses)
	{
		return GetTotalIncome(income) + GetTotalExpenses(expenses);
	}
```

- `public static GetBalance(Unity.Collections.NativeArray<System.Int32> income, Unity.Collections.NativeArray<System.Int32> expenses) : System.Int32`  

```csharp
public static int GetBalance(NativeArray<int> income, NativeArray<int> expenses)
	{
		return GetTotalIncome(income) + GetTotalExpenses(expenses);
	}
```

- `public GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep) : System.Void`  

```csharp
public static void GetEstimatedServiceBudget(Entity servicePrefab, out int upkeep, NativeParallelHashMap<Entity, CollectedCityServiceBudgetData> budgets, NativeList<CollectedCityServiceUpkeepData> upkeeps, NativeParallelHashMap<Entity, int2> upkeepIndices, Entity budgetEntity, BufferLookup<ServiceBudgetData> budgetDatas)
	{
		if (!budgets.ContainsKey(servicePrefab))
		{
			upkeep = 0;
			return;
		}
		int serviceBudget = GetServiceBudget(servicePrefab, budgets, budgetEntity, budgetDatas);
		CollectedCityServiceBudgetData data = budgets[servicePrefab];
		int2 indices = upkeepIndices[servicePrefab];
		upkeep = GetEstimatedServiceUpkeep(data, indices, serviceBudget, upkeeps);
	}
```

- `public static GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> upkeepIndices, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas) : System.Void`  

```csharp
public static void GetEstimatedServiceBudget(Entity servicePrefab, out int upkeep, NativeParallelHashMap<Entity, CollectedCityServiceBudgetData> budgets, NativeList<CollectedCityServiceUpkeepData> upkeeps, NativeParallelHashMap<Entity, int2> upkeepIndices, Entity budgetEntity, BufferLookup<ServiceBudgetData> budgetDatas)
	{
		if (!budgets.ContainsKey(servicePrefab))
		{
			upkeep = 0;
			return;
		}
		int serviceBudget = GetServiceBudget(servicePrefab, budgets, budgetEntity, budgetDatas);
		CollectedCityServiceBudgetData data = budgets[servicePrefab];
		int2 indices = upkeepIndices[servicePrefab];
		upkeep = GetEstimatedServiceUpkeep(data, indices, serviceBudget, upkeeps);
	}
```

- `private static GetEstimatedServiceUpkeep(Game.Simulation.CollectedCityServiceBudgetData data, Unity.Mathematics.int2 indices, System.Int32 budget, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps) : System.Int32`  

```csharp
private static int GetEstimatedServiceUpkeep(CollectedCityServiceBudgetData data, int2 indices, int budget, NativeList<CollectedCityServiceUpkeepData> upkeeps)
	{
		int num = data.m_BaseCost;
		for (int i = indices.x; i < indices.x + indices.y; i++)
		{
			CollectedCityServiceUpkeepData collectedCityServiceUpkeepData = upkeeps[i];
			int num2 = Mathf.RoundToInt(collectedCityServiceUpkeepData.m_FullCost);
			if (collectedCityServiceUpkeepData.m_Resource == Resource.Money)
			{
				num2 = Mathf.RoundToInt((float)num2 * ((float)budget / 100f));
			}
			num += num2;
		}
		return num;
	}
```

- `public GetExpense(Game.City.ExpenseSource source) : System.Int32`  

```csharp
public static int GetExpense(ExpenseSource source, NativeArray<int> expenses)
	{
		if ((int)source < expenses.Length)
		{
			return expenses[(int)source];
		}
		return 0;
	}
```

- `public static GetExpense(Game.City.ExpenseSource source, Unity.Collections.NativeArray<System.Int32> expenses) : System.Int32`  

```csharp
public static int GetExpense(ExpenseSource source, NativeArray<int> expenses)
	{
		if ((int)source < expenses.Length)
		{
			return expenses[(int)source];
		}
		return 0;
	}
```

- `public GetExpenseArray(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetExpenseArray(out JobHandle deps)
	{
		deps = m_TempArrayDeps;
		return m_ExpensesTemp;
	}
```

- `public GetIncome(Game.City.IncomeSource source) : System.Int32`  

```csharp
public static int GetIncome(IncomeSource source, NativeArray<int> income)
	{
		if ((int)source < income.Length)
		{
			return income[(int)source];
		}
		return 0;
	}
```

- `public static GetIncome(Game.City.IncomeSource source, Unity.Collections.NativeArray<System.Int32> income) : System.Int32`  

```csharp
public static int GetIncome(IncomeSource source, NativeArray<int> income)
	{
		if ((int)source < income.Length)
		{
			return income[(int)source];
		}
		return 0;
	}
```

- `public GetIncomeArray(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetIncomeArray(out JobHandle deps)
	{
		deps = m_TempArrayDeps;
		return m_IncomeTemp;
	}
```

- `public GetMoneyDelta() : System.Int32`  

```csharp
public int GetMoneyDelta()
	{
		int num = 0;
		for (int i = 0; i < 15; i++)
		{
			num -= GetExpense((ExpenseSource)i);
		}
		for (int j = 0; j < 14; j++)
		{
			num += GetIncome((IncomeSource)j);
		}
		return num / 24;
	}
```

- `public GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab) : System.Int32`  

```csharp
public int GetNumberOfServiceBuildings(Entity serviceBuildingPrefab)
	{
		if (base.EntityManager.HasComponent<CollectedServiceBuildingBudgetData>(serviceBuildingPrefab))
		{
			return base.EntityManager.GetComponentData<CollectedServiceBuildingBudgetData>(serviceBuildingPrefab).m_Count;
		}
		return 0;
	}
```

- `public GetServiceBudget(Unity.Entities.Entity servicePrefab) : System.Int32`  

```csharp
public static int GetServiceBudget(Entity servicePrefab, NativeParallelHashMap<Entity, CollectedCityServiceBudgetData> budgets, Entity budgetEntity, BufferLookup<ServiceBudgetData> budgetDatas)
	{
		if (!budgets.ContainsKey(servicePrefab))
		{
			return 0;
		}
		DynamicBuffer<ServiceBudgetData> dynamicBuffer = budgetDatas[budgetEntity];
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			ServiceBudgetData serviceBudgetData = dynamicBuffer[i];
			if (serviceBudgetData.m_Service == servicePrefab)
			{
				return serviceBudgetData.m_Budget;
			}
		}
		return 100;
	}
```

- `public static GetServiceBudget(Unity.Entities.Entity servicePrefab, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas) : System.Int32`  

```csharp
public static int GetServiceBudget(Entity servicePrefab, NativeParallelHashMap<Entity, CollectedCityServiceBudgetData> budgets, Entity budgetEntity, BufferLookup<ServiceBudgetData> budgetDatas)
	{
		if (!budgets.ContainsKey(servicePrefab))
		{
			return 0;
		}
		DynamicBuffer<ServiceBudgetData> dynamicBuffer = budgetDatas[budgetEntity];
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			ServiceBudgetData serviceBudgetData = dynamicBuffer[i];
			if (serviceBudgetData.m_Service == servicePrefab)
			{
				return serviceBudgetData.m_Budget;
			}
		}
		return 100;
	}
```

- `public GetServiceBuildings(Unity.Entities.Entity servicePrefab) : Unity.Entities.Entity[]`  

```csharp
public Entity[] GetServiceBuildings(Entity servicePrefab)
	{
		NativeArray<Entity> nativeArray = m_ServiceObjectQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<ServiceObjectData> nativeArray2 = m_ServiceObjectQuery.ToComponentDataArray<ServiceObjectData>(Allocator.TempJob);
		List<Entity> list = new List<Entity>(4);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (nativeArray2[i].m_Service == servicePrefab)
			{
				list.Add(nativeArray[i]);
			}
		}
		nativeArray.Dispose();
		nativeArray2.Dispose();
		return list.ToArray();
	}
```

- `public GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget) : System.Int32`  

```csharp
public int GetServiceEfficiency(Entity servicePrefab, int budget)
	{
		return Mathf.RoundToInt(100f * __query_844909884_0.GetSingleton<BuildingEfficiencyParameterData>().m_ServiceBudgetEfficiencyFactor.Evaluate((float)budget / 100f));
	}
```

- `public GetTotalExpenses() : System.Int32`  

```csharp
public static int GetTotalExpenses(NativeArray<int> expenses)
	{
		int num = 0;
		for (int i = 0; i < expenses.Length; i++)
		{
			num -= expenses[i];
		}
		return num;
	}
```

- `public static GetTotalExpenses(Unity.Collections.NativeArray<System.Int32> expenses) : System.Int32`  

```csharp
public static int GetTotalExpenses(NativeArray<int> expenses)
	{
		int num = 0;
		for (int i = 0; i < expenses.Length; i++)
		{
			num -= expenses[i];
		}
		return num;
	}
```

- `public GetTotalIncome() : System.Int32`  

```csharp
public int GetTotalIncome(IncomeSource source)
	{
		if ((int)source < m_TotalIncome.Length)
		{
			return m_TotalIncome[(int)source];
		}
		return 0;
	}
```

- `public static GetTotalIncome(Unity.Collections.NativeArray<System.Int32> income) : System.Int32`  

```csharp
public int GetTotalIncome(IncomeSource source)
	{
		if ((int)source < m_TotalIncome.Length)
		{
			return m_TotalIncome[(int)source];
		}
		return 0;
	}
```

- `public GetTotalIncome(Game.City.IncomeSource source) : System.Int32`  

```csharp
public int GetTotalIncome(IncomeSource source)
	{
		if ((int)source < m_TotalIncome.Length)
		{
			return m_TotalIncome[(int)source];
		}
		return 0;
	}
```

- `public GetTotalTaxIncome() : System.Int32`  

```csharp
private static int GetTotalTaxIncome(NativeArray<int> income)
	{
		return GetIncome(IncomeSource.TaxCommercial, income) + GetIncome(IncomeSource.TaxIndustrial, income) + GetIncome(IncomeSource.TaxResidential, income) + GetIncome(IncomeSource.TaxOffice, income);
	}
```

- `private static GetTotalTaxIncome(Unity.Collections.NativeArray<System.Int32> income) : System.Int32`  

```csharp
private static int GetTotalTaxIncome(NativeArray<int> income)
	{
		return GetIncome(IncomeSource.TaxCommercial, income) + GetIncome(IncomeSource.TaxIndustrial, income) + GetIncome(IncomeSource.TaxResidential, income) + GetIncome(IncomeSource.TaxOffice, income);
	}
```

- `public GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab) : Unity.Mathematics.int2`  

```csharp
public int2 GetWorkersAndWorkplaces(Entity serviceBuildingPrefab)
	{
		if (base.EntityManager.HasComponent<CollectedServiceBuildingBudgetData>(serviceBuildingPrefab))
		{
			CollectedServiceBuildingBudgetData componentData = base.EntityManager.GetComponentData<CollectedServiceBuildingBudgetData>(serviceBuildingPrefab);
			return new int2(componentData.m_Workers, componentData.m_Workplaces);
		}
		return new int2(0, 0);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_ServiceFeeSystem = base.World.GetOrCreateSystemManaged<ServiceFeeSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_MapTilePurchaseSystem = base.World.GetOrCreateSystemManaged<MapTilePurchaseSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_GameModeGovernmentSubsidiesSystem = base.World.GetOrCreateSystemManaged<GameModeGovernmentSubsidiesSystem>();
		m_TotalIncome = new NativeArray<int>(14, Allocator.Persistent);
		m_Income = new NativeArray<int>(14, Allocator.Persistent);
		m_IncomeTemp = new NativeArray<int>(14, Allocator.Persistent);
		m_Expenses = new NativeArray<int>(15, Allocator.Persistent);
		m_ExpensesTemp = new NativeArray<int>(15, Allocator.Persistent);
		m_CityServiceUpkeepIndices = new NativeParallelHashMap<Entity, int2>(4, Allocator.Persistent);
		m_CityServiceUpkeeps = new NativeList<CollectedCityServiceUpkeepData>(4, Allocator.Persistent);
		m_CityServiceBudgets = new NativeParallelHashMap<Entity, CollectedCityServiceBudgetData>(4, Allocator.Persistent);
		m_TotalTaxes = new NativeReference<int>(Allocator.Persistent);
		m_ServiceQuery = GetEntityQuery(ComponentType.ReadWrite<CollectedCityServiceBudgetData>(), ComponentType.ReadWrite<CollectedCityServiceUpkeepData>());
		m_ServiceObjectQuery = GetEntityQuery(ComponentType.ReadWrite<CollectedServiceBuildingBudgetData>(), ComponentType.ReadOnly<ServiceObjectData>());
		m_UpkeepGroup = GetEntityQuery(ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_BudgetDataQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceBudgetData>());
		m_ServiceBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_NetUpkeepQuery = GetEntityQuery(ComponentType.ReadOnly<Composition>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Owner>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Native>(), ComponentType.Exclude<Temp>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_HealthcareFacilityQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.Hospital>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_DeathcareFacilityQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.DeathcareFacility>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_GarbageFacilityQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.GarbageFacility>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_FireStationQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.FireStation>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_PoliceStationQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.PoliceStation>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_OutsideTradeParameterQuery = GetEntityQuery(ComponentType.ReadOnly<OutsideTradeParameterData>());
		RequireForUpdate(m_BudgetDataQuery);
		RequireForUpdate(m_ServiceQuery);
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
		m_Income.Dispose();
		m_IncomeTemp.Dispose();
		m_TotalIncome.Dispose();
		m_Expenses.Dispose();
		m_ExpensesTemp.Dispose();
		m_CityServiceUpkeeps.Dispose();
		m_CityServiceBudgets.Dispose();
		m_CityServiceUpkeepIndices.Dispose();
		m_TotalTaxes.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		if (m_BudgetDataQuery.CalculateEntityCount() == 0)
		{
			base.EntityManager.CreateEntity(ComponentType.ReadWrite<ServiceBudgetData>());
		}
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_TotalTaxIncome = m_TotalTaxes.Value;
		m_TempArrayDeps.Complete();
		m_IncomeTemp.CopyTo(m_Income);
		m_ExpensesTemp.CopyTo(m_Expenses);
		JobHandle outJobHandle;
		NativeList<Entity> cityServiceEntities = m_ServiceQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle);
		UpdateDataJob jobData = new UpdateDataJob
		{
			m_CityServiceEntities = cityServiceEntities,
			m_City = m_CitySystem.City,
			m_Lookup = m_CityStatisticsSystem.GetLookup(),
			m_Stats = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RO_BufferLookup, ref base.CheckedStateRef),
			m_CollectedFees = m_ServiceFeeSystem.GetServiceFees(),
			m_BudgetDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ServiceBudgetData_RO_BufferLookup, ref base.CheckedStateRef),
			m_Loans = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_Loan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BudgetEntity = m_BudgetDataQuery.GetSingletonEntity(),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_CityServiceBudgets = m_CityServiceBudgets,
			m_CityServiceUpkeepIndices = m_CityServiceUpkeepIndices,
			m_CityServiceUpkeeps = m_CityServiceUpkeeps,
			m_CollectedBudgets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceBudgetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CollectedUpkeeps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceUpkeepData_RO_BufferLookup, ref base.CheckedStateRef),
			m_Creditworthiness = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_Creditworthiness_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Expenses = m_ExpensesTemp,
			m_ServiceFees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_ServiceFee_RO_BufferLookup, ref base.CheckedStateRef),
			m_Income = m_IncomeTemp,
			m_TaxRates = m_TaxSystem.GetTaxRates(),
			m_Populations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_City_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideTradeParameterData = m_OutsideTradeParameterQuery.GetSingleton<OutsideTradeParameterData>(),
			m_EconomyParametersData = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_MonthlySubsidy = m_GameModeGovernmentSubsidiesSystem.monthlySubsidy,
			m_TotalTaxes = m_TotalTaxes,
			m_ServiceFacilityBuildingCount = new int4(m_HealthcareFacilityQuery.CalculateEntityCount(), m_DeathcareFacilityQuery.CalculateEntityCount(), m_GarbageFacilityQuery.CalculateEntityCount(), m_FireStationQuery.CalculateEntityCount()),
			m_PoliceStationBuildingCount = m_PoliceStationQuery.CalculateEntityCount(),
			m_MapTileUpkeepCost = ((!m_CityConfigurationSystem.unlockMapTiles) ? m_MapTilePurchaseSystem.CalculateOwnedTilesUpkeep() : 0)
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(outJobHandle, m_TempArrayDeps, base.Dependency));
		m_TaxSystem.AddReader(base.Dependency);
		m_TempArrayDeps = base.Dependency;
		cityServiceEntities.Dispose(base.Dependency);
		ClearServiceDataJob jobData2 = new ClearServiceDataJob
		{
			m_BudgetDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_CollectedCityServiceBudgetData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpkeepDataType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_CollectedCityServiceUpkeepData_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_ServiceQuery, base.Dependency);
		CityServiceBudgetJob jobData3 = new CityServiceBudgetJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceObjectDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpkeepDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpkeepData_RO_BufferLookup, ref base.CheckedStateRef),
			m_ServiceUsages = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUsage_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgradeBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_EmployeeBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_BudgetDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceBudgetData_RW_ComponentLookup, ref base.CheckedStateRef),
			m_UpkeepDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceUpkeepData_RW_BufferLookup, ref base.CheckedStateRef),
			m_ServiceBudgets = m_BudgetDataQuery.GetSingletonBuffer<ServiceBudgetData>(isReadOnly: true),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_EconomyParameterData = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData3, m_UpkeepGroup, base.Dependency);
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(new ClearBuildingDataJob
		{
			m_BudgetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_CollectedServiceBuildingBudgetData_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		}, m_ServiceObjectQuery, base.Dependency);
		JobHandle job = JobChunkExtensions.Schedule(new CollectServiceBuildingBudgetDatasJob
		{
			m_WorkProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EmployeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_Employee_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Budgets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_CollectedServiceBuildingBudgetData_RW_ComponentLookup, ref base.CheckedStateRef)
		}, m_ServiceBuildingQuery, dependsOn);
		JobHandle job2 = JobChunkExtensions.Schedule(new NetServiceBudgetJob
		{
			m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceObjects = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableNetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BudgetDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceBudgetData_RW_ComponentLookup, ref base.CheckedStateRef)
		}, m_NetUpkeepQuery, base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(job, job2);
	}
```

- `public SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage) : System.Void`  

```csharp
public void SetServiceBudget(Entity servicePrefab, int percentage)
	{
		m_TempArrayDeps.Complete();
		if (!m_CityServiceBudgets.ContainsKey(servicePrefab))
		{
			return;
		}
		Entity singletonEntity = m_BudgetDataQuery.GetSingletonEntity();
		DynamicBuffer<ServiceBudgetData> buffer = base.EntityManager.GetBuffer<ServiceBudgetData>(singletonEntity);
		bool flag = false;
		bool flag2 = false;
		for (int i = 0; i < buffer.Length; i++)
		{
			ServiceBudgetData value = buffer[i];
			if (value.m_Service == servicePrefab)
			{
				flag = value.m_Budget != percentage;
				value.m_Budget = percentage;
				buffer[i] = value;
				flag2 = true;
				break;
			}
		}
		if (!flag2)
		{
			flag = true;
			buffer.Add(new ServiceBudgetData
			{
				m_Service = servicePrefab,
				m_Budget = percentage
			});
		}
		if (flag)
		{
			m_EndFrameBarrier.CreateCommandBuffer().AddComponent<Updated>(singletonEntity);
		}
	}
```


## Nested types

- `Game.Simulation.CityServiceBudgetSystem+UpdateDataJob`  
- `Game.Simulation.CityServiceBudgetSystem+ClearServiceDataJob`  
- `Game.Simulation.CityServiceBudgetSystem+CityServiceBudgetJob`  
- `Game.Simulation.CityServiceBudgetSystem+ClearBuildingDataJob`  
- `Game.Simulation.CityServiceBudgetSystem+CollectServiceBuildingBudgetDatasJob`  
- `Game.Simulation.CityServiceBudgetSystem+NetServiceBudgetJob`  
- `Game.Simulation.CityServiceBudgetSystem+TypeHandle`  

