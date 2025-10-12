# Game.UI.MapMetadataSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private System.Single m_Area`  
- `private System.Single m_BuildableLand`  
- `private System.Single m_SurfaceWaterAvailability`  
- `private System.Single m_GroundWaterAvailability`  
- `private Game.UI.MapMetadataSystem+Resources m_Resources`  
- `private Game.UI.MapMetadataSystem+Connections m_Connections`  
- `private Unity.Entities.EntityQuery m_MapTileQuery`  
- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  
- `private System.String <mapName>k__BackingField`  
- `private Game.UI.MapMetadataSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.String mapName { get; set }`  
- `public System.String theme { get }`  
- `public Colossal.Mathematics.Bounds1 temperatureRange { get }`  
- `public System.Single cloudiness { get }`  
- `public System.Single precipitation { get }`  
- `public System.Single latitude { get }`  
- `public System.Single longitude { get }`  
- `public System.Single area { get }`  
- `public System.Single buildableLand { get }`  
- `public System.Single surfaceWaterAvailability { get }`  
- `public System.Single groundWaterAvailability { get }`  
- `public Game.UI.MapMetadataSystem+Resources resources { get }`  
- `public Game.UI.MapMetadataSystem+Connections connections { get }`  

## Constructors

- `public MapMetadataSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UpdateConnections() : System.Void`  
- `private UpdateResources() : System.Void`  

## Nested types

- `Game.UI.MapMetadataSystem+Resources`  
- `Game.UI.MapMetadataSystem+Connections`  
- `Game.UI.MapMetadataSystem+TypeHandle`  

