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
public static Unity.Entities.Entity CreateFlowEdge(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity);
```

- `public static CreateFlowEdge(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity CreateFlowEdge(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity);
```

- `public static CreateFlowEdge(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity CreateFlowEdge(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity);
```

- `public static DeleteBuildingNodes(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Simulation.ElectricityBuildingConnection connection, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : System.Void`  

```csharp
public static System.Void DeleteBuildingNodes(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Simulation.ElectricityBuildingConnection connection, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
```

- `public static DeleteFlowNode(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.Entity node, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections) : System.Void`  

```csharp
public static System.Void DeleteFlowNode(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.Entity node, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections);
```

- `public static DeleteFlowNode(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity node) : System.Void`  

```csharp
public static System.Void DeleteFlowNode(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity node);
```

- `public static HasAnyFlowEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : System.Boolean`  

```csharp
public static System.Boolean HasAnyFlowEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
```

- `public static TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
public static System.Boolean TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity);
```

- `public static TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Game.Simulation.ElectricityFlowEdge& edge) : System.Boolean`  

```csharp
public static System.Boolean TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Game.Simulation.ElectricityFlowEdge& edge);
```

- `public static TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity, Game.Simulation.ElectricityFlowEdge& edge) : System.Boolean`  

```csharp
public static System.Boolean TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity, Game.Simulation.ElectricityFlowEdge& edge);
```

- `public static TrySetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : System.Boolean`  

```csharp
public static System.Boolean TrySetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges);
```


