# Game.Simulation.ResourceFlowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceFlowSystem : Game.GameSystemBase
{
    private Game.Simulation.ExtractorCompanySystem m_ExtractorCompanySystem;
    private Unity.Entities.EntityQuery m_NetQuery;
    private Game.Simulation.ResourceFlowSystem+TypeHandle __TypeHandle;

    public ResourceFlowSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ExtractorCompanySystem m_ExtractorCompanySystem`  

```csharp
private Game.Simulation.ExtractorCompanySystem m_ExtractorCompanySystem;
```

- `private Unity.Entities.EntityQuery m_NetQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetQuery;
```

- `private Game.Simulation.ResourceFlowSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResourceFlowSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResourceFlowSystem()`  

```csharp
[Preserve]
	public ResourceFlowSystem()
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
		return 262144 / EconomyUtils.kCompanyUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ExtractorCompanySystem = base.World.GetExistingSystemManaged<ExtractorCompanySystem>();
		m_NetQuery = GetEntityQuery(ComponentType.ReadWrite<ResourceConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_NetQuery);
		Assert.AreEqual(GetUpdateInterval(SystemUpdatePhase.GameSimulation), m_ExtractorCompanySystem.GetUpdateInterval(SystemUpdatePhase.GameSimulation) * 16);
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
		ResourceFlowJob jobData = new ResourceFlowJob
		{
			m_Chunks = m_NetQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Object_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceUpgradeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourceConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ResourceConnection_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResourceConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ResourceConnection_RW_ComponentLookup, ref base.CheckedStateRef)
		};
		JobHandle jobHandle = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		jobData.m_Chunks.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.ResourceFlowSystem+SourceNodeData`  
- `Game.Simulation.ResourceFlowSystem+TargetDirectionData`  
- `Game.Simulation.ResourceFlowSystem+ResourceNodeItem`  
- `Game.Simulation.ResourceFlowSystem+ResourceFlowJob`  
- `Game.Simulation.ResourceFlowSystem+TypeHandle`  

