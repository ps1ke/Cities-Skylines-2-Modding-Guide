# Game.Rendering.OverlayInfomodeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem`  
- `private Game.Rendering.WaterRenderSystem m_WaterRenderSystem`  
- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Simulation.WindSystem m_WindSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Tools.TelecomPreviewSystem m_TelecomCoverageSystem`  
- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  
- `private Game.Simulation.LandValueSystem m_LandValueSystem`  
- `private Game.Simulation.PopulationToGridSystem m_PopulationToGridSystem`  
- `private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  
- `private UnityEngine.Texture2D m_TerrainTexture`  
- `private UnityEngine.Texture2D m_WaterTexture`  
- `private UnityEngine.Texture2D m_WindTexture`  
- `private Unity.Jobs.JobHandle m_Dependency`  
- `private Game.Rendering.OverlayInfomodeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public OverlayInfomodeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public ApplyOverlay() : System.Void`  
- `private GetTerrainTextureData<T>(Game.Simulation.CellMapData<T> cellMapData) : Unity.Collections.NativeArray<System.Byte>`  
- `private GetTerrainTextureData(Unity.Mathematics.int2 size) : Unity.Collections.NativeArray<System.Byte>`  
- `private GetWaterTextureData<T>(Game.Simulation.CellMapData<T> cellMapData) : Unity.Collections.NativeArray<System.Byte>`  
- `private GetWaterTextureData(Unity.Mathematics.int2 size) : Unity.Collections.NativeArray<System.Byte>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.OverlayInfomodeSystem+ClearJob`  
- `Game.Rendering.OverlayInfomodeSystem+GroundWaterJob`  
- `Game.Rendering.OverlayInfomodeSystem+GroundPollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+NoisePollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+AirPollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+WindJob`  
- `Game.Rendering.OverlayInfomodeSystem+TelecomCoverageJob`  
- `Game.Rendering.OverlayInfomodeSystem+FertilityJob`  
- `Game.Rendering.OverlayInfomodeSystem+OreJob`  
- `Game.Rendering.OverlayInfomodeSystem+OilJob`  
- `Game.Rendering.OverlayInfomodeSystem+FishJob`  
- `Game.Rendering.OverlayInfomodeSystem+LandValueJob`  
- `Game.Rendering.OverlayInfomodeSystem+PopulationJob`  
- `Game.Rendering.OverlayInfomodeSystem+AttractionJob`  
- `Game.Rendering.OverlayInfomodeSystem+CustomerJob`  
- `Game.Rendering.OverlayInfomodeSystem+WorkplaceJob`  
- `Game.Rendering.OverlayInfomodeSystem+ServiceJob`  
- `Game.Rendering.OverlayInfomodeSystem+GroundWaterPollutionJob`  
- `Game.Rendering.OverlayInfomodeSystem+TypeHandle`  

