# Game.UI.Tooltip.TempExtractorTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempExtractorTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Objects.SearchSystem m_SearchSystem;
    private Unity.Entities.EntityQuery m_ErrorQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Game.UI.Tooltip.StringTooltip m_ResourceAvailable;
    private Game.UI.Tooltip.StringTooltip m_ResourceUnavailable;
    private Game.UI.Tooltip.IntTooltip m_Surplus;
    private Game.UI.Tooltip.IntTooltip m_Deficit;
    private Game.UI.Tooltip.StringTooltip m_ClimateAvailable;
    private Game.UI.Tooltip.StringTooltip m_ClimateUnavailable;
    private Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle __TypeHandle;

    public TempExtractorTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean FindResource(Colossal.Mathematics.Circle2 circle, Game.Areas.MapFeature requiredFeature, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
    private System.Boolean FindWoodResource(Colossal.Mathematics.Circle2 circle);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Boolean ProcessAreaNodes(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodeBuf, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource);
    private System.Boolean ProcessAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource);
    private System.Boolean ShouldMapFeatureUseResourceIcon(Game.Economy.Resource resource);
}
```


## Fields

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
```

- `private Unity.Entities.EntityQuery m_ErrorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ErrorQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
```

- `private Game.UI.Tooltip.StringTooltip m_ResourceAvailable`  

```csharp
private Game.UI.Tooltip.StringTooltip m_ResourceAvailable;
```

- `private Game.UI.Tooltip.StringTooltip m_ResourceUnavailable`  

```csharp
private Game.UI.Tooltip.StringTooltip m_ResourceUnavailable;
```

- `private Game.UI.Tooltip.IntTooltip m_Surplus`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Surplus;
```

- `private Game.UI.Tooltip.IntTooltip m_Deficit`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Deficit;
```

- `private Game.UI.Tooltip.StringTooltip m_ClimateAvailable`  

```csharp
private Game.UI.Tooltip.StringTooltip m_ClimateAvailable;
```

- `private Game.UI.Tooltip.StringTooltip m_ClimateUnavailable`  

```csharp
private Game.UI.Tooltip.StringTooltip m_ClimateUnavailable;
```

- `private Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempExtractorTooltipSystem()`  

```csharp
public TempExtractorTooltipSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private FindResource(Colossal.Mathematics.Circle2 circle, Game.Areas.MapFeature requiredFeature, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : System.Boolean`  

```csharp
private System.Boolean FindResource(Colossal.Mathematics.Circle2 circle, Game.Areas.MapFeature requiredFeature, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
```

- `private FindWoodResource(Colossal.Mathematics.Circle2 circle) : System.Boolean`  

```csharp
private System.Boolean FindWoodResource(Colossal.Mathematics.Circle2 circle);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ProcessAreaNodes(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodeBuf, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource) : System.Boolean`  

```csharp
private System.Boolean ProcessAreaNodes(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodeBuf, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource);
```

- `private ProcessAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource) : System.Boolean`  

```csharp
private System.Boolean ProcessAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas, Unity.Entities.ComponentLookup<Game.Prefabs.LotData> lotDatas, Game.Economy.Resource extractedResource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Game.Objects.Transform transform, Game.Simulation.CellMapData<Game.Simulation.NaturalResourceCell> resourceMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Areas.MapFeature& requiredFeature, System.Boolean& foundResource);
```

- `private ShouldMapFeatureUseResourceIcon(Game.Economy.Resource resource) : System.Boolean`  

```csharp
private System.Boolean ShouldMapFeatureUseResourceIcon(Game.Economy.Resource resource);
```


## Nested types

- `Game.UI.Tooltip.TempExtractorTooltipSystem+TreeIterator`  
- `Game.UI.Tooltip.TempExtractorTooltipSystem+TypeHandle`  

