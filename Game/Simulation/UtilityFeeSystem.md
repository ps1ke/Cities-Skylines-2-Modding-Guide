# Game.Simulation.UtilityFeeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UtilityFeeSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Unity.Entities.EntityQuery m_ConsumerGroup;
    private Game.Simulation.UtilityFeeSystem+TypeHandle __TypeHandle;
    private static const System.Int32 kUpdatesPerDay;

    public UtilityFeeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
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

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Unity.Entities.EntityQuery m_ConsumerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerGroup;
```

- `private Game.Simulation.UtilityFeeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.UtilityFeeSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 kUpdatesPerDay`  

```csharp
private static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public UtilityFeeSystem()`  

```csharp
[Preserve]
	public UtilityFeeSystem()
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
		return 128;
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
		m_ServiceFeeSystem = base.World.GetOrCreateSystemManaged<ServiceFeeSystem>();
		m_ConsumerGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Renter>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<ElectricityConsumer>(),
				ComponentType.ReadOnly<WaterConsumer>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, 128, 16);
		JobHandle deps;
		SellUtilitiesJob jobData = new SellUtilitiesJob
		{
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ElectricityConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = GetSharedComponentTypeHandle<UpdateFrame>(),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RW_BufferLookup, ref base.CheckedStateRef),
			m_Fees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_ServiceFee_RO_BufferLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_UpdateFrameIndex = updateFrame,
			m_FeeQueue = m_ServiceFeeSystem.GetFeeQueue(out deps).AsParallelWriter(),
			m_RandomSeed = RandomSeed.Next()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ConsumerGroup, JobHandle.CombineDependencies(base.Dependency, deps));
		m_ServiceFeeSystem.AddQueueWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.UtilityFeeSystem+SellUtilitiesJob`  
- `Game.Simulation.UtilityFeeSystem+TypeHandle`  

