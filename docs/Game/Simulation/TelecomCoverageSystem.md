# Game.Simulation.TelecomCoverageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TelecomCoverage>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_DensityQuery`  
- `private Unity.Entities.EntityQuery m_FacilityQuery`  
- `private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status`  
- `private Game.Simulation.TelecomCoverageSystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 TEXTURE_SIZE`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public TelecomCoverageSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TelecomCoverageSystem+CellDensityData`  
- `Game.Simulation.TelecomCoverageSystem+CellFacilityData`  
- `Game.Simulation.TelecomCoverageSystem+TelecomCoverageJob`  
- `Game.Simulation.TelecomCoverageSystem+TypeHandle`  

