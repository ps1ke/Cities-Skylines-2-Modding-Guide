# Game.Simulation.TrafficAmbienceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TrafficAmbienceCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Fields

- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public TrafficAmbienceSystem()`  

## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public static GetTrafficAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap) : Game.Simulation.TrafficAmbienceCell`  
- `public static GetTrafficAmbience2(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TrafficAmbienceCell> trafficAmbienceMap, System.Single maxPerCell) : Game.Simulation.TrafficAmbienceCell`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TrafficAmbienceSystem+TrafficAmbienceUpdateJob`  

