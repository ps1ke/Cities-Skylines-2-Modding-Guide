# Game.Simulation.UpdateGroupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpdateGroupSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes;
    private Game.Simulation.UpdateGroupSystem+UpdateGroupSizes m_UpdateGroupSizes;
    private Game.Simulation.UpdateGroupSystem+TypeHandle __TypeHandle;

    public UpdateGroupSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Simulation.UpdateGroupSystem+UpdateGroupSizes GetUpdateGroupSizes();
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

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes`  

```csharp
private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes;
```

- `private Game.Simulation.UpdateGroupSystem+UpdateGroupSizes m_UpdateGroupSizes`  

```csharp
private Game.Simulation.UpdateGroupSystem+UpdateGroupSizes m_UpdateGroupSizes;
```

- `private Game.Simulation.UpdateGroupSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.UpdateGroupSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public UpdateGroupSystem()`  

```csharp
[Preserve]
	public UpdateGroupSystem()
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

- `public GetUpdateGroupSizes() : Game.Simulation.UpdateGroupSystem+UpdateGroupSizes`  

```csharp
public UpdateGroupSizes GetUpdateGroupSizes()
	{
		return m_UpdateGroupSizes;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_CreatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<UpdateFrame>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_UpdatedQuery = GetEntityQuery(ComponentType.ReadOnly<Updated>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadOnly<Moving>(), ComponentType.Exclude<Created>());
		m_UpdateGroupTypes = new UpdateGroupTypes(this);
		m_UpdateGroupSizes = new UpdateGroupSizes(Allocator.Persistent);
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
		m_UpdateGroupSizes.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_CreatedQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			NativeList<ArchetypeChunk> chunks = m_CreatedQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
			m_UpdateGroupTypes.Update(this);
			UpdateGroupJob jobData = new UpdateGroupJob
			{
				m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AppliedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Applied_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ControllerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LayoutElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
				m_CreatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Created_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabUpdateFrameData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UpdateFrameData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformFrameData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_TransformFrame_RW_BufferLookup, ref base.CheckedStateRef),
				m_Chunks = chunks,
				m_UpdateGroupTypes = m_UpdateGroupTypes,
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer(),
				m_UpdateGroupSizes = m_UpdateGroupSizes
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
			chunks.Dispose(base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		}
		if (!m_UpdatedQuery.IsEmptyIgnoreFilter)
		{
			MovingObjectsUpdatedJob jobData2 = new MovingObjectsUpdatedJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HumanNavigationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_HumanNavigation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
				m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformFrameData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_TransformFrame_RW_BufferLookup, ref base.CheckedStateRef),
				m_SimulationFrame = m_SimulationSystem.frameIndex
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_UpdatedQuery, base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.UpdateGroupSystem+UpdateGroupTypes`  
- `Game.Simulation.UpdateGroupSystem+UpdateGroupSizes`  
- `Game.Simulation.UpdateGroupSystem+UpdateGroupJob`  
- `Game.Simulation.UpdateGroupSystem+MovingObjectsUpdatedJob`  
- `Game.Simulation.UpdateGroupSystem+TypeHandle`  

