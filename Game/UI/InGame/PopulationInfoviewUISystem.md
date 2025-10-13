# Game.UI.InGame.PopulationInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class PopulationInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Population;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Employed;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Jobs;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_Unemployment;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_Homelessness;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_BirthRate;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeathRate;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedIn;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedAway;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Homeless;
    private Colossal.UI.Binding.RawValueBinding m_AgeData;
    private Unity.Entities.EntityQuery m_WorkProviderModifiedQuery;
    private Unity.Entities.EntityQuery m_PopulationModifiedQuery;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public PopulationInfoviewUISystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void PerformUpdate();
    private System.Void UpdateAgeData(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateBindings();
    private System.Void UpdateStatistics();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Population`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Population;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Employed`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Employed;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Jobs`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Jobs;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_Unemployment`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_Unemployment;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_Homelessness`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_Homelessness;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_BirthRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_BirthRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeathRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeathRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedIn`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedIn;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedAway`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedAway;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Homeless`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Homeless;
```

- `private Colossal.UI.Binding.RawValueBinding m_AgeData`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_AgeData;
```

- `private Unity.Entities.EntityQuery m_WorkProviderModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkProviderModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationModifiedQuery;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `public PopulationInfoviewUISystem()`  

```csharp
[Preserve]
	public PopulationInfoviewUISystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CountWorkplacesSystem = base.World.GetOrCreateSystemManaged<CountWorkplacesSystem>();
		m_CountHouseholdDataSystem = base.World.GetOrCreateSystemManaged<CountHouseholdDataSystem>();
		m_WorkProviderModifiedQuery = GetEntityQuery(ComponentType.ReadOnly<WorkProvider>(), ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Temp>());
		m_PopulationModifiedQuery = GetEntityQuery(ComponentType.ReadOnly<Population>(), ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Temp>());
		AddBinding(m_Population = new ValueBinding<int>("populationInfo", "population", 0));
		AddBinding(m_Employed = new ValueBinding<int>("populationInfo", "employed", 0));
		AddBinding(m_Jobs = new ValueBinding<int>("populationInfo", "jobs", 0));
		AddBinding(m_Unemployment = new ValueBinding<float>("populationInfo", "unemployment", 0f));
		AddBinding(m_BirthRate = new ValueBinding<int>("populationInfo", "birthRate", 0));
		AddBinding(m_DeathRate = new ValueBinding<int>("populationInfo", "deathRate", 0));
		AddBinding(m_MovedIn = new ValueBinding<int>("populationInfo", "movedIn", 0));
		AddBinding(m_MovedAway = new ValueBinding<int>("populationInfo", "movedAway", 0));
		AddBinding(m_Homeless = new ValueBinding<int>("populationInfo", "homeless", 0));
		AddBinding(m_Homelessness = new ValueBinding<float>("populationInfo", "homelessness", 0f));
		AddBinding(m_AgeData = new RawValueBinding("populationInfo", "ageData", UpdateAgeData));
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		UpdateBindings();
	}
```

- `private UpdateAgeData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateAgeData(IJsonWriter binder)
	{
		binder.TypeBegin("infoviews.ChartData");
		binder.PropertyName("values");
		binder.ArrayBegin(4u);
		binder.Write(m_CountHouseholdDataSystem.ChildrenCount);
		binder.Write(m_CountHouseholdDataSystem.TeenCount);
		binder.Write(m_CountHouseholdDataSystem.AdultCount);
		binder.Write(m_CountHouseholdDataSystem.SeniorCount);
		binder.ArrayEnd();
		binder.PropertyName("total");
		binder.Write(m_CountHouseholdDataSystem.MovedInCitizenCount);
		binder.TypeEnd();
	}
```

- `private UpdateBindings() : System.Void`  

```csharp
private void UpdateBindings()
	{
		m_Jobs.Update(m_CountWorkplacesSystem.GetTotalWorkplaces().TotalCount);
		m_Employed.Update(m_CountHouseholdDataSystem.CityWorkerCount);
		m_Unemployment.Update(m_CountHouseholdDataSystem.UnemploymentRate);
		m_Homelessness.Update(m_CountHouseholdDataSystem.HomelessnessRate);
		m_Homeless.Update(m_CountHouseholdDataSystem.HomelessCitizenCount);
		Population componentData = base.EntityManager.GetComponentData<Population>(m_CitySystem.City);
		m_Population.Update(componentData.m_Population);
		m_AgeData.Update();
		UpdateStatistics();
	}
```

- `private UpdateStatistics() : System.Void`  

```csharp
private void UpdateStatistics()
	{
		m_BirthRate.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.BirthRate));
		m_DeathRate.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.DeathRate));
		m_MovedIn.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.CitizensMovedIn));
		m_MovedAway.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.CitizensMovedAway));
	}
```


