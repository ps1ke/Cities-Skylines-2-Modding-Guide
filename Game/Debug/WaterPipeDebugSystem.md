# Game.Debug.WaterPipeDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeDebugSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NodeGroup;
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Unity.Entities.EntityQuery m_OtherGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.WaterPipeDebugSystem+TypeHandle __TypeHandle;

    public WaterPipeDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Boolean FindEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.Entity& edge, Unity.Entities.DynamicBuffer<Game.Simulation.ConnectedFlowEdge> edgeBuffer, Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> edges);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_NodeGroup;
```

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Unity.Entities.EntityQuery m_OtherGroup`  

```csharp
private Unity.Entities.EntityQuery m_OtherGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.WaterPipeDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.WaterPipeDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeDebugSystem()`  

```csharp
[Preserve]
	public WaterPipeDebugSystem()
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

- `private static FindEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.Entity& edge, Unity.Entities.DynamicBuffer<Game.Simulation.ConnectedFlowEdge> edgeBuffer, Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> edges) : System.Boolean`  

```csharp
private static bool FindEdge(Entity node1, Entity node2, out Entity edge, DynamicBuffer<ConnectedFlowEdge> edgeBuffer, ComponentLookup<WaterPipeEdge> edges)
	{
		for (int i = 0; i < edgeBuffer.Length; i++)
		{
			WaterPipeEdge waterPipeEdge = edges[edgeBuffer[i].m_Edge];
			if (waterPipeEdge.m_Start == node2 || waterPipeEdge.m_End == node2)
			{
				edge = edgeBuffer[i].m_Edge;
				return true;
			}
		}
		edge = Entity.Null;
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_NodeGroup = GetEntityQuery(ComponentType.ReadOnly<Node>(), ComponentType.ReadOnly<WaterPipeNodeConnection>());
		m_EdgeGroup = GetEntityQuery(ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<WaterPipeNodeConnection>());
		m_OtherGroup = GetEntityQuery(ComponentType.Exclude<Node>(), ComponentType.Exclude<Edge>(), ComponentType.ReadOnly<WaterPipeNodeConnection>());
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNode_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Node> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef);
		InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<WaterPipeNodeConnection> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef);
		NativeArray<Node> nativeArray = m_NodeGroup.ToComponentDataArray<Node>(Allocator.TempJob);
		NativeArray<WaterPipeNodeConnection> nativeArray2 = m_NodeGroup.ToComponentDataArray<WaterPipeNodeConnection>(Allocator.TempJob);
		JobHandle dependencies;
		GizmoBatcher gizmosBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies);
		dependencies.Complete();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			gizmosBatcher.DrawWireSphere(nativeArray[i].m_Position, 2f, Color.white);
		}
		nativeArray.Dispose();
		nativeArray2.Dispose();
		NativeArray<Entity> nativeArray3 = m_EdgeGroup.ToEntityArray(Allocator.TempJob);
		NativeArray<Edge> nativeArray4 = m_EdgeGroup.ToComponentDataArray<Edge>(Allocator.TempJob);
		NativeArray<Entity> nativeArray5 = m_OtherGroup.ToEntityArray(Allocator.TempJob);
		nativeArray2 = m_EdgeGroup.ToComponentDataArray<WaterPipeNodeConnection>(Allocator.TempJob);
		ComponentLookup<WaterPipeEdge> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef);
		InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef);
		new float3(0f, 3f, 0f);
		for (int j = 0; j < nativeArray4.Length; j++)
		{
			_ = nativeArray3[j];
			Edge edge = nativeArray4[j];
			Node node = componentLookup[edge.m_Start];
			Node node2 = componentLookup[edge.m_End];
			float3 @float = 0.5f * (node.m_Position + node2.m_Position);
			gizmosBatcher.DrawWireSphere(@float, 2f, Color.white);
			Entity waterPipeNode = nativeArray2[j].m_WaterPipeNode;
			if (componentLookup2.HasComponent(edge.m_Start))
			{
				Entity waterPipeNode2 = componentLookup2[edge.m_Start].m_WaterPipeNode;
				DynamicBuffer<ConnectedFlowEdge> buffer = base.EntityManager.GetBuffer<ConnectedFlowEdge>(waterPipeNode, isReadOnly: true);
				if (FindEdge(waterPipeNode, waterPipeNode2, out var edge2, buffer, componentLookup3))
				{
					int freshFlow = componentLookup3[edge2].m_FreshFlow;
					int freshCapacity = componentLookup3[edge2].m_FreshCapacity;
					int sewageFlow = componentLookup3[edge2].m_SewageFlow;
					int sewageCapacity = componentLookup3[edge2].m_SewageCapacity;
					float3 float2 = @float - node.m_Position;
					float3 float3 = math.normalizesafe(new float3(0f - float2.z, 0f, float2.x));
					gizmosBatcher.DrawWireCylinder(15f * float3 + 0.5f * (node.m_Position + @float), 0.002f * (float)freshFlow, 15f, Color.white);
					gizmosBatcher.DrawWireCylinder(15f * float3 + 0.5f * (node.m_Position + @float), 0.002f * (float)freshCapacity, 15f, Color.gray);
					gizmosBatcher.DrawWireCylinder(-5f * float3 + 0.5f * (node.m_Position + @float), 0.002f * (float)sewageFlow, 15f, Color.yellow);
					gizmosBatcher.DrawWireCylinder(-5f * float3 + 0.5f * (node.m_Position + @float), 0.002f * (float)sewageCapacity, 15f, Color.gray);
				}
			}
			if (componentLookup2.HasComponent(edge.m_End))
			{
				Entity waterPipeNode3 = componentLookup2[edge.m_End].m_WaterPipeNode;
				DynamicBuffer<ConnectedFlowEdge> buffer = base.EntityManager.GetBuffer<ConnectedFlowEdge>(waterPipeNode, isReadOnly: true);
				if (FindEdge(waterPipeNode, waterPipeNode3, out var edge3, buffer, componentLookup3))
				{
					int freshFlow2 = componentLookup3[edge3].m_FreshFlow;
					int freshCapacity2 = componentLookup3[edge3].m_FreshCapacity;
					int sewageFlow2 = componentLookup3[edge3].m_SewageFlow;
					int sewageCapacity2 = componentLookup3[edge3].m_SewageCapacity;
					float3 float4 = @float - node2.m_Position;
					float3 float5 = math.normalizesafe(new float3(0f - float4.z, 0f, float4.x));
					gizmosBatcher.DrawWireCylinder(15f * float5 + 0.5f * (node2.m_Position + @float), 0.002f * (float)freshFlow2, 15f, Color.white);
					gizmosBatcher.DrawWireCylinder(15f * float5 + 0.5f * (node2.m_Position + @float), 0.002f * (float)freshCapacity2, 15f, Color.gray);
					gizmosBatcher.DrawWireCylinder(-15f * float5 + 0.5f * (node2.m_Position + @float), 0.002f * (float)sewageFlow2, 15f, Color.yellow);
					gizmosBatcher.DrawWireCylinder(-15f * float5 + 0.5f * (node2.m_Position + @float), 0.002f * (float)sewageCapacity2, 15f, Color.gray);
				}
			}
		}
		nativeArray3.Dispose();
		nativeArray4.Dispose();
		nativeArray2.Dispose();
		nativeArray5.Dispose();
	}
```


## Nested types

- `Game.Debug.WaterPipeDebugSystem+TypeHandle`  

