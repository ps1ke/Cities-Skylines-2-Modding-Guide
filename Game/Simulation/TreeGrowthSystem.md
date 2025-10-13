# Game.Simulation.TreeGrowthSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TreeGrowthSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_TreeQuery;
    private Game.Simulation.TreeGrowthSystem+TypeHandle __TypeHandle;
    public static const System.Int32 UPDATES_PER_DAY;
    public static const System.Int32 TICK_SPEED_CHILD;
    public static const System.Int32 TICK_SPEED_TEEN;
    public static const System.Int32 TICK_SPEED_ADULT;
    public static const System.Int32 TICK_SPEED_ELDERLY;
    public static const System.Int32 TICK_SPEED_DEAD;

    public TreeGrowthSystem();

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

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_TreeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TreeQuery;
```

- `private Game.Simulation.TreeGrowthSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TreeGrowthSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 UPDATES_PER_DAY`  

```csharp
public static const System.Int32 UPDATES_PER_DAY;
```

- `public static const System.Int32 TICK_SPEED_CHILD`  

```csharp
public static const System.Int32 TICK_SPEED_CHILD;
```

- `public static const System.Int32 TICK_SPEED_TEEN`  

```csharp
public static const System.Int32 TICK_SPEED_TEEN;
```

- `public static const System.Int32 TICK_SPEED_ADULT`  

```csharp
public static const System.Int32 TICK_SPEED_ADULT;
```

- `public static const System.Int32 TICK_SPEED_ELDERLY`  

```csharp
public static const System.Int32 TICK_SPEED_ELDERLY;
```

- `public static const System.Int32 TICK_SPEED_DEAD`  

```csharp
public static const System.Int32 TICK_SPEED_DEAD;
```


## Constructors

- `public TreeGrowthSystem()`  

```csharp
[Preserve]
	public TreeGrowthSystem()
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
		return 512;
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
		m_TreeQuery = GetEntityQuery(ComponentType.ReadWrite<Tree>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Overridden>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_TreeQuery);
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, 32, 16);
		m_TreeQuery.ResetFilter();
		m_TreeQuery.SetSharedComponentFilter(new UpdateFrame(updateFrame));
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new TreeGrowthJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TreeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Tree_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DamagedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Damaged_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_TreeQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.TreeGrowthSystem+TreeGrowthJob`  
- `Game.Simulation.TreeGrowthSystem+TypeHandle`  

