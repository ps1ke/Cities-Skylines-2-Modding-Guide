# Game.Simulation.WaterPumpingStationAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_PumpQuery`  
- `private Unity.Entities.EntityQuery m_ParameterQuery`  
- `private Game.Simulation.WaterPumpingStationAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public WaterPumpingStationAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetSurfaceWaterAvailability(Unity.Mathematics.float3 position, Game.Prefabs.AllowedWaterTypes allowedTypes, Game.Simulation.WaterSurfaceData waterSurfaceData, System.Single effectiveDepth) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WaterPumpingStationAISystem+PumpTickJob`  
- `Game.Simulation.WaterPumpingStationAISystem+TypeHandle`  

