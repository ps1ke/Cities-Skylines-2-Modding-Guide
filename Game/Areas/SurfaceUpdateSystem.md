# Game.Areas.SurfaceUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SurfaceUpdateSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Unity.Entities.EntityQuery m_UpdatedNetQuery;
    private Game.Areas.SurfaceUpdateSystem+TypeHandle __TypeHandle;

    public SurfaceUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedNetQuery;
```

- `private Game.Areas.SurfaceUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.SurfaceUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SurfaceUpdateSystem()`  

```csharp
[Preserve]
	public SurfaceUpdateSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_UpdatedNetQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Net.Node>(),
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		RequireForUpdate(m_UpdatedNetQuery);
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
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateAreasJob
		{
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SurfaceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Surface_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_UpdatedNetQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Areas.SurfaceUpdateSystem+UpdateAreasJob`  
- `Game.Areas.SurfaceUpdateSystem+TypeHandle`  

