# Game.Simulation.ExtractorCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ExtractorCompanySystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem;
    private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Game.Simulation.ExtractorCompanySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1012523227_0;
    private Unity.Entities.EntityQuery __query_1012523227_1;

    public ExtractorCompanySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Boolean GetBestConcentration(Game.Economy.Resource resource, Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Single& concentration, System.Single& size);
    private static System.Void GetBestConcentration(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, System.Boolean requireNaturalResource, System.Single& concentration, System.Single& size);
    public static System.Single GetEffectiveConcentration(Game.Prefabs.ExtractorParameterData extractorParameters, Game.Areas.MapFeature feature, System.Single concentration);
    public static Game.Areas.MapFeature GetRequiredMapFeature(Game.Economy.Resource output, Unity.Entities.Entity lotPrefab, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem`  

```csharp
private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem;
```

- `private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem`  

```csharp
private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem;
```

- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  

```csharp
private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Game.Simulation.ExtractorCompanySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ExtractorCompanySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1012523227_0`  

```csharp
private Unity.Entities.EntityQuery __query_1012523227_0;
```

- `private Unity.Entities.EntityQuery __query_1012523227_1`  

```csharp
private Unity.Entities.EntityQuery __query_1012523227_1;
```


## Constructors

- `public ExtractorCompanySystem()`  

```csharp
public ExtractorCompanySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetBestConcentration(Game.Economy.Resource resource, Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Single& concentration, System.Single& size) : System.Boolean`  

```csharp
public static System.Boolean GetBestConcentration(Game.Economy.Resource resource, Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Single& concentration, System.Single& size);
```

- `private static GetBestConcentration(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, System.Boolean requireNaturalResource, System.Single& concentration, System.Single& size) : System.Void`  

```csharp
private static System.Void GetBestConcentration(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ExtractorAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractorDatas, Game.Prefabs.ExtractorParameterData extractorParameters, System.Boolean requireNaturalResource, System.Single& concentration, System.Single& size);
```

- `public static GetEffectiveConcentration(Game.Prefabs.ExtractorParameterData extractorParameters, Game.Areas.MapFeature feature, System.Single concentration) : System.Single`  

```csharp
public static System.Single GetEffectiveConcentration(Game.Prefabs.ExtractorParameterData extractorParameters, Game.Areas.MapFeature feature, System.Single concentration);
```

- `public static GetRequiredMapFeature(Game.Economy.Resource output, Unity.Entities.Entity lotPrefab, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas) : Game.Areas.MapFeature`  

```csharp
public static Game.Areas.MapFeature GetRequiredMapFeature(Game.Economy.Resource output, Unity.Entities.Entity lotPrefab, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ExtractorAreaData> extractorAreaDatas);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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


## Nested types

- `Game.Simulation.ExtractorCompanySystem+ExtractorJob`  
- `Game.Simulation.ExtractorCompanySystem+TypeHandle`  

