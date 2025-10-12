# Game.Net.GeometrySystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedEdgesQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedNodesQuery`  
- `private Unity.Entities.EntityQuery m_AllEdgesQuery`  
- `private Unity.Entities.EntityQuery m_AllNodesQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Net.GeometrySystem+TypeHandle __TypeHandle`  

## Constructors

- `public GeometrySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.GeometrySystem+InitializeNodeGeometryJob`  
- `Game.Net.GeometrySystem+CalculateEdgeGeometryJob`  
- `Game.Net.GeometrySystem+EdgeData`  
- `Game.Net.GeometrySystem+AllocateBuffersJob`  
- `Game.Net.GeometrySystem+FlattenNodeGeometryJob`  
- `Game.Net.GeometrySystem+FinishEdgeGeometryJob`  
- `Game.Net.GeometrySystem+CalculateNodeGeometryJob`  
- `Game.Net.GeometrySystem+IntersectionData`  
- `Game.Net.GeometrySystem+CalculateIntersectionGeometryJob`  
- `Game.Net.GeometrySystem+CopyNodeGeometryJob`  
- `Game.Net.GeometrySystem+UpdateNodeGeometryJob`  
- `Game.Net.GeometrySystem+TypeHandle`  

