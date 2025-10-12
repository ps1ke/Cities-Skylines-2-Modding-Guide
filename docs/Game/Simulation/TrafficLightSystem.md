# Game.Simulation.TrafficLightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_TrafficLightQuery`  
- `private Game.Simulation.TrafficLightSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public TrafficLightSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static UpdateLaneSignal(Game.Net.TrafficLights trafficLights, Game.Net.LaneSignal& laneSignal) : System.Void`  
- `public static UpdateMoveableBridge(Game.Net.TrafficLights trafficLights, Game.Objects.Transform transform, Game.Prefabs.MoveableBridgeData moveableBridgeData, Game.Common.PointOfInterest& pointOfInterest) : System.Void`  
- `public static UpdateTrafficLightState(Game.Net.TrafficLights trafficLights, Game.Objects.TrafficLight& trafficLight) : System.Void`  

## Nested types

- `Game.Simulation.TrafficLightSystem+UpdateTrafficLightsJob`  
- `Game.Simulation.TrafficLightSystem+TypeHandle`  

