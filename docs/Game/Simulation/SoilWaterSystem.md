# Game.Simulation.SoilWaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.SoilWater>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private UnityEngine.Texture2D m_SoilWaterTexture`  
- `private Unity.Entities.EntityQuery m_SoilWaterParameterQuery`  
- `private Unity.Entities.EntityQuery m_FloodQuery`  
- `private Unity.Entities.EntityQuery m_FloodPrefabQuery`  
- `private Game.Simulation.SoilWaterSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_336595330_0`  
- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdatesPerDay`  
- `public static readonly System.Int32 kLoadDistribution`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  
- `public UnityEngine.Texture soilTexture { get }`  

## Constructors

- `public SoilWaterSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CreateFloodCounter() : System.Void`  
- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public static GetSoilWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SoilWater> soilWaterMap) : Game.Simulation.SoilWater`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.SoilWaterSystem+SoilWaterTickJob`  
- `Game.Simulation.SoilWaterSystem+TypeHandle`  

