# Game.Simulation.ElectricityStatusSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityStatusSystem : Game.GameSystemBase
{
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_ElectricityParameterQuery;
    private Game.Simulation.ElectricityStatusSystem+TypeHandle __TypeHandle;

    public ElectricityStatusSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ElectricityParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ElectricityParameterQuery;
```

- `private Game.Simulation.ElectricityStatusSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityStatusSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ElectricityStatusSystem()`  

```csharp
[Preserve]
	public ElectricityStatusSystem()
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
		return 128;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 127;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ElectricityFlowSystem = base.World.GetOrCreateSystemManaged<ElectricityFlowSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_EdgeQuery = GetEntityQuery(ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<ElectricityNodeConnection>(), ComponentType.Exclude<Temp>());
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<ElectricityBuildingConnection>(), ComponentType.ReadOnly<Transform>(), ComponentType.ReadOnly<Game.Net.SubNet>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ElectricityParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ElectricityParameterData>());
		RequireAnyForUpdate(m_EdgeQuery, m_BuildingQuery);
		RequireForUpdate(m_ElectricityParameterQuery);
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
		IconCommandBuffer iconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer();
		ElectricityParameterData singleton = m_ElectricityParameterQuery.GetSingleton<ElectricityParameterData>();
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(new NetEdgeNotificationJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ElectricityNodeConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectedFlowEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SourceNode = m_ElectricityFlowSystem.sourceNode,
			m_SinkNode = m_ElectricityFlowSystem.sinkNode,
			m_ElectricityParameters = singleton,
			m_IconCommandBuffer = iconCommandBuffer
		}, m_EdgeQuery, base.Dependency);
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new BuildingNotificationJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ElectricityBuildingConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityBuildingConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectedFlowEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SourceNode = m_ElectricityFlowSystem.sourceNode,
			m_ElectricityParameters = singleton,
			m_IconCommandBuffer = iconCommandBuffer
		}, m_BuildingQuery, dependsOn);
		base.Dependency = dependency;
		m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.ElectricityStatusSystem+NetEdgeNotificationJob`  
- `Game.Simulation.ElectricityStatusSystem+BuildingNotificationJob`  
- `Game.Simulation.ElectricityStatusSystem+TypeHandle`  

