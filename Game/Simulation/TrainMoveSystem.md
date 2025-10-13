# Game.Simulation.TrainMoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrainMoveSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_TrainQuery;
    private Unity.Entities.EntityQuery m_LayoutQuery;
    private Game.Simulation.TrainMoveSystem+TypeHandle __TypeHandle;

    public TrainMoveSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_TrainQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrainQuery;
```

- `private Unity.Entities.EntityQuery m_LayoutQuery`  

```csharp
private Unity.Entities.EntityQuery m_LayoutQuery;
```

- `private Game.Simulation.TrainMoveSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrainMoveSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TrainMoveSystem()`  

```csharp
[Preserve]
	public TrainMoveSystem()
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
		return 16;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 3;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_LightingSystem = base.World.GetOrCreateSystemManaged<LightingSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_TrainQuery = GetEntityQuery(ComponentType.ReadOnly<Train>(), ComponentType.ReadOnly<TrainNavigation>(), ComponentType.ReadWrite<Transform>(), ComponentType.ReadWrite<Moving>(), ComponentType.ReadWrite<TransformFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<TripSource>());
		m_LayoutQuery = GetEntityQuery(ComponentType.ReadOnly<Train>(), ComponentType.ReadOnly<TrainNavigation>(), ComponentType.ReadOnly<LayoutElement>(), ComponentType.ReadWrite<TransformFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<TripSource>());
		RequireForUpdate(m_TrainQuery);
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
		uint transformFrameIndex = m_SimulationSystem.frameIndex / 16 % 4;
		UpdateTransformDataJob jobData = new UpdateTransformDataJob
		{
			m_TrainType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NavigationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainNavigation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MovingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Moving_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_TransformFrame_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_BogieFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainBogieFrame_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrainData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformFrameIndex = transformFrameIndex
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateLayoutDataJob
		{
			m_PseudoRandomSeedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LayoutElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformFrames = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_TransformFrame_RW_BufferLookup, ref base.CheckedStateRef),
			m_TransformFrameIndex = transformFrameIndex,
			m_DayLightBrightness = m_LightingSystem.dayLightBrightness,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, dependsOn: JobChunkExtensions.ScheduleParallel(jobData, m_TrainQuery, base.Dependency), query: m_LayoutQuery);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.TrainMoveSystem+UpdateTransformDataJob`  
- `Game.Simulation.TrainMoveSystem+UpdateLayoutDataJob`  
- `Game.Simulation.TrainMoveSystem+TypeHandle`  

