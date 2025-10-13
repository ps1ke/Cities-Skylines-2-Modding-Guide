# Game.Simulation.PayWageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PayWageSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Unity.Entities.EntityQuery m_EconomyParameterGroup;
    private Unity.Entities.EntityQuery m_HouseholdGroup;
    private Unity.Collections.NativeQueue<Game.Simulation.PayWageSystem+Payment> m_PaymentQueue;
    private Game.Simulation.PayWageSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public PayWageSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterGroup;
```

- `private Unity.Entities.EntityQuery m_HouseholdGroup`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdGroup;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.PayWageSystem+Payment> m_PaymentQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.PayWageSystem+Payment> m_PaymentQueue;
```

- `private Game.Simulation.PayWageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PayWageSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public PayWageSystem()`  

```csharp
[Preserve]
	public PayWageSystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_PaymentQueue = new NativeQueue<Payment>(Allocator.Persistent);
		m_EconomyParameterGroup = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_HouseholdGroup = GetEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_EconomyParameterGroup);
		RequireForUpdate(m_HouseholdGroup);
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
		m_PaymentQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new PayWageJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizenType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ResourcesType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_TaxPayerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_TaxPayer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CommuterHouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CommuterHousehold_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = GetSharedComponentTypeHandle<UpdateFrame>(),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Companies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EmployeeBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyParameters = m_EconomyParameterGroup.GetSingleton<EconomyParameterData>(),
			m_UpdateFrameIndex = updateFrame,
			m_PaymentQueue = m_PaymentQueue.AsParallelWriter(),
			m_TaxRates = m_TaxSystem.GetTaxRates()
		}, m_HouseholdGroup, base.Dependency);
		m_TaxSystem.AddReader(jobHandle);
		PayJob jobData = new PayJob
		{
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RW_BufferLookup, ref base.CheckedStateRef),
			m_PaymentQueue = m_PaymentQueue
		};
		base.Dependency = IJobExtensions.Schedule(jobData, jobHandle);
	}
```


## Nested types

- `Game.Simulation.PayWageSystem+Payment`  
- `Game.Simulation.PayWageSystem+PayJob`  
- `Game.Simulation.PayWageSystem+PayWageJob`  
- `Game.Simulation.PayWageSystem+TypeHandle`  

