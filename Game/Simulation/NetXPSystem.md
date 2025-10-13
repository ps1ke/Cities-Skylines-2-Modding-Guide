# Game.Simulation.NetXPSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetXPSystem : Game.GameSystemBase
{
    private Game.Simulation.XPSystem m_XPSystem;
    private Unity.Entities.EntityQuery m_CreatedNetQuery;
    private Unity.Entities.EntityQuery m_DeletedNetQuery;
    private Game.Simulation.NetXPSystem+TypeHandle __TypeHandle;
    private static readonly System.Single kXPRewardLength;

    public NetXPSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.XPSystem m_XPSystem`  

```csharp
private Game.Simulation.XPSystem m_XPSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedNetQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedNetQuery;
```

- `private Game.Simulation.NetXPSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.NetXPSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single kXPRewardLength`  

```csharp
private static readonly System.Single kXPRewardLength;
```


## Constructors

- `public NetXPSystem()`  

```csharp
[Preserve]
	public NetXPSystem()
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
		m_CreatedNetQuery = GetEntityQuery(ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Curve>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_DeletedNetQuery = GetEntityQuery(ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Curve>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Created>(), ComponentType.Exclude<Temp>());
		m_XPSystem = base.World.GetOrCreateSystemManaged<XPSystem>();
		RequireForUpdate(m_CreatedNetQuery);
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
		NativeList<Entity> nativeList = m_CreatedNetQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle outJobHandle2;
		NativeList<Entity> nativeList2 = m_DeletedNetQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle2);
		JobHandle deps;
		NetXPJob jobData = new NetXPJob
		{
			m_PlaceableNetDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Elevations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RW_ComponentLookup, ref base.CheckedStateRef),
			m_RoadDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TrackDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackData_RW_ComponentLookup, ref base.CheckedStateRef),
			m_WaterwayDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterwayData_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PipelineDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PipelineData_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PowerLineDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PowerLineData_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Curves = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CreatedEntities = nativeList.AsDeferredJobArray(),
			m_DeletedEntities = nativeList2.AsDeferredJobArray(),
			m_XPQueue = m_XPSystem.GetQueue(out deps)
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(outJobHandle, outJobHandle2, JobHandle.CombineDependencies(deps, base.Dependency)));
		m_XPSystem.AddQueueWriter(base.Dependency);
		nativeList.Dispose(base.Dependency);
		nativeList2.Dispose(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.NetXPSystem+NetXPJob`  
- `Game.Simulation.NetXPSystem+NetXPs`  
- `Game.Simulation.NetXPSystem+TypeHandle`  

