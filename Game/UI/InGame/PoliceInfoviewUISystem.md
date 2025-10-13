# Game.UI.InGame.PoliceInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PoliceInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimeProducers;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_CrimeProbability;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_JailCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ArrestedCriminals;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_InJail;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_PrisonCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Prisoners;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_InPrison;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Criminals;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimePerMonth;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_EscapedRate;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_AverageCrimeProbability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_JailAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_PrisonAvailability;
    private Unity.Entities.EntityQuery m_PrisonQuery;
    private Unity.Entities.EntityQuery m_PrisonModifiedQuery;
    private Unity.Entities.EntityQuery m_CriminalQuery;
    private Unity.Entities.EntityQuery m_PoliceStationQuery;
    private Unity.Entities.EntityQuery m_PoliceStationModifiedQuery;
    private Unity.Entities.EntityQuery m_CrimeProducerQuery;
    private Unity.Entities.EntityQuery m_CrimeProducerModifiedQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_632591896_0;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public PoliceInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.UI.InGame.IndicatorValue GetCrimeProbability();
    private Game.UI.InGame.IndicatorValue GetJailAvailability();
    private Game.UI.InGame.IndicatorValue GetPrisonAvailability();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimeProducers`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimeProducers;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_CrimeProbability`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_CrimeProbability;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_JailCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_JailCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ArrestedCriminals`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ArrestedCriminals;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_InJail`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_InJail;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_PrisonCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_PrisonCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Prisoners`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Prisoners;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_InPrison`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_InPrison;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Criminals`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Criminals;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimePerMonth`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimePerMonth;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_EscapedRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_EscapedRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_AverageCrimeProbability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_AverageCrimeProbability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_JailAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_JailAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_PrisonAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_PrisonAvailability;
```

- `private Unity.Entities.EntityQuery m_PrisonQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrisonQuery;
```

- `private Unity.Entities.EntityQuery m_PrisonModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrisonModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_CriminalQuery`  

```csharp
private Unity.Entities.EntityQuery m_CriminalQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceStationQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceStationModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceStationModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeProducerQuery;
```

- `private Unity.Entities.EntityQuery m_CrimeProducerModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeProducerModifiedQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_632591896_0`  

```csharp
private Unity.Entities.EntityQuery __query_632591896_0;
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

- `public PoliceInfoviewUISystem()`  

```csharp
[Preserve]
	public PoliceInfoviewUISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<PoliceConfigurationData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_632591896_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `private GetCrimeProbability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetCrimeProbability()
	{
		float value = m_CrimeProbability.value;
		int value2 = m_CrimeProducers.value;
		return new IndicatorValue(0f, __query_632591896_0.GetSingleton<PoliceConfigurationData>().m_MaxCrimeAccumulation, (value2 > 0) ? (value / (float)value2) : 0f);
	}
```

- `private GetJailAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetJailAvailability()
	{
		int value = m_JailCapacity.value;
		int value2 = m_ArrestedCriminals.value;
		return IndicatorValue.Calculate(value, value2, 0f);
	}
```

- `private GetPrisonAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetPrisonAvailability()
	{
		int value = m_PrisonCapacity.value;
		int value2 = m_Prisoners.value;
		return IndicatorValue.Calculate(value, value2, 0f);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_PrisonQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Buildings.Prison>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Owner>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_PoliceStationQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Buildings.PoliceStation>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Owner>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_CrimeProducerQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<CrimeProducer>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_CriminalQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<Criminal>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_PrisonModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Buildings.Prison>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_PoliceStationModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Buildings.PoliceStation>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_CrimeProducerModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<CrimeProducer>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		AddBinding(m_CrimeProducers = new ValueBinding<int>("policeInfo", "crimeProducers", 0));
		AddBinding(m_CrimeProbability = new ValueBinding<float>("policeInfo", "crimeProbability", 0f));
		AddBinding(m_PrisonCapacity = new ValueBinding<int>("policeInfo", "prisonCapacity", 0));
		AddBinding(m_Prisoners = new ValueBinding<int>("policeInfo", "prisoners", 0));
		AddBinding(m_InPrison = new ValueBinding<int>("policeInfo", "inPrison", 0));
		AddBinding(m_JailCapacity = new ValueBinding<int>("policeInfo", "jailCapacity", 0));
		AddBinding(m_ArrestedCriminals = new ValueBinding<int>("policeInfo", "arrestedCriminals", 0));
		AddBinding(m_InJail = new ValueBinding<int>("policeInfo", "inJail", 0));
		AddBinding(m_Criminals = new ValueBinding<int>("policeInfo", "criminals", 0));
		AddBinding(m_CrimePerMonth = new ValueBinding<int>("policeInfo", "crimePerMonth", 0));
		AddBinding(m_EscapedRate = new ValueBinding<float>("policeInfo", "escapedRate", 0f));
		AddBinding(m_AverageCrimeProbability = new GetterValueBinding<IndicatorValue>("policeInfo", "averageCrimeProbability", GetCrimeProbability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_JailAvailability = new GetterValueBinding<IndicatorValue>("policeInfo", "jailAvailability", GetJailAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_PrisonAvailability = new GetterValueBinding<IndicatorValue>("policeInfo", "prisonAvailability", GetPrisonAvailability, new ValueWriter<IndicatorValue>()));
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
		ResetResults();
		JobChunkExtensions.Schedule(new CrimeProducerJob
		{
			m_CrimeProducerHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_CrimeProducerQuery, base.Dependency).Complete();
		JobChunkExtensions.Schedule(new PoliceStationJob
		{
			m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OccupantHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Occupant_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PoliceStationDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PoliceStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgradesFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_PoliceStationQuery, base.Dependency).Complete();
		JobChunkExtensions.Schedule(new PrisonJob
		{
			m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OccupantHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Occupant_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrisonDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrisonData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgradesFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_PrisonQuery, base.Dependency).Complete();
		JobChunkExtensions.Schedule(new CriminalJob
		{
			m_CriminalHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Criminal_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_CriminalQuery, base.Dependency).Complete();
		m_PrisonCapacity.Update((int)m_Results[6]);
		m_Prisoners.Update((int)m_Results[5]);
		m_InPrison.Update((int)m_Results[7]);
		m_JailCapacity.Update((int)m_Results[3]);
		m_ArrestedCriminals.Update((int)m_Results[2]);
		m_InJail.Update((int)m_Results[4]);
		m_CrimeProducers.Update((int)m_Results[0]);
		m_CrimeProbability.Update(m_Results[1]);
		m_Criminals.Update(m_CriminalQuery.CalculateEntityCount());
		m_AverageCrimeProbability.Update();
		m_JailAvailability.Update();
		m_PrisonAvailability.Update();
		m_CrimePerMonth.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.CrimeCount));
		m_EscapedRate.Update((m_CrimePerMonth.value == 0) ? 0f : math.min(100f, (float)m_CityStatisticsSystem.GetStatisticValue(StatisticType.EscapedArrestCount) * 100f / (float)m_CrimePerMonth.value));
	}
```

- `private ResetResults() : System.Void`  

```csharp
private void ResetResults()
	{
		for (int i = 0; i < m_Results.Length; i++)
		{
			m_Results[i] = 0f;
		}
	}
```


## Nested types

- `Game.UI.InGame.PoliceInfoviewUISystem+Result`  
- `Game.UI.InGame.PoliceInfoviewUISystem+PoliceStationJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+PrisonJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+CrimeProducerJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+CriminalJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle`  

