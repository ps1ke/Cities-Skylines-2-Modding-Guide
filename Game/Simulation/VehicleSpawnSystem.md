# Game.Simulation.VehicleSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehicleSpawnSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Simulation.VehicleSpawnSystem+TypeHandle __TypeHandle;

    public VehicleSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Simulation.VehicleSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.VehicleSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public VehicleSpawnSystem()`  

```csharp
[Preserve]
	public VehicleSpawnSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_VehicleQuery = GetEntityQuery(ComponentType.ReadWrite<TripSource>(), ComponentType.ReadOnly<Vehicle>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_VehicleQuery);
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
		NativeList<SpawnData> spawnData = new NativeList<SpawnData>(Allocator.TempJob);
		NativeList<SpawnRange> nativeList = new NativeList<SpawnRange>(Allocator.TempJob);
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_VehicleQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		GroupSpawnSourcesJob jobData = new GroupSpawnSourcesJob
		{
			m_Chunks = chunks,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ControllerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpawnSourceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_TripSource_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpawnData = spawnData,
			m_SpawnGroups = nativeList
		};
		JobHandle jobHandle = new TrySpawnVehiclesJob
		{
			m_SpawnData = spawnData.AsDeferredJobArray(),
			m_SpawnGroups = nativeList.AsDeferredJobArray(),
			m_TrainCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Layouts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}.Schedule(dependsOn: IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle)), list: nativeList, innerloopBatchCount: 1);
		spawnData.Dispose(jobHandle);
		nativeList.Dispose(jobHandle);
		chunks.Dispose(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.VehicleSpawnSystem+SpawnData`  
- `Game.Simulation.VehicleSpawnSystem+SpawnRange`  
- `Game.Simulation.VehicleSpawnSystem+GroupSpawnSourcesJob`  
- `Game.Simulation.VehicleSpawnSystem+LaneBufferItem`  
- `Game.Simulation.VehicleSpawnSystem+TrySpawnVehiclesJob`  
- `Game.Simulation.VehicleSpawnSystem+TypeHandle`  

