# Game.UI.InGame.RoadsInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoadsInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_ParkingCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkedCars;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkingIncome;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ParkingAvailability;
    private Unity.Entities.EntityQuery m_ParkingFacilityQuery;
    private Unity.Entities.EntityQuery m_ParkingFacilityModifiedQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public RoadsInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
    private System.Void UpdateAvailability();
    private System.Void UpdateCapacity();
    private System.Void UpdateIncome();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ParkingCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_ParkingCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkedCars`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkedCars;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkingIncome`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkingIncome;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ParkingAvailability`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ParkingAvailability;
```

- `private Unity.Entities.EntityQuery m_ParkingFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkingFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_ParkingFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkingFacilityModifiedQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public RoadsInfoviewUISystem()`  

```csharp
[Preserve]
	public RoadsInfoviewUISystem()
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
		m_ParkingFacilityQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Buildings.ParkingFacility>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Net.SubLane>(),
				ComponentType.ReadOnly<Game.Net.SubNet>(),
				ComponentType.ReadOnly<Game.Objects.SubObject>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_ParkingFacilityModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Buildings.ParkingFacility>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		AddBinding(m_ParkingCapacity = new ValueBinding<float>("roadsInfo", "parkingCapacity", 0f));
		AddBinding(m_ParkedCars = new ValueBinding<int>("roadsInfo", "parkedCars", 0));
		AddBinding(m_ParkingIncome = new ValueBinding<int>("roadsInfo", "parkingIncome", 0));
		AddBinding(m_ParkingAvailability = new ValueBinding<IndicatorValue>("roadsInfo", "parkingAvailability", default(IndicatorValue), new ValueWriter<IndicatorValue>()));
		m_Results = new NativeArray<int>(2, Allocator.Persistent);
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
		UpdateCapacity();
		UpdateAvailability();
		UpdateIncome();
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

- `private UpdateAvailability() : System.Void`  

```csharp
private void UpdateAvailability()
	{
		m_ParkingAvailability.Update(IndicatorValue.Calculate(m_ParkingCapacity.value, m_ParkedCars.value));
	}
```

- `private UpdateCapacity() : System.Void`  

```csharp
private void UpdateCapacity()
	{
		ResetResults();
		JobChunkExtensions.Schedule(new UpdateParkingJob
		{
			m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_SubNetHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubNet_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubLaneHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubObjectHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CurveFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingLaneFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarageLaneFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_GarageLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingLaneDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubLaneFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjectFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneObjectFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_ParkingFacilityQuery, base.Dependency).Complete();
		m_ParkingCapacity.Update(m_Results[0]);
		m_ParkedCars.Update(m_Results[1]);
	}
```

- `private UpdateIncome() : System.Void`  

```csharp
private void UpdateIncome()
	{
		m_ParkingIncome.Update(m_CityStatisticsSystem.GetStatisticValue(StatisticType.Income, 9));
	}
```


## Nested types

- `Game.UI.InGame.RoadsInfoviewUISystem+Result`  
- `Game.UI.InGame.RoadsInfoviewUISystem+UpdateParkingJob`  
- `Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle`  

