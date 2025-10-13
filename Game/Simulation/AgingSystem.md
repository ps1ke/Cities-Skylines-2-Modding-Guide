# Game.Simulation.AgingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AgingSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    public Colossal.Collections.NativeValue<System.Int32> m_BecomeTeen;
    public Colossal.Collections.NativeValue<System.Int32> m_BecomeAdult;
    public Colossal.Collections.NativeValue<System.Int32> m_BecomeElder;
    public Colossal.NativeCounter m_BecomeTeenCounter;
    public Colossal.NativeCounter m_BecomeAdultCounter;
    public Colossal.NativeCounter m_BecomeElderCounter;
    private Game.Simulation.AgingSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static System.Boolean s_DebugAgeAllCitizens;

    public AgingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetAdultAgeLimitInDays();
    public static System.Int32 GetElderAgeLimitInDays();
    public static System.Int32 GetTeenAgeLimitInDays();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `public Colossal.Collections.NativeValue<System.Int32> m_BecomeTeen`  

```csharp
public Colossal.Collections.NativeValue<System.Int32> m_BecomeTeen;
```

- `public Colossal.Collections.NativeValue<System.Int32> m_BecomeAdult`  

```csharp
public Colossal.Collections.NativeValue<System.Int32> m_BecomeAdult;
```

- `public Colossal.Collections.NativeValue<System.Int32> m_BecomeElder`  

```csharp
public Colossal.Collections.NativeValue<System.Int32> m_BecomeElder;
```

- `public Colossal.NativeCounter m_BecomeTeenCounter`  

```csharp
public Colossal.NativeCounter m_BecomeTeenCounter;
```

- `public Colossal.NativeCounter m_BecomeAdultCounter`  

```csharp
public Colossal.NativeCounter m_BecomeAdultCounter;
```

- `public Colossal.NativeCounter m_BecomeElderCounter`  

```csharp
public Colossal.NativeCounter m_BecomeElderCounter;
```

- `private Game.Simulation.AgingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AgingSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static System.Boolean s_DebugAgeAllCitizens`  

```csharp
public static System.Boolean s_DebugAgeAllCitizens;
```


## Constructors

- `public AgingSystem()`  

```csharp
[Preserve]
	public AgingSystem()
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

- `public static GetAdultAgeLimitInDays() : System.Int32`  

```csharp
public static int GetAdultAgeLimitInDays()
	{
		return 36;
	}
```

- `public static GetElderAgeLimitInDays() : System.Int32`  

```csharp
public static int GetElderAgeLimitInDays()
	{
		return 84;
	}
```

- `public static GetTeenAgeLimitInDays() : System.Int32`  

```csharp
public static int GetTeenAgeLimitInDays()
	{
		return 21;
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
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_HouseholdQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Household>() },
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_BecomeTeen = new NativeValue<int>(Allocator.Persistent);
		m_BecomeAdult = new NativeValue<int>(Allocator.Persistent);
		m_BecomeElder = new NativeValue<int>(Allocator.Persistent);
		m_BecomeTeenCounter = new NativeCounter(Allocator.Persistent);
		m_BecomeAdultCounter = new NativeCounter(Allocator.Persistent);
		m_BecomeElderCounter = new NativeCounter(Allocator.Persistent);
		RequireForUpdate(m_HouseholdQuery);
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
		base.OnDestroy();
		m_BecomeTeen.Dispose();
		m_BecomeAdult.Dispose();
		m_BecomeElder.Dispose();
		m_BecomeTeenCounter.Dispose();
		m_BecomeAdultCounter.Dispose();
		m_BecomeElderCounter.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		AgingJob jobData = new AgingJob
		{
			m_BecomeTeenCounter = m_BecomeTeenCounter.ToConcurrent(),
			m_BecomeAdultCounter = m_BecomeAdultCounter.ToConcurrent(),
			m_BecomeElderCounter = m_BecomeElderCounter.ToConcurrent(),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizenType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TravelPurposes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentLookup, ref base.CheckedStateRef),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>(),
			m_UpdateFrameIndex = updateFrame,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_DebugAgeAllCitizens = s_DebugAgeAllCitizens
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_HouseholdQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.AgingSystem+AgingJob`  
- `Game.Simulation.AgingSystem+TypeHandle`  

