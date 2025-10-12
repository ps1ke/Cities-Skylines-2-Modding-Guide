# Game.Simulation.PowerPlantAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  
- `private Game.Simulation.WindSystem m_WindSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Unity.Entities.EntityQuery m_PowerPlantQuery`  
- `private Game.Simulation.PowerPlantAISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_833752410_0`  
- `public static const System.Int32 MAX_WATERPOWERED_SIZE`  

## Constructors

- `public PowerPlantAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetGroundWaterProduction(Game.Prefabs.GroundWaterPoweredData groundWaterData, Unity.Mathematics.float3 position, System.Single efficiency, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap) : Unity.Mathematics.float2`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static GetWaterCapacity(Game.Buildings.WaterPowered waterPowered, Game.Prefabs.WaterPoweredData waterData) : System.Single`  
- `public static GetWindProduction(Game.Prefabs.WindPoweredData windData, Game.Simulation.Wind wind, System.Single efficiency) : Unity.Mathematics.float2`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PowerPlantAISystem+PowerPlantTickJob`  
- `Game.Simulation.PowerPlantAISystem+TypeHandle`  

