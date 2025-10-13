# Game.UI.InGame.ToolbarBottomUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolbarBottomUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
    private Colossal.UI.Binding.GetterValueBinding<System.String> m_CityNameBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyDeltaBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationDeltaBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_UnlimitedMoneyBinding;
    private Game.Prefabs.UIToolbarBottomConfigurationPrefab m_ToolbarBottomConfigurationPrefab;
    private Unity.Entities.EntityQuery m_ToolbarBottomConfigurationQuery;
    private Game.UI.InGame.ToolbarBottomUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_2118611066_0;
    private static const System.String kGroup;

    public ToolbarBottomUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.String <OnCreate>b__14_0();
    private System.Int32 <OnCreate>b__14_1();
    private System.Boolean <OnCreate>b__14_2();
    private Unity.Mathematics.float2 <OnCreate>b__14_3();
    private Unity.Mathematics.float2 <OnCreate>b__14_4();
    private System.Int32 GetPopulation();
    private System.Int32 GetPopulationDelta();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void SetCityName(System.String name);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  

```csharp
private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.String> m_CityNameBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.String> m_CityNameBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyDeltaBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyDeltaBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationDeltaBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationDeltaBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_UnlimitedMoneyBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_UnlimitedMoneyBinding;
```

- `private Game.Prefabs.UIToolbarBottomConfigurationPrefab m_ToolbarBottomConfigurationPrefab`  

```csharp
private Game.Prefabs.UIToolbarBottomConfigurationPrefab m_ToolbarBottomConfigurationPrefab;
```

- `private Unity.Entities.EntityQuery m_ToolbarBottomConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ToolbarBottomConfigurationQuery;
```

- `private Game.UI.InGame.ToolbarBottomUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.ToolbarBottomUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_2118611066_0`  

```csharp
private Unity.Entities.EntityQuery __query_2118611066_0;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public ToolbarBottomUISystem()`  

```csharp
[Preserve]
	public ToolbarBottomUISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<UIToolbarBottomConfigurationData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2118611066_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `private <OnCreate>b__14_0() : System.String`  

```csharp
private System.String <OnCreate>b__14_0();
```

- `private <OnCreate>b__14_1() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_1();
```

- `private <OnCreate>b__14_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__14_2();
```

- `private <OnCreate>b__14_3() : Unity.Mathematics.float2`  

```csharp
private Unity.Mathematics.float2 <OnCreate>b__14_3();
```

- `private <OnCreate>b__14_4() : Unity.Mathematics.float2`  

```csharp
private Unity.Mathematics.float2 <OnCreate>b__14_4();
```

- `private GetPopulation() : System.Int32`  

```csharp
private int GetPopulation()
	{
		if (base.EntityManager.HasComponent<Population>(m_CitySystem.City))
		{
			return base.EntityManager.GetComponentData<Population>(m_CitySystem.City).m_Population;
		}
		return 0;
	}
```

- `private GetPopulationDelta() : System.Int32`  

```csharp
private int GetPopulationDelta()
	{
		Population population = default(Population);
		if (base.EntityManager.HasComponent<Population>(m_CitySystem.City))
		{
			population = base.EntityManager.GetComponentData<Population>(m_CitySystem.City);
		}
		NativeArray<int> statisticDataArray = m_CityStatisticsSystem.GetStatisticDataArray(StatisticType.Population);
		if (statisticDataArray.Length == 0)
		{
			return population.m_Population;
		}
		int num = ((statisticDataArray.Length >= 2) ? statisticDataArray[statisticDataArray.Length - 2] : 0);
		int num2 = statisticDataArray[statisticDataArray.Length - 1];
		float t = (float)(long)(m_CityStatisticsSystem.GetSampleFrameIndex(m_CityStatisticsSystem.sampleCount - 1) % 8192) / 8192f;
		return (population.m_Population - Mathf.RoundToInt(math.lerp(num, num2, t))) * 32 / 24;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityServiceBudgetSystem = base.World.GetOrCreateSystemManaged<CityServiceBudgetSystem>();
		m_ToolbarBottomConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<UIToolbarBottomConfigurationData>());
		AddBinding(m_CityNameBinding = new GetterValueBinding<string>("toolbarBottom", "cityName", () => m_CityConfigurationSystem.cityName ?? ""));
		AddBinding(m_MoneyBinding = new GetterValueBinding<int>("toolbarBottom", "money", () => m_CitySystem.moneyAmount));
		AddBinding(m_MoneyDeltaBinding = new GetterValueBinding<int>("toolbarBottom", "moneyDelta", m_CityServiceBudgetSystem.GetMoneyDelta));
		AddBinding(m_UnlimitedMoneyBinding = new GetterValueBinding<bool>("toolbarBottom", "unlimitedMoney", () => m_CityConfigurationSystem.unlimitedMoney));
		AddBinding(m_PopulationBinding = new GetterValueBinding<int>("toolbarBottom", "population", GetPopulation));
		AddBinding(m_PopulationDeltaBinding = new GetterValueBinding<int>("toolbarBottom", "populationDelta", GetPopulationDelta));
		AddBinding(new GetterValueBinding<float2>("toolbarBottom", "populationTrendThresholds", () => new float2(m_ToolbarBottomConfigurationPrefab.m_PopulationTrendThresholds.m_Medium, m_ToolbarBottomConfigurationPrefab.m_PopulationTrendThresholds.m_High)));
		AddBinding(new GetterValueBinding<float2>("toolbarBottom", "moneyTrendThresholds", () => new float2(m_ToolbarBottomConfigurationPrefab.m_MoneyTrendThresholds.m_Medium, m_ToolbarBottomConfigurationPrefab.m_MoneyTrendThresholds.m_High)));
		AddBinding(new TriggerBinding<string>("toolbarBottom", "setCityName", SetCityName));
		RequireForUpdate(m_ToolbarBottomConfigurationQuery);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_CityNameBinding.Update();
		m_MoneyBinding.Update();
		m_PopulationBinding.Update();
		m_MoneyDeltaBinding.Update();
		m_PopulationDeltaBinding.Update();
		m_UnlimitedMoneyBinding.Update();
		if (m_ToolbarBottomConfigurationPrefab == null)
		{
			Entity singletonEntity = __query_2118611066_0.GetSingletonEntity();
			m_ToolbarBottomConfigurationPrefab = m_PrefabSystem.GetPrefab<UIToolbarBottomConfigurationPrefab>(singletonEntity);
		}
	}
```

- `private SetCityName(System.String name) : System.Void`  

```csharp
private void SetCityName(string name)
	{
		m_CityConfigurationSystem.cityName = name;
		m_CityNameBinding.Update();
	}
```


## Nested types

- `Game.UI.InGame.ToolbarBottomUISystem+TypeHandle`  

