# Game.Rendering.NetColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ZonePreferenceParameterGroup`  
- `private Unity.Entities.EntityQuery m_EdgeQuery`  
- `private Unity.Entities.EntityQuery m_NodeQuery`  
- `private Unity.Entities.EntityQuery m_LaneQuery`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private Unity.Entities.EntityQuery m_ProcessQuery`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.ZoneToolSystem m_ZoneToolSystem`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  
- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  
- `private Game.Rendering.NetColorSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1733354667_0`  

## Constructors

- `public NetColorSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.NetColorSystem+UpdateEdgeColorsJob`  
- `Game.Rendering.NetColorSystem+UpdateNodeColorsJob`  
- `Game.Rendering.NetColorSystem+UpdateEdgeColors2Job`  
- `Game.Rendering.NetColorSystem+LaneColorJob`  
- `Game.Rendering.NetColorSystem+TypeHandle`  

