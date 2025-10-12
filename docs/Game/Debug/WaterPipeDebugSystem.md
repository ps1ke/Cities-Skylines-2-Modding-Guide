# Game.Debug.WaterPipeDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_NodeGroup`  
- `private Unity.Entities.EntityQuery m_EdgeGroup`  
- `private Unity.Entities.EntityQuery m_OtherGroup`  
- `private Colossal.GizmosSystem m_GizmosSystem`  
- `private Game.Debug.WaterPipeDebugSystem+TypeHandle __TypeHandle`  

## Constructors

- `public WaterPipeDebugSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static FindEdge(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Unity.Entities.Entity& edge, Unity.Entities.DynamicBuffer<Game.Simulation.ConnectedFlowEdge> edgeBuffer, Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> edges) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Debug.WaterPipeDebugSystem+TypeHandle`  

