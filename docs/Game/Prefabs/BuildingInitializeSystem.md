# Game.Prefabs.BuildingInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.BuildingInitializeSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_547773813_0`  
- `private static Colossal.Logging.ILog log`  

## Constructors

- `public BuildingInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private InitializeLotSize(Game.Prefabs.BuildingPrefab buildingPrefab, Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Game.Prefabs.BuildingData& buildingData) : System.Void`  
- `public static InitializeTerraformData(Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Colossal.Mathematics.Bounds2 lotBounds, Colossal.Mathematics.Bounds2 flatBounds) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.BuildingInitializeSystem+FindConnectionRequirementsJob`  
- `Game.Prefabs.BuildingInitializeSystem+TypeHandle`  

