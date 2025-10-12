# Game.Simulation.ElectricityGraphUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static CreateFlowEdge(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity) : Unity.Entities.Entity`  
- `public static CreateFlowEdge(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity) : Unity.Entities.Entity`  
- `public static CreateFlowEdge(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityArchetype edgeArchetype, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity) : Unity.Entities.Entity`  
- `public static DeleteBuildingNodes(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Simulation.ElectricityBuildingConnection connection, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : System.Void`  
- `public static DeleteFlowNode(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.Entity node, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections) : System.Void`  
- `public static DeleteFlowNode(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity node) : System.Void`  
- `public static HasAnyFlowEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : System.Boolean`  
- `public static TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity) : System.Boolean`  
- `public static TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Game.Simulation.ElectricityFlowEdge& edge) : System.Boolean`  
- `public static TryGetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges, Unity.Entities.Entity& entity, Game.Simulation.ElectricityFlowEdge& edge) : System.Boolean`  
- `public static TrySetFlowEdge(Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, Game.Net.FlowDirection direction, System.Int32 capacity, Unity.Entities.BufferLookup`1[[Game.Simulation.ConnectedFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowConnections, Unity.Entities.ComponentLookup`1[[Game.Simulation.ElectricityFlowEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& flowEdges) : System.Boolean`  

