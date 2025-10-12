# Game.Tools.TelecomPreviewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TelecomCoverage>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_DensityQuery`  
- `private Unity.Entities.EntityQuery m_FacilityQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedQuery`  
- `private System.Boolean m_ForceUpdate`  
- `private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status`  
- `private Game.Tools.TelecomPreviewSystem+TypeHandle __TypeHandle`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public TelecomPreviewSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.TelecomPreviewSystem+TypeHandle`  

