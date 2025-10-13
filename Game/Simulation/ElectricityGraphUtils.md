# Game.Simulation.ElectricityGraphUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ElectricityGraphUtils
{
    public static Unity.Entities.Entity CreateFlowEdge(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity);
    public static Unity.Entities.Entity CreateFlowEdge(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity);
    public static Unity.Entities.Entity CreateFlowEdge(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity);
    public static System.Void DeleteBuildingNodes(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Simulation.ElectricityBuildingConnection connection, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
    public static System.Void DeleteFlowNode(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.Entity node, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections);
    public static System.Void DeleteFlowNode(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity node);
    public static System.Boolean HasAnyFlowEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
    public static System.Boolean TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity);
    public static System.Boolean TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Game.Simulation.ElectricityFlowEdge& edge);
    public static System.Boolean TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity, Game.Simulation.ElectricityFlowEdge& edge);
    public static System.Boolean TrySetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
}
```


## Methods

- `public static CreateFlowEdge(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity) : Unity.Entities.Entity`  

```csharp
public static Entity CreateFlowEdge(EntityManager entityManager, EntityArchetype edgeArchetype, Entity startNode, Entity endNode, FlowDirection direction, int capacity)
	{
		Assert.AreNotEqual(startNode, Entity.Null);
		Assert.AreNotEqual(endNode, Entity.Null);
		Entity entity = entityManager.CreateEntity(edgeArchetype);
		entityManager.SetComponentData(entity, new ElectricityFlowEdge
		{
			m_Start = startNode,
			m_End = endNode,
			direction = direction,
			m_Capacity = capacity
		});
		entityManager.GetBuffer<ConnectedFlowEdge>(startNode).Add(new ConnectedFlowEdge(entity));
		entityManager.GetBuffer<ConnectedFlowEdge>(endNode).Add(new ConnectedFlowEdge(entity));
		return entity;
	}
```

- `public static CreateFlowEdge(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity) : Unity.Entities.Entity`  

```csharp
public static Entity CreateFlowEdge(EntityManager entityManager, EntityArchetype edgeArchetype, Entity startNode, Entity endNode, FlowDirection direction, int capacity)
	{
		Assert.AreNotEqual(startNode, Entity.Null);
		Assert.AreNotEqual(endNode, Entity.Null);
		Entity entity = entityManager.CreateEntity(edgeArchetype);
		entityManager.SetComponentData(entity, new ElectricityFlowEdge
		{
			m_Start = startNode,
			m_End = endNode,
			direction = direction,
			m_Capacity = capacity
		});
		entityManager.GetBuffer<ConnectedFlowEdge>(startNode).Add(new ConnectedFlowEdge(entity));
		entityManager.GetBuffer<ConnectedFlowEdge>(endNode).Add(new ConnectedFlowEdge(entity));
		return entity;
	}
```

- `public static CreateFlowEdge(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity) : Unity.Entities.Entity`  

```csharp
public static Entity CreateFlowEdge(EntityManager entityManager, EntityArchetype edgeArchetype, Entity startNode, Entity endNode, FlowDirection direction, int capacity)
	{
		Assert.AreNotEqual(startNode, Entity.Null);
		Assert.AreNotEqual(endNode, Entity.Null);
		Entity entity = entityManager.CreateEntity(edgeArchetype);
		entityManager.SetComponentData(entity, new ElectricityFlowEdge
		{
			m_Start = startNode,
			m_End = endNode,
			direction = direction,
			m_Capacity = capacity
		});
		entityManager.GetBuffer<ConnectedFlowEdge>(startNode).Add(new ConnectedFlowEdge(entity));
		entityManager.GetBuffer<ConnectedFlowEdge>(endNode).Add(new ConnectedFlowEdge(entity));
		return entity;
	}
