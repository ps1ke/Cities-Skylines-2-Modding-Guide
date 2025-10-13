# Game.UI.InGame.HealthcareInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HealthcareInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHealth;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCount;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_SickCount;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_DeathRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_ProcessingRate;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryUse;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryCapacity;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HealthcareAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_DeathcareAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CemeteryAvailability;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_DeathcareFacilityQuery;
    private Unity.Entities.EntityQuery m_HealthcareFacilityQuery;
    private Unity.Entities.EntityQuery m_DeathcareFacilityModifiedQuery;
    private Unity.Entities.EntityQuery m_HealthcareFacilityModifiedQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public HealthcareInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.UI.InGame.IndicatorValue GetCemeteryAvailability();
    private Game.UI.InGame.IndicatorValue GetDeathcareAvailability();
    private Game.UI.InGame.IndicatorValue GetHealthcareAvailability();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHealth`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHealth;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCount`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCount;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SickCount`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_SickCount;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_DeathRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_DeathRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ProcessingRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_ProcessingRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryUse`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryUse;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryCapacity;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HealthcareAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HealthcareAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_DeathcareAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_DeathcareAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CemeteryAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CemeteryAvailability;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_DeathcareFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeathcareFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_DeathcareFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeathcareFacilityModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareFacilityModifiedQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public HealthcareInfoviewUISystem()`  

```csharp
[Preserve]
	public HealthcareInfoviewUISystem()
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

- `private GetCemeteryAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetCemeteryAvailability()
	{
		return IndicatorValue.Calculate(m_CemeteryCapacity.value, m_CemeteryUse.value);
	}
```

- `private GetDeathcareAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetDeathcareAvailability()
	{
		return IndicatorValue.Calculate(m_ProcessingRate.value, m_DeathRate.value);
	}
```

- `private GetHealthcareAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetHealthcareAvailability()
	{
		return IndicatorValue.Calculate(m_PatientCapacity.value, m_SickCount.value);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_HouseholdQuery = GetEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.Exclude<CommuterHousehold>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<MovingAway>());
		m_DeathcareFacilityQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.DeathcareFacility>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Patient>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_DeathcareFacilityModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[5]
			{
				ComponentType.ReadOnly<Game.Buildings.DeathcareFacility>(),
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<ServiceDispatch>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<Patient>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_HealthcareFacilityQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.Hospital>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Patient>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_HealthcareFacilityModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[5]
			{
				ComponentType.ReadOnly<Game.Buildings.Hospital>(),
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<ServiceDispatch>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<Patient>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		AddBinding(m_AverageHealth = new ValueBinding<float>("healthcareInfo", "averageHealth", 0f));
		AddBinding(m_DeathRate = new ValueBinding<float>("healthcareInfo", "deathRate", 0f));
		AddBinding(m_ProcessingRate = new ValueBinding<float>("healthcareInfo", "processingRate", 0f));
		AddBinding(m_CemeteryUse = new ValueBinding<int>("healthcareInfo", "cemeteryUse", 0));
		AddBinding(m_CemeteryCapacity = new ValueBinding<int>("healthcareInfo", "cemeteryCapacity", 0));
		AddBinding(m_SickCount = new ValueBinding<int>("healthcareInfo", "sickCount", 0));
		AddBinding(m_PatientCount = new ValueBinding<int>("healthcareInfo", "patientCount", 0));
		AddBinding(m_PatientCapacity = new ValueBinding<int>("healthcareInfo", "patientCapacity", 0));
		AddBinding(m_HealthcareAvailability = new GetterValueBinding<IndicatorValue>("healthcareInfo", "healthcareAvailability", GetHealthcareAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_DeathcareAvailability = new GetterValueBinding<IndicatorValue>("healthcareInfo", "deathcareAvailability", GetDeathcareAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_CemeteryAvailability = new GetterValueBinding<IndicatorValue>("healthcareInfo", "cemeteryAvailability", GetCemeteryAvailability, new ValueWriter<IndicatorValue>()));
		m_Results = new NativeArray<float>(8, Allocator.Persistent);
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
		m_Results.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		m_Results.Fill(0f);
		JobChunkExtensions.Schedule(new CalculateAverageHealthJob
		{
			m_HouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizenType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_HouseholdQuery, base.Dependency).Complete();
		JobChunkExtensions.Schedule(new UpdateHealthcareJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PatientType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Patient_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HospitalDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_HospitalData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Result = m_Results
		}, m_HealthcareFacilityQuery, base.Dependency).Complete();
		JobChunkExtensions.Schedule(new UpdateDeathcareJob
		{
			m_DeathcareFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_DeathcareFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_DeathcareFacilities = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DeathcareFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_DeathcareFacilityQuery, base.Dependency).Complete();
		float num = m_Results[0];
		float x = m_Results[1];
		m_AverageHealth.Update(math.round(num / math.max(x, 1f)));
		m_PatientCount.Update((int)m_Results[3]);
		m_SickCount.Update((int)m_Results[2]);
		m_PatientCapacity.Update((int)m_Results[4]);
		m_DeathRate.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.DeathRate));
		m_ProcessingRate.Update(m_Results[5]);
		m_CemeteryUse.Update((int)m_Results[6]);
		m_CemeteryCapacity.Update((int)m_Results[7]);
		m_DeathcareAvailability.Update();
		m_CemeteryAvailability.Update();
		m_HealthcareAvailability.Update();
	}
```


## Nested types

- `Game.UI.InGame.HealthcareInfoviewUISystem+Result`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+CalculateAverageHealthJob`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+UpdateHealthcareJob`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+UpdateDeathcareJob`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle`  

