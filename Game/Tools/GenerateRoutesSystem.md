# Game.Tools.GenerateRoutesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateRoutesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_SubElementQuery;
    private Game.Tools.GenerateRoutesSystem+TypeHandle __TypeHandle;

    public GenerateRoutesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_SubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubElementQuery;
```

- `private Game.Tools.GenerateRoutesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateRoutesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateRoutesSystem()`  

```csharp
[Preserve]
	public GenerateRoutesSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier2>();
		m_DefinitionQuery = GetEntityQuery(ComponentType.ReadOnly<CreationDefinition>(), ComponentType.ReadOnly<WaypointDefinition>(), ComponentType.ReadOnly<Updated>());
		m_SubElementQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Updated>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Waypoint>(),
				ComponentType.ReadOnly<Segment>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		RequireForUpdate(m_DefinitionQuery);
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
		NativeList<ArchetypeChunk> subElementChunks = m_SubElementQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new CreateRoutesJob
		{
			m_SubElementChunks = subElementChunks,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaypointType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SegmentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaypointDefinitionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_WaypointDefinition_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ColorDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_ColorDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Color_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_DefinitionQuery, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
		subElementChunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Tools.GenerateRoutesSystem+CreateRoutesJob`  
- `Game.Tools.GenerateRoutesSystem+TypeHandle`  