```

- `public static DeleteBuildingNodes(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Simulation.ElectricityBuildingConnection connection, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : System.Void`  

```csharp
public static void DeleteBuildingNodes(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ElectricityBuildingConnection connection, ref BufferLookup<ConnectedFlowEdge> flowConnections, ref ComponentLookup<ElectricityFlowEdge> flowEdges)
	{
		if (connection.m_TransformerNode != Entity.Null)
		{
			DeleteFlowNode(commandBuffer, jobIndex, connection.m_TransformerNode, ref flowConnections);
		}
		if (connection.m_ProducerEdge != Entity.Null)
		{
			DeleteFlowNode(commandBuffer, jobIndex, connection.GetProducerNode(ref flowEdges), ref flowConnections);
		}
		if (connection.m_ConsumerEdge != Entity.Null)
		{
			DeleteFlowNode(commandBuffer, jobIndex, connection.GetConsumerNode(ref flowEdges), ref flowConnections);
		}
		if (connection.m_ChargeEdge != Entity.Null)
		{
			DeleteFlowNode(commandBuffer, jobIndex, connection.GetChargeNode(ref flowEdges), ref flowConnections);
		}
		if (connection.m_DischargeEdge != Entity.Null)
		{
			DeleteFlowNode(commandBuffer, jobIndex, connection.GetDischargeNode(ref flowEdges), ref flowConnections);
		}
	}
```

- `public static DeleteFlowNode(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.Entity node, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections) : System.Void`  

```csharp
public static void DeleteFlowNode(EntityManager entityManager, Entity node)
	{
		entityManager.AddComponent<Deleted>(node);
		foreach (ConnectedFlowEdge item in entityManager.GetBuffer<ConnectedFlowEdge>(node, isReadOnly: true))
		{
			entityManager.AddComponent<Deleted>(item.m_Edge);
		}
	}
```

- `public static DeleteFlowNode(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity node) : System.Void`  

```csharp
public static void DeleteFlowNode(EntityManager entityManager, Entity node)
	{
		entityManager.AddComponent<Deleted>(node);
		foreach (ConnectedFlowEdge item in entityManager.GetBuffer<ConnectedFlowEdge>(node, isReadOnly: true))
		{
			entityManager.AddComponent<Deleted>(item.m_Edge);
		}
	}
```

- `public static HasAnyFlowEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : System.Boolean`  

```csharp
public static bool HasAnyFlowEdge(Entity node1, Entity node2, ref BufferLookup<ConnectedFlowEdge> flowConnections, ref ComponentLookup<ElectricityFlowEdge> flowEdges)
	{
		Assert.IsTrue(node1.Index > 0);
		Assert.IsTrue(node2.Index > 0);
		foreach (ConnectedFlowEdge item in flowConnections[node1])
		{
			ElectricityFlowEdge electricityFlowEdge = flowEdges[item.m_Edge];
			if ((electricityFlowEdge.m_Start == node1 && electricityFlowEdge.m_End == node2) || (electricityFlowEdge.m_Start == node2 && electricityFlowEdge.m_End == node1))
			{
				return true;
			}
		}
		return false;
	}
```

- `public static TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
public static bool TryGetFlowEdge(Entity startNode, Entity endNode, ref BufferLookup<ConnectedFlowEdge> flowConnections, ref ComponentLookup<ElectricityFlowEdge> flowEdges, out Entity entity, out ElectricityFlowEdge edge)
	{
		Assert.IsTrue(startNode.Index > 0);
		Assert.IsTrue(endNode.Index > 0);
		foreach (ConnectedFlowEdge item in flowConnections[startNode])
		{
			entity = item.m_Edge;
			edge = flowEdges[entity];
			if (edge.m_Start == startNode && edge.m_End == endNode)
			{
				return true;
			}
		}
		entity = default(Entity);
		edge = default(ElectricityFlowEdge);
		return false;
	}
```

- `public static TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Game.Simulation.ElectricityFlowEdge& edge) : System.Boolean`  

```csharp
public static bool TryGetFlowEdge(Entity startNode, Entity endNode, ref BufferLookup<ConnectedFlowEdge> flowConnections, ref ComponentLookup<ElectricityFlowEdge> flowEdges, out Entity entity, out ElectricityFlowEdge edge)
	{
		Assert.IsTrue(startNode.Index > 0);
		Assert.IsTrue(endNode.Index > 0);
		foreach (ConnectedFlowEdge item in flowConnections[startNode])
		{
			entity = item.m_Edge;
			edge = flowEdges[entity];
			if (edge.m_Start == startNode && edge.m_End == endNode)
			{
				return true;
			}
		}
		entity = default(Entity);
		edge = default(ElectricityFlowEdge);
		return false;
	}
```

- `public static TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity, Game.Simulation.ElectricityFlowEdge& edge) : System.Boolean`  

```csharp
public static bool TryGetFlowEdge(Entity startNode, Entity endNode, ref BufferLookup<ConnectedFlowEdge> flowConnections, ref ComponentLookup<ElectricityFlowEdge> flowEdges, out Entity entity, out ElectricityFlowEdge edge)
	{
		Assert.IsTrue(startNode.Index > 0);
		Assert.IsTrue(endNode.Index > 0);
		foreach (ConnectedFlowEdge item in flowConnections[startNode])
		{
			entity = item.m_Edge;
			edge = flowEdges[entity];
			if (edge.m_Start == startNode && edge.m_End == endNode)
			{
				return true;
			}
		}
		entity = default(Entity);
		edge = default(ElectricityFlowEdge);
		return false;
	}
```

- `public static TrySetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : System.Boolean`  

```csharp
public static bool TrySetFlowEdge(Entity startNode, Entity endNode, FlowDirection direction, int capacity, ref BufferLookup<ConnectedFlowEdge> flowConnections, ref ComponentLookup<ElectricityFlowEdge> flowEdges)
	{
		if (TryGetFlowEdge(startNode, endNode, ref flowConnections, ref flowEdges, out var entity, out var edge))
		{
			edge.direction = direction;
			edge.m_Capacity = capacity;
			flowEdges[entity] = edge;
			return true;
		}
		return false;
	}
```


