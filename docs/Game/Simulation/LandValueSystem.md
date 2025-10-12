# Game.Simulation.LandValueSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.LandValueCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  
- `private Unity.Entities.EntityQuery m_NodeGroup`  
- `private Unity.Entities.EntityQuery m_AttractivenessParameterQuery`  
- `private Unity.Entities.EntityQuery m_LandValueParameterQuery`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  
- `private Game.Simulation.LandValueSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public LandValueSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public static GetCellIndex(Unity.Mathematics.float3 pos) : System.Int32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.LandValueSystem+NetIterator`  
- `Game.Simulation.LandValueSystem+LandValueMapUpdateJob`  
- `Game.Simulation.LandValueSystem+EdgeUpdateJob`  
- `Game.Simulation.LandValueSystem+TypeHandle`  

