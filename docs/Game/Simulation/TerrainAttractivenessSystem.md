# Game.Simulation.TerrainAttractivenessSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TerrainAttractiveness>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  
- `private Unity.Entities.EntityQuery m_AttractivenessParameterGroup`  
- `private Unity.Collections.NativeArray<Unity.Mathematics.float3> m_AttractFactorData`  
- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public TerrainAttractivenessSystem()`  

## Methods

- `public static EvaluateAttractiveness(System.Single terrainHeight, Game.Simulation.TerrainAttractiveness attractiveness, Game.Prefabs.AttractivenessParameterData parameters) : System.Single`  
- `public static EvaluateAttractiveness(Unity.Mathematics.float3 position, Game.Simulation.CellMapData<Game.Simulation.TerrainAttractiveness> data, Game.Simulation.TerrainHeightData heightData, Game.Prefabs.AttractivenessParameterData parameters, Unity.Collections.NativeArray<System.Int32> factors) : System.Single`  
- `public static GetAttractiveness(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TerrainAttractiveness> attractivenessMap) : Game.Simulation.TerrainAttractiveness`  
- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TerrainAttractivenessSystem+TerrainAttractivenessPrepareJob`  
- `Game.Simulation.TerrainAttractivenessSystem+TerrainAttractivenessJob`  

