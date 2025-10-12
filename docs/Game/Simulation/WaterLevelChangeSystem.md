# Game.Simulation.WaterLevelChangeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_WaterLevelChangeQuery`  
- `private Game.Simulation.WaterLevelChangeSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdateInterval`  

## Properties

- `public static System.Int32 TsunamiEndDelay { get }`  

## Constructors

- `public WaterLevelChangeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetMinimumDelayAt(Game.Events.WaterLevelChange change, Unity.Mathematics.float3 position) : System.UInt32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WaterLevelChangeSystem+WaterLevelChangeJob`  
- `Game.Simulation.WaterLevelChangeSystem+TypeHandle`  

