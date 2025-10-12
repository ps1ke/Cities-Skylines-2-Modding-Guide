# Game.Simulation.NoisePollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.NoisePollution>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Fields

- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public NoisePollutionSystem()`  

## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public static GetPollution(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> pollutionMap) : Game.Simulation.NoisePollution`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.NoisePollutionSystem+NoisePollutionSwapJob`  
- `Game.Simulation.NoisePollutionSystem+NoisePollutionClearJob`  

