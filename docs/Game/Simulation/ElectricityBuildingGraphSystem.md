# Game.Simulation.ElectricityBuildingGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  
- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  
- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_UpdatedBuildingQuery`  
- `private Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ElectricityBuildingGraphSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `internal static <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all) : Unity.Entities.EntityQueryDesc`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ElectricityBuildingGraphSystem+UpdateBuildingConnectionsJob`  
- `Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle`  

