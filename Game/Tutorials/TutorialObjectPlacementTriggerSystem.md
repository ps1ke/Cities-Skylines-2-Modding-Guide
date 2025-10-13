# Game.Tutorials.TutorialObjectPlacementTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialObjectPlacementTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_CreatedObjectQuery;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Tutorials.TutorialObjectPlacementTriggerSystem+TypeHandle __TypeHandle;

    public TutorialObjectPlacementTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean HasElevation();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedObjectQuery;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Tutorials.TutorialObjectPlacementTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialObjectPlacementTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialObjectPlacementTriggerSystem()`  

```csharp
[Preserve]
	public TutorialObjectPlacementTriggerSystem()
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

- `private HasElevation() : System.Boolean`  

```csharp
private bool HasElevation()
	{
		if (m_ToolSystem.activeTool == m_NetToolSystem)
		{
			return math.abs(m_NetToolSystem.elevation) > 0.0001f;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ActiveTriggerQuery = GetEntityQuery(ComponentType.ReadOnly<ObjectPlacementTriggerData>(), ComponentType.ReadOnly<TriggerActive>(), ComponentType.ReadWrite<ObjectPlacementTriggerCountData>(), ComponentType.Exclude<TriggerCompleted>());
		m_CreatedObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<Created>()
			},
			Any = new ComponentType[10]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadOnly<Game.Net.WaterPipeConnection>(),
				ComponentType.ReadOnly<Game.Net.ElectricityConnection>(),
				ComponentType.ReadOnly<Game.Prefabs.ResourceConnection>(),
				ComponentType.ReadOnly<Game.Routes.TransportStop>(),
				ComponentType.ReadOnly<Route>(),
				ComponentType.ReadOnly<Tree>(),
				ComponentType.ReadOnly<Waterway>(),
				ComponentType.ReadOnly<ServiceUpgradeBuilding>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Native>()
			}
		});
		m_ObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PrefabRef>() },
			Any = new ComponentType[10]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadOnly<Game.Net.WaterPipeConnection>(),
				ComponentType.ReadOnly<Game.Net.ElectricityConnection>(),
				ComponentType.ReadOnly<Game.Net.ResourceConnection>(),
				ComponentType.ReadOnly<Game.Routes.TransportStop>(),
				ComponentType.ReadOnly<Route>(),
				ComponentType.ReadOnly<Tree>(),
				ComponentType.ReadOnly<Waterway>(),
				ComponentType.ReadOnly<ServiceUpgradeBuilding>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Native>()
			}
		});
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_NetToolSystem = base.World.GetOrCreateSystemManaged<NetToolSystem>();
		RequireForUpdate(m_ActiveTriggerQuery);
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
		base.OnUpdate();
		if (base.triggersChanged)
		{
			ClearCountJob jobData = new ClearCountJob
			{
				m_CountType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tutorials_ObjectPlacementTriggerCountData_RW_ComponentTypeHandle, ref base.CheckedStateRef)
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ActiveTriggerQuery, base.Dependency);
			JobHandle outJobHandle;
			CheckObjectsJob jobData2 = new CheckObjectsJob
			{
				m_CreatedObjectChunks = m_ObjectQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
				m_Natives = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ElectricityConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ElectricityConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WaterPipeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_WaterPipeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterPipeConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_WaterPipeConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ResourceConnection = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ResourceConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ResourceConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SewageOutlets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_SewageOutlet_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Transformers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Transformer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Placeholder = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Placeholder_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TriggerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_ObjectPlacementTriggerData_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_CountType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tutorials_ObjectPlacementTriggerCountData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CommandBuffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter(),
				m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_ForcedUnlockDataFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ForceUIGroupUnlockData_RO_BufferLookup, ref base.CheckedStateRef),
				m_UnlockRequirementFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_UnlockRequirement_RO_BufferLookup, ref base.CheckedStateRef),
				m_Roads = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Edges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UnlockEventArchetype = m_UnlockEventArchetype,
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_HasElevation = HasElevation(),
				m_FirstTimeCheck = true
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_ActiveTriggerQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
			jobData2.m_CreatedObjectChunks.Dispose(base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
		else if (!m_CreatedObjectQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle2;
			CheckObjectsJob jobData3 = new CheckObjectsJob
			{
				m_CreatedObjectChunks = m_CreatedObjectQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2),
				m_Natives = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ElectricityConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ElectricityConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WaterPipeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_WaterPipeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterPipeConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_WaterPipeConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ResourceConnection = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ResourceConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ResourceConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SewageOutlets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_SewageOutlet_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Transformers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Transformer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Placeholder = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Placeholder_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TriggerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_ObjectPlacementTriggerData_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_CountType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tutorials_ObjectPlacementTriggerCountData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CommandBuffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter(),
				m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_ForcedUnlockDataFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ForceUIGroupUnlockData_RO_BufferLookup, ref base.CheckedStateRef),
				m_UnlockRequirementFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_UnlockRequirement_RO_BufferLookup, ref base.CheckedStateRef),
				m_Roads = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Edges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UnlockEventArchetype = m_UnlockEventArchetype,
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_HasElevation = HasElevation(),
				m_FirstTimeCheck = false
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData3, m_ActiveTriggerQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle2));
			jobData3.m_CreatedObjectChunks.Dispose(base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialObjectPlacementTriggerSystem+ClearCountJob`  
- `Game.Tutorials.TutorialObjectPlacementTriggerSystem+CheckObjectsJob`  
- `Game.Tutorials.TutorialObjectPlacementTriggerSystem+TypeHandle`  

