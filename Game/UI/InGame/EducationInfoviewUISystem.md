# Game.UI.InGame.EducationInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EducationInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Colossal.UI.Binding.RawValueBinding m_EducationData;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryStudents;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolStudents;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeStudents;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityStudents;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryEligible;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolEligible;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeEligible;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityEligible;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityCapacity;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElementaryAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HighSchoolAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CollegeAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_UniversityAvailability;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_SchoolQuery;
    private Unity.Entities.EntityQuery m_SchoolModifiedQuery;
    private Unity.Entities.EntityQuery m_EligibleQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.EducationInfoviewUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_607537787_0;
    private Unity.Entities.EntityQuery __query_607537787_1;
    private Unity.Entities.EntityQuery __query_607537787_2;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public EducationInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
    private Game.UI.InGame.IndicatorValue UpdateCollegeAvailability();
    private System.Void UpdateEducationData(Colossal.UI.Binding.IJsonWriter binder);
    private Game.UI.InGame.IndicatorValue UpdateElementaryAvailability();
    private System.Void UpdateEligibility();
    private Game.UI.InGame.IndicatorValue UpdateHighSchoolAvailability();
    private System.Void UpdateStudentCounts();
    private Game.UI.InGame.IndicatorValue UpdateUniversityAvailability();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Colossal.UI.Binding.RawValueBinding m_EducationData`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_EducationData;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryStudents`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryStudents;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolStudents`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolStudents;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeStudents`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeStudents;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityStudents`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityStudents;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryEligible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryEligible;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolEligible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolEligible;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeEligible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeEligible;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityEligible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityEligible;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityCapacity;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElementaryAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElementaryAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HighSchoolAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HighSchoolAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CollegeAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CollegeAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_UniversityAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_UniversityAvailability;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_SchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_SchoolQuery;
```

- `private Unity.Entities.EntityQuery m_SchoolModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_SchoolModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_EligibleQuery`  

```csharp
private Unity.Entities.EntityQuery m_EligibleQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.EducationInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.EducationInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_607537787_0`  

```csharp
private Unity.Entities.EntityQuery __query_607537787_0;
```

- `private Unity.Entities.EntityQuery __query_607537787_1`  

```csharp
private Unity.Entities.EntityQuery __query_607537787_1;
```

- `private Unity.Entities.EntityQuery __query_607537787_2`  

