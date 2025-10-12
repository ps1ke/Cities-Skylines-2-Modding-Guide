# Game.Simulation.StreetLightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Rendering.LightingSystem m_LightingSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_StreetLightQuery`  
- `private Game.Simulation.StreetLightSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public StreetLightSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Net.Road road) : System.Void`  
- `public static UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Buildings.Building building) : System.Void`  
- `public static UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Vehicles.Watercraft watercraft) : System.Void`  

## Nested types

- `Game.Simulation.StreetLightSystem+UpdateStreetLightsJob`  
- `Game.Simulation.StreetLightSystem+TypeHandle`  

