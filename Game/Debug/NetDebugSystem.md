# Game.Debug.NetDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_NetGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_NodeOption;
    private Game.Debug.BaseDebugSystem+Option m_EdgeOption;
    private Game.Debug.BaseDebugSystem+Option m_OutlineOption;
    private Game.Debug.NetDebugSystem+TypeHandle __TypeHandle;

    public NetDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NetGroup`  

```csharp
private Unity.Entities.EntityQuery m_NetGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_NodeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_NodeOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_EdgeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_EdgeOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_OutlineOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_OutlineOption;
```

- `private Game.Debug.NetDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.NetDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetDebugSystem()`  

```csharp
[Preserve]
	public NetDebugSystem()
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
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_NetGroup = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Node>(),
				ComponentType.ReadOnly<Edge>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Hidden>()
			}
		});
		m_NodeOption = AddOption("Draw Nodes", defaultEnabled: true);
		m_EdgeOption = AddOption("Draw Edges", defaultEnabled: true);
		m_OutlineOption = AddOption("Draw Outlines", defaultEnabled: true);
		RequireForUpdate(m_NetGroup);
		base.Enabled = false;
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

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new NetGizmoJob
		{
			m_NodeOption = m_NodeOption.enabled,
			m_EdgeOption = m_EdgeOption.enabled,
			m_OutlineOption = m_OutlineOption.enabled,
			m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StartGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EndGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectedNodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
		}, m_NetGroup, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.NetDebugSystem+NetGizmoJob`  
- `Game.Debug.NetDebugSystem+TypeHandle`  

