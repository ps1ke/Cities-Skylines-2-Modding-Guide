# Game.Simulation.VehicleOutOfControlSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehicleOutOfControlSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Simulation.VehicleOutOfControlSystem+TypeHandle __TypeHandle;

    public VehicleOutOfControlSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Simulation.VehicleOutOfControlSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.VehicleOutOfControlSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public VehicleOutOfControlSystem()`  

```csharp
[Preserve]
	public VehicleOutOfControlSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_VehicleQuery = GetEntityQuery(ComponentType.ReadOnly<OutOfControl>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<Transform>(), ComponentType.ReadWrite<Moving>(), ComponentType.ReadWrite<TransformFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<TripSource>());
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
		uint index = m_SimulationSystem.frameIndex & 0xF;
		m_VehicleQuery.ResetFilter();
		m_VehicleQuery.SetSharedComponentFilter(new UpdateFrame(index));
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new VehicleOutOfControlMoveJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MovingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Moving_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_TransformFrame_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OrphanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_TransformFrameIndex = m_SimulationSystem.frameIndex / 16 % 4
		}, m_VehicleQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.VehicleOutOfControlSystem+VehicleOutOfControlMoveJob`  
- `Game.Simulation.VehicleOutOfControlSystem+TypeHandle`  

