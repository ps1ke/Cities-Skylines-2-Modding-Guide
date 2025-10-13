# Game.UI.InGame.PostInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PostInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_PostFacilityModifiedQuery;
    private Unity.Entities.EntityQuery m_MailProducerQuery;
    private Unity.Entities.EntityQuery m_MailProducerModifiedQuery;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollectedMail;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeliveredMail;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_MailProductionRate;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_PostServiceAvailability;
    private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_Result;
    private Game.UI.InGame.PostInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;
    private static const System.Single kAccumulationFactor;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public PostInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
    private System.Void UpdateAvailability();
    private System.Void UpdateMailRate();
    private System.Void UpdateProcessingRate();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_PostFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostFacilityModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_MailProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_MailProducerQuery;
```

- `private Unity.Entities.EntityQuery m_MailProducerModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_MailProducerModifiedQuery;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollectedMail`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollectedMail;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeliveredMail`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeliveredMail;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_MailProductionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_MailProductionRate;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_PostServiceAvailability`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_PostServiceAvailability;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_Result`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_Result;
```

- `private Game.UI.InGame.PostInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PostInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `private static const System.Single kAccumulationFactor`  

```csharp
private static const System.Single kAccumulationFactor;
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

- `public PostInfoviewUISystem()`  

```csharp
[Preserve]
	public PostInfoviewUISystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_PostFacilityModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Buildings.PostFacility>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Created>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_MailProducerQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<MailProducer>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_MailProducerModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<MailProducer>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Created>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		AddBinding(m_CollectedMail = new ValueBinding<int>("postInfo", "collectedMail", 0));
		AddBinding(m_DeliveredMail = new ValueBinding<int>("postInfo", "deliveredMail", 0));
		AddBinding(m_MailProductionRate = new ValueBinding<float>("postInfo", "mailProductionRate", 0f));
		AddBinding(m_PostServiceAvailability = new ValueBinding<IndicatorValue>("postInfo", "postServiceAvailability", default(IndicatorValue), new ValueWriter<IndicatorValue>()));
		m_Result = new NativeArray<float2>(1, Allocator.Persistent);
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
		m_Result.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		UpdateMailRate();
		UpdateProcessingRate();
		UpdateAvailability();
	}
```

- `private ResetResults() : System.Void`  

```csharp
private void ResetResults()
	{
		for (int i = 0; i < m_Result.Length; i++)
		{
			m_Result[i] = default(float2);
		}
	}
```

- `private UpdateAvailability() : System.Void`  

```csharp
private void UpdateAvailability()
	{
		m_PostServiceAvailability.Update(IndicatorValue.Calculate(m_DeliveredMail.value + m_CollectedMail.value, m_MailProductionRate.value));
	}
```

- `private UpdateMailRate() : System.Void`  

```csharp
private void UpdateMailRate()
	{
		ResetResults();
		JobChunkExtensions.Schedule(new UpdateMailRateJob
		{
			m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceObjectFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MailAccumulationFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MailAccumulationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RenterFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_EmployeeFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizenFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_Result = m_Result
		}, m_MailProducerQuery, base.Dependency).Complete();
		float2 @float = m_Result[0] * 72.81778f;
		m_MailProductionRate.Update(@float.x + @float.y);
	}
```

- `private UpdateProcessingRate() : System.Void`  

```csharp
private void UpdateProcessingRate()
	{
		m_DeliveredMail.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.DeliveredMail));
		m_CollectedMail.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.CollectedMail));
	}
```


## Nested types

- `Game.UI.InGame.PostInfoviewUISystem+UpdateMailRateJob`  
- `Game.UI.InGame.PostInfoviewUISystem+TypeHandle`  

