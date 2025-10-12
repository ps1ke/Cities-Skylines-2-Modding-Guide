# Game.Simulation.CarNavigationSystem+Actions

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem`  
- `public Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  
- `public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneReservation> m_LaneReservationQueue`  
- `public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneEffects> m_LaneEffectsQueue`  
- `public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationHelpers+LaneSignal> m_LaneSignalQueue`  
- `public Unity.Collections.NativeQueue<Game.Simulation.CarNavigationSystem+TrafficAmbienceEffect> m_TrafficAmbienceQueue`  
- `public Unity.Jobs.JobHandle m_Dependency`  
- `private Game.Simulation.CarNavigationSystem+Actions+TypeHandle __TypeHandle`  

## Constructors

- `public Actions()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CarNavigationSystem+Actions+TypeHandle`  