```csharp
private Unity.Entities.EntityQuery __query_607537787_2;
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

- `public EducationInfoviewUISystem()`  

```csharp
[Preserve]
	public EducationInfoviewUISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<EconomyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_607537787_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<EducationParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_607537787_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<TimeData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_607537787_2 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		RequireForUpdate<EconomyParameterData>();
		RequireForUpdate<TimeData>();
		m_HouseholdQuery = GetEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<CommuterHousehold>(), ComponentType.Exclude<MovingAway>());
		m_SchoolQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Buildings.School>(), ComponentType.ReadOnly<Game.Buildings.Student>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_SchoolModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Buildings.School>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_EligibleQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadWrite<Citizen>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<HasJobSeeker>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		AddBinding(m_EducationData = new RawValueBinding("educationInfo", "educationData", UpdateEducationData));
		AddBinding(m_ElementaryStudents = new ValueBinding<int>("educationInfo", "elementaryStudentCount", 0));
		AddBinding(m_HighSchoolStudents = new ValueBinding<int>("educationInfo", "highSchoolStudentCount", 0));
		AddBinding(m_CollegeStudents = new ValueBinding<int>("educationInfo", "collegeStudentCount", 0));
		AddBinding(m_UniversityStudents = new ValueBinding<int>("educationInfo", "universityStudentCount", 0));
		AddBinding(m_ElementaryEligible = new ValueBinding<int>("educationInfo", "elementaryEligible", 0));
		AddBinding(m_HighSchoolEligible = new ValueBinding<int>("educationInfo", "highSchoolEligible", 0));
		AddBinding(m_CollegeEligible = new ValueBinding<int>("educationInfo", "collegeEligible", 0));
		AddBinding(m_UniversityEligible = new ValueBinding<int>("educationInfo", "universityEligible", 0));
		AddBinding(m_ElementaryCapacity = new ValueBinding<int>("educationInfo", "elementaryCapacity", 0));
		AddBinding(m_HighSchoolCapacity = new ValueBinding<int>("educationInfo", "highSchoolCapacity", 0));
		AddBinding(m_CollegeCapacity = new ValueBinding<int>("educationInfo", "collegeCapacity", 0));
		AddBinding(m_UniversityCapacity = new ValueBinding<int>("educationInfo", "universityCapacity", 0));
		AddBinding(m_ElementaryAvailability = new GetterValueBinding<IndicatorValue>("educationInfo", "elementaryAvailability", UpdateElementaryAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_HighSchoolAvailability = new GetterValueBinding<IndicatorValue>("educationInfo", "highSchoolAvailability", UpdateHighSchoolAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_CollegeAvailability = new GetterValueBinding<IndicatorValue>("educationInfo", "collegeAvailability", UpdateCollegeAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_UniversityAvailability = new GetterValueBinding<IndicatorValue>("educationInfo", "universityAvailability", UpdateUniversityAvailability, new ValueWriter<IndicatorValue>()));
		m_Results = new NativeArray<int>(17, Allocator.Persistent);
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
		ResetResults();
		UpdateStudentCounts();
		UpdateEligibility();
		m_EducationData.Update();
		m_ElementaryStudents.Update(m_Results[9]);
		m_ElementaryCapacity.Update(m_Results[13]);
		m_ElementaryEligible.Update(m_Results[5]);
		m_HighSchoolStudents.Update(m_Results[10]);
		m_HighSchoolCapacity.Update(m_Results[14]);
		m_HighSchoolEligible.Update(m_Results[6]);
		m_CollegeStudents.Update(m_Results[11]);
		m_CollegeCapacity.Update(m_Results[15]);
		m_CollegeEligible.Update(m_Results[7]);
		m_UniversityStudents.Update(m_Results[12]);
		m_UniversityCapacity.Update(m_Results[16]);
		m_UniversityEligible.Update(m_Results[8]);
		m_ElementaryAvailability.Update();
		m_HighSchoolAvailability.Update();
		m_CollegeAvailability.Update();
		m_UniversityAvailability.Update();
	}
```

- `private ResetResults() : System.Void`  

```csharp
private void ResetResults()
	{
		for (int i = 0; i < m_Results.Length; i++)
		{
			m_Results[i] = 0;
		}
	}
```

- `private UpdateCollegeAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue UpdateCollegeAvailability()
	{
		return IndicatorValue.Calculate(m_CollegeCapacity.value, m_CollegeEligible.value);
	}
```

- `private UpdateEducationData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateEducationData(IJsonWriter binder)
	{
		JobChunkExtensions.Schedule(new UpdateEducationDataJob
		{
			m_HouseholdHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizenHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CitizenFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblemFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_HouseholdQuery, base.Dependency).Complete();
		InfoviewsUIUtils.UpdateFiveSlicePieChartData(binder, m_Results[0], m_Results[1], m_Results[2], m_Results[3], m_Results[4]);
	}
```

- `private UpdateElementaryAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue UpdateElementaryAvailability()
	{
		return IndicatorValue.Calculate(m_ElementaryCapacity.value, m_ElementaryEligible.value);
	}
```

- `private UpdateEligibility() : System.Void`  

```csharp
private void UpdateEligibility()
	{
		JobChunkExtensions.Schedule(new UpdateEligibilityJob
		{
			m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CitizenHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StudentHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WorkerHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdMemberFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblemFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingAways = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_MovingAway_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceFeeFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_ServiceFee_RO_BufferLookup, ref base.CheckedStateRef),
			m_CityModifierFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_City = m_CitySystem.City,
			m_EconomyParameterData = __query_607537787_0.GetSingleton<EconomyParameterData>(),
			m_EducationParameterData = __query_607537787_1.GetSingleton<EducationParameterData>(),
			m_TimeData = __query_607537787_2.GetSingleton<TimeData>(),
			m_Results = m_Results
		}, m_EligibleQuery, base.Dependency).Complete();
	}
```

- `private UpdateHighSchoolAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue UpdateHighSchoolAvailability()
	{
		return IndicatorValue.Calculate(m_HighSchoolCapacity.value, m_HighSchoolEligible.value);
	}
```

- `private UpdateStudentCounts() : System.Void`  

```csharp
private void UpdateStudentCounts()
	{
		JobChunkExtensions.Schedule(new UpdateStudentCountsJob
		{
			m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_StudentHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Student_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SchoolDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SchoolData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgradeFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_SchoolQuery, base.Dependency).Complete();
	}
```

- `private UpdateUniversityAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue UpdateUniversityAvailability()
	{
		return IndicatorValue.Calculate(m_UniversityCapacity.value, m_UniversityEligible.value);
	}
```


## Nested types

- `Game.UI.InGame.EducationInfoviewUISystem+Result`  
- `Game.UI.InGame.EducationInfoviewUISystem+UpdateEducationDataJob`  
- `Game.UI.InGame.EducationInfoviewUISystem+UpdateStudentCountsJob`  
- `Game.UI.InGame.EducationInfoviewUISystem+UpdateEligibilityJob`  
- `Game.UI.InGame.EducationInfoviewUISystem+TypeHandle`  

