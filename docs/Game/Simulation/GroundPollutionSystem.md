# Game.Simulation.GroundPollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.GroundPollution>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_PollutionParameterGroup`  
- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public GroundPollutionSystem()`  

## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public static GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap) : Game.Simulation.GroundPollution`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.GroundPollutionSystem+PollutionFadeJob`  

