# Game.UI.Editor.MapRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Areas.MapTileSystem m_MapTileSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Entities.EntityQuery m_TileQuery`  
- `private Unity.Entities.EntityQuery m_OutsideRoadNodeQuery`  
- `private Unity.Entities.EntityQuery m_OutsideTrainNodeQuery`  
- `private Unity.Entities.EntityQuery m_OutsideAirNodeQuery`  
- `private Unity.Entities.EntityQuery m_OutsideElectricityConnectionQuery`  
- `private Unity.Jobs.JobHandle m_ResultDependency`  
- `private Colossal.Collections.NativeValue<System.Boolean> m_WaterResult`  
- `private Unity.Collections.NativeArray<System.Boolean> m_StartingAreaResources`  
- `private Unity.Collections.NativeArray<System.Boolean> m_MapResources`  
- `private System.Boolean <hasStartingArea>k__BackingField`  
- `private System.Boolean <roadConnection>k__BackingField`  
- `private System.Boolean <trainConnection>k__BackingField`  
- `private System.Boolean <airConnection>k__BackingField`  
- `private System.Boolean <electricityConnection>k__BackingField`  
- `private Game.UI.Editor.MapRequirementSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Boolean hasStartingArea { get; private set }`  
- `public System.Boolean roadConnection { get; private set }`  
- `public System.Boolean trainConnection { get; private set }`  
- `public System.Boolean airConnection { get; private set }`  
- `public System.Boolean electricityConnection { get; private set }`  

## Constructors

- `public MapRequirementSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public MapHasResource(Game.Areas.MapFeature feature) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public StartingAreaHasResource(Game.Areas.MapFeature feature) : System.Boolean`  

## Nested types

- `Game.UI.Editor.MapRequirementSystem+CollectResourcesJob`  
- `Game.UI.Editor.MapRequirementSystem+CollectStartingResourcesJob`  
- `Game.UI.Editor.MapRequirementSystem+CheckWaterJob`  
- `Game.UI.Editor.MapRequirementSystem+TypeHandle`  

