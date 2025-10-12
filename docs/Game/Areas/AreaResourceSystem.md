# Game.Areas.AreaResourceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  
- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedAreaQuery`  
- `private Unity.Entities.EntityQuery m_MapTileQuery`  
- `private Unity.Entities.EntityQuery m_BrushQuery`  
- `private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_LastCityModifiers`  
- `private Game.Areas.AreaResourceSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_596039173_0`  

## Constructors

- `public AreaResourceSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static CalculateBuildable(Unity.Mathematics.float3 worldPos, Unity.Mathematics.float2 cellSize, Game.Simulation.WaterSurfaceData m_WaterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Colossal.Mathematics.Bounds1 buildableLandMaxSlope) : System.Single`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Areas.AreaResourceSystem+FindUpdatedAreasWithBrushesJob`  
- `Game.Areas.AreaResourceSystem+FindUpdatedAreasWithBoundsJob`  
- `Game.Areas.AreaResourceSystem+CollectUpdatedAreasJob`  
- `Game.Areas.AreaResourceSystem+UpdateAreaResourcesJob`  
- `Game.Areas.AreaResourceSystem+TreeIterator`  
- `Game.Areas.AreaResourceSystem+WoodIterator`  
- `Game.Areas.AreaResourceSystem+TypeHandle`  

