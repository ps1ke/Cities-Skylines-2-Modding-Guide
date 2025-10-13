# Game.Net.NodeAlignSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NodeAlignSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NodeQuery;
    private Game.Net.NodeAlignSystem+TypeHandle __TypeHandle;

    public NodeAlignSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeQuery;
```

- `private Game.Net.NodeAlignSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.NodeAlignSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NodeAlignSystem()`  

```csharp
[Preserve]
	public NodeAlignSystem()
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
		m_NodeQuery = GetEntityQuery(ComponentType.ReadOnly<Node>(), ComponentType.ReadOnly<Updated>());
		RequireForUpdate(m_NodeQuery);
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
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new UpdateNodeRotationsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_StandaloneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Standalone_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef)
		}, m_NodeQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Net.NodeAlignSystem+UpdateNodeRotationsJob`  
- `Game.Net.NodeAlignSystem+LineComparer`  
- `Game.Net.NodeAlignSystem+TypeHandle`  

