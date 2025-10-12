# Game.UI.Tooltip.TempExtractorTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  
- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Objects.SearchSystem m_SearchSystem`  
- `private Unity.Entities.EntityQuery m_ErrorQuery`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  
- `private Game.UI.Tooltip.StringTooltip m_ResourceAvailable`  
- `private Game.UI.Tooltip.StringTooltip m_ResourceUnavailable`  
- `private Game.UI.Tooltip.IntTooltip m_Surplus`  
- `private Game.UI.Tooltip.IntTooltip m_Deficit`  
- `private Game.UI.Tooltip.StringTooltip m_ClimateAvailable`  
- `private Game.UI.Tooltip.StringTooltip m_ClimateUnavailable`  
- `private Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TempExtractorTooltipSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private FindResource(Colossal.Mathematics.Circle2 circle, Game.Areas.MapFeature requiredFeature, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : System.Boolean`  
- `private FindWoodResource(Colossal.Mathematics.Circle2 circle) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ProcessAreaNodes(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodeBuf, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource) : System.Boolean`  
- `private ProcessAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource) : System.Boolean`  
- `private ShouldMapFeatureUseResourceIcon(Game.Economy.Resource resource) : System.Boolean`  

## Nested types

- `Game.UI.Tooltip.TempExtractorTooltipSystem+TreeIterator`  
- `Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle`  

