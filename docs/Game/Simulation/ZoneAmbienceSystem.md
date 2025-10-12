# Game.Simulation.ZoneAmbienceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.ZoneAmbienceCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Fields

- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public ZoneAmbienceSystem()`  

## Methods

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static GetZoneAmbience(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single maxPerCell) : System.Single`  
- `public static GetZoneAmbience(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap) : Game.Simulation.ZoneAmbienceCell`  
- `public static GetZoneAmbienceNear(Game.Simulation.GroupAmbienceType type, Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.ZoneAmbienceCell> zoneAmbienceMap, System.Single nearWeight, System.Single maxPerCell) : System.Single`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ZoneAmbienceSystem+ZoneAmbienceUpdateJob`  

