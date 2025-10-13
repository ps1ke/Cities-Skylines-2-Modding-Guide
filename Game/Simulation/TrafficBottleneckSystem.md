# Game.Simulation.TrafficBottleneckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficBottleneckSystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_BlockerQuery;
    private Unity.Entities.EntityQuery m_BottleneckQuery;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Game.Simulation.TrafficBottleneckSystem+TypeHandle __TypeHandle;

    public TrafficBottleneckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_BlockerQuery`  

```csharp
private Unity.Entities.EntityQuery m_BlockerQuery;
```

- `private Unity.Entities.EntityQuery m_BottleneckQuery`  

```csharp
private Unity.Entities.EntityQuery m_BottleneckQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Game.Simulation.TrafficBottleneckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrafficBottleneckSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TrafficBottleneckSystem()`  

```csharp
[Preserve]
	public TrafficBottleneckSystem()
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
		return 64;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_BlockerQuery = GetEntityQuery(ComponentType.ReadOnly<Blocker>(), ComponentType.ReadOnly<Vehicle>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_BottleneckQuery = GetEntityQuery(ComponentType.ReadOnly<Bottleneck>(), ComponentType.Exclude<Deleted>());
		m_ConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<TrafficConfigurationData>());
		RequireAnyForUpdate(m_BlockerQuery, m_BottleneckQuery);
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> blockerChunks = m_BlockerQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle outJobHandle2;
		NativeList<ArchetypeChunk> bottleneckChunks = m_BottleneckQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2);
		JobHandle jobHandle = IJobExtensions.Schedule(new TrafficBottleneckJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BlockerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Blocker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BottleneckType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Bottleneck_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BlockerChunks = blockerChunks,
			m_BottleneckChunks = bottleneckChunks,
			m_TrafficConfigurationData = m_ConfigurationQuery.GetSingleton<TrafficConfigurationData>(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_EntityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer(),
			m_TriggerActionQueue = m_TriggerSystem.CreateActionBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle, outJobHandle2));
		blockerChunks.Dispose(jobHandle);
		bottleneckChunks.Dispose(jobHandle);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.TrafficBottleneckSystem+GroupData`  
- `Game.Simulation.TrafficBottleneckSystem+BottleneckData`  
- `Game.Simulation.TrafficBottleneckSystem+BottleneckState`  
- `Game.Simulation.TrafficBottleneckSystem+TrafficBottleneckJob`  
- `Game.Simulation.TrafficBottleneckSystem+TypeHandle`  

