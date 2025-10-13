# Game.Tools.NodeReductionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NodeReductionSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_TempNodeQuery;
    private Game.Tools.NodeReductionSystem+TypeHandle __TypeHandle;

    public NodeReductionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_TempNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempNodeQuery;
```

- `private Game.Tools.NodeReductionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.NodeReductionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NodeReductionSystem()`  

```csharp
[Preserve]
	public NodeReductionSystem()
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
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_TempNodeQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Node>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Fixed>());
		RequireForUpdate(m_TempNodeQuery);
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
		NativeQueue<ReductionData> reductionQueue = new NativeQueue<ReductionData>(Allocator.TempJob);
		FindCandidatesJob jobData = new FindCandidatesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerDefinitionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_OwnerDefinition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FixedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Fixed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_ReductionQueue = reductionQueue.AsParallelWriter()
		};
		NodeReductionJob jobData2 = new NodeReductionJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LocalConnectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RW_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RW_ComponentLookup, ref base.CheckedStateRef),
			m_BuildOrderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_BuildOrder_RW_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RW_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RW_BufferLookup, ref base.CheckedStateRef),
			m_ReductionQueue = reductionQueue
		};
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(jobData, m_TempNodeQuery, base.Dependency);
		JobHandle jobHandle = IJobExtensions.Schedule(jobData2, dependsOn);
		reductionQueue.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Tools.NodeReductionSystem+FindCandidatesJob`  
- `Game.Tools.NodeReductionSystem+ReductionData`  
- `Game.Tools.NodeReductionSystem+NodeReductionJob`  
- `Game.Tools.NodeReductionSystem+TypeHandle`  

