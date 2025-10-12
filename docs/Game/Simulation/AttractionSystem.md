# Game.Simulation.AttractionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Unity.Entities.EntityQuery m_BuildingGroup`  
- `private Unity.Entities.EntityQuery m_SettingsQuery`  
- `private Game.Simulation.AttractionSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AttractionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static SetFactor(Unity.Collections.NativeArray<System.Int32> factors, Game.Simulation.AttractionSystem+AttractivenessFactor factor, System.Single attractiveness) : System.Void`  

## Nested types

- `Game.Simulation.AttractionSystem+AttractivenessFactor`  
- `Game.Simulation.AttractionSystem+AttractivenessJob`  
- `Game.Simulation.AttractionSystem+TypeHandle`  

