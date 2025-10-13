# Game.UI.InGame.StatisticsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StatisticsUISystem : Game.UI.UISystemBase
{
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
    private Game.UI.InGame.TimeUISystem m_TimeUISystem;
    private Unity.Entities.EntityQuery m_StatisticsCategoryQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
    private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_GroupCache;
    private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SubGroupCache;
    private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SelectedStatistics;
    private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SelectedStatisticsTracker;
    private Unity.Entities.Entity m_ActiveCategory;
    private Unity.Entities.Entity m_ActiveGroup;
    private System.Int32 m_SampleRange;
    private System.Boolean m_Stacked;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_GroupsMapBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_SampleRangeBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_SampleCountBinding;
    private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_ActiveGroupBinding;
    private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_ActiveCategoryBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_StackedBinding;
    private Colossal.UI.Binding.RawValueBinding m_SelectedStatisticsBinding;
    private Colossal.UI.Binding.RawValueBinding m_CategoriesBinding;
    private Colossal.UI.Binding.RawValueBinding m_DataBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UnlockingRequirementsBinding;
    private System.Boolean m_ClearActive;
    private System.Int32 m_UnlockRequirementVersion;
    private static const System.String kGroup;

    public StatisticsUISystem();

    private Unity.Entities.Entity <OnCreate>b__31_0();
    private Unity.Entities.Entity <OnCreate>b__31_1();
    private System.Boolean <OnCreate>b__31_2();
    private System.Boolean <UpdateStackedStatus>b__53_0(Game.UI.InGame.StatisticsUISystem+StatItem stat);
    private System.Void AddStat(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Boolean onlyTracker);
    private System.Void BindCategories(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindData(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindData(Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.StatisticsUISystem+StatItem stat);
    private System.Void BindGroups(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity parent);
    private System.Void BindSelectedStatistics(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindUnlockingRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity);
    private System.Void CacheChildren(Unity.Entities.Entity parentEntity, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache);
    private System.Void CacheParameterChildren(Unity.Entities.Entity parent, System.Boolean locked, Game.Prefabs.StatisticsData statisticsData, Game.Prefabs.PrefabData prefabData, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache);
    private System.Void CheckActiveCategory(Game.UI.InGame.StatisticsUISystem+StatItem stat);
    private System.Void CheckActiveGroup(Game.UI.InGame.StatisticsUISystem+StatItem stat);
    private System.Void ClearActive();
    private System.Void ClearStats();
    private System.Void DeepRemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat);
    private Unity.Collections.NativeArray<System.Int64> EnsureDataSize(Unity.Collections.NativeArray<System.Int64> data);
    private Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint> GetDataPoints(System.Int32 range, System.Int32 samples, Unity.Collections.NativeArray<System.Int64> data, Game.Common.TimeData timeData);
    private System.Int32 GetSampleInterval(System.Int32 range);
    private Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+StatCategory> GetSortedCategories();
    private Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint> GetStatisticData(Game.UI.InGame.StatisticsUISystem+StatItem stat);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnStatisticsUpdated();
    protected virtual System.Void OnUpdate();
    private System.Void ProcessAddStat(Game.UI.InGame.StatisticsUISystem+StatItem stat);
    private System.Void ProcessAddStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat);
    private System.Void RemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Boolean keepTracker);
    private System.Void RemoveStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat);
    private System.Void RemoveStatParent(Game.UI.InGame.StatisticsUISystem+StatItem stat);
    private System.Void SetSampleRange(System.Int32 range);
    private System.Boolean TryAddChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache);
    private System.Void UpdateStackedStatus();
    private System.Void UpdateStats();
}
```


## Fields

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  

```csharp
private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
```

- `private Game.UI.InGame.TimeUISystem m_TimeUISystem`  

```csharp
private Game.UI.InGame.TimeUISystem m_TimeUISystem;
```

- `private Unity.Entities.EntityQuery m_StatisticsCategoryQuery`  

```csharp
private Unity.Entities.EntityQuery m_StatisticsCategoryQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
```

- `private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_GroupCache`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_GroupCache;
```

- `private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SubGroupCache`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SubGroupCache;
```

- `private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SelectedStatistics`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SelectedStatistics;
```

- `private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SelectedStatisticsTracker`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SelectedStatisticsTracker;
```

- `private Unity.Entities.Entity m_ActiveCategory`  

```csharp
private Unity.Entities.Entity m_ActiveCategory;
```

- `private Unity.Entities.Entity m_ActiveGroup`  

```csharp
private Unity.Entities.Entity m_ActiveGroup;
```

- `private System.Int32 m_SampleRange`  

```csharp
private System.Int32 m_SampleRange;
```

- `private System.Boolean m_Stacked`  

```csharp
private System.Boolean m_Stacked;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_GroupsMapBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_GroupsMapBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SampleRangeBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_SampleRangeBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SampleCountBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_SampleCountBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_ActiveGroupBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_ActiveGroupBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_ActiveCategoryBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_ActiveCategoryBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_StackedBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_StackedBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_SelectedStatisticsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_SelectedStatisticsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_CategoriesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_CategoriesBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_DataBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_DataBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UnlockingRequirementsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UnlockingRequirementsBinding;
```

- `private System.Boolean m_ClearActive`  

```csharp
private System.Boolean m_ClearActive;
```

- `private System.Int32 m_UnlockRequirementVersion`  

```csharp
private System.Int32 m_UnlockRequirementVersion;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public StatisticsUISystem()`  

```csharp
public StatisticsUISystem();
```


## Methods

- `private <OnCreate>b__31_0() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__31_0();
```

- `private <OnCreate>b__31_1() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__31_1();
```

- `private <OnCreate>b__31_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__31_2();
```

- `private <UpdateStackedStatus>b__53_0(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Boolean`  

```csharp
private System.Boolean <UpdateStackedStatus>b__53_0(Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `private AddStat(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Boolean onlyTracker) : System.Void`  

```csharp
private System.Void AddStat(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Boolean onlyTracker);
```

- `private BindCategories(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindCategories(Colossal.UI.Binding.IJsonWriter binder);
```

- `private BindData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindData(Colossal.UI.Binding.IJsonWriter binder);
```

- `private BindData(Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private System.Void BindData(Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `private BindGroups(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity parent) : System.Void`  

```csharp
private System.Void BindGroups(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity parent);
```

- `private BindSelectedStatistics(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindSelectedStatistics(Colossal.UI.Binding.IJsonWriter binder);
```

- `private BindUnlockingRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
private System.Void BindUnlockingRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity);
```

- `private CacheChildren(Unity.Entities.Entity parentEntity, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache) : System.Void`  

```csharp
private System.Void CacheChildren(Unity.Entities.Entity parentEntity, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache);
```

- `private CacheParameterChildren(Unity.Entities.Entity parent, System.Boolean locked, Game.Prefabs.StatisticsData statisticsData, Game.Prefabs.PrefabData prefabData, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache) : System.Void`  

```csharp
private System.Void CacheParameterChildren(Unity.Entities.Entity parent, System.Boolean locked, Game.Prefabs.StatisticsData statisticsData, Game.Prefabs.PrefabData prefabData, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache);
```

- `private CheckActiveCategory(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private System.Void CheckActiveCategory(Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `private CheckActiveGroup(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private System.Void CheckActiveGroup(Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `private ClearActive() : System.Void`  

```csharp
private System.Void ClearActive();
```

- `private ClearStats() : System.Void`  

```csharp
private System.Void ClearStats();
```

- `private DeepRemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private System.Void DeepRemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `private EnsureDataSize(Unity.Collections.NativeArray<System.Int64> data) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
private Unity.Collections.NativeArray<System.Int64> EnsureDataSize(Unity.Collections.NativeArray<System.Int64> data);
```

- `private GetDataPoints(System.Int32 range, System.Int32 samples, Unity.Collections.NativeArray<System.Int64> data, Game.Common.TimeData timeData) : Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint>`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint> GetDataPoints(System.Int32 range, System.Int32 samples, Unity.Collections.NativeArray<System.Int64> data, Game.Common.TimeData timeData);
```

- `private GetSampleInterval(System.Int32 range) : System.Int32`  

```csharp
private System.Int32 GetSampleInterval(System.Int32 range);
```

- `private GetSortedCategories() : Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+StatCategory>`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+StatCategory> GetSortedCategories();
```

- `private GetStatisticData(Game.UI.InGame.StatisticsUISystem+StatItem stat) : Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint>`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint> GetStatisticData(Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnStatisticsUpdated() : System.Void`  

```csharp
private System.Void OnStatisticsUpdated();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ProcessAddStat(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private System.Void ProcessAddStat(Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `private ProcessAddStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private System.Void ProcessAddStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `private RemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Boolean keepTracker) : System.Void`  

```csharp
private System.Void RemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Boolean keepTracker);
```

- `private RemoveStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private System.Void RemoveStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `private RemoveStatParent(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private System.Void RemoveStatParent(Game.UI.InGame.StatisticsUISystem+StatItem stat);
```

- `private SetSampleRange(System.Int32 range) : System.Void`  

```csharp
private System.Void SetSampleRange(System.Int32 range);
```

- `private TryAddChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache) : System.Boolean`  

```csharp
private System.Boolean TryAddChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache);
```

- `private UpdateStackedStatus() : System.Void`  

```csharp
private System.Void UpdateStackedStatus();
```

- `private UpdateStats() : System.Void`  

```csharp
private System.Void UpdateStats();
```


## Nested types

- `Game.UI.InGame.StatisticsUISystem+StatCategory`  
- `Game.UI.InGame.StatisticsUISystem+DataPoint`  
- `Game.UI.InGame.StatisticsUISystem+StatItem`  
- `Game.UI.InGame.StatisticsUISystem+<>c`  
- `Game.UI.InGame.StatisticsUISystem+<>c__DisplayClass56_0`  
- `Game.UI.InGame.StatisticsUISystem+<>c__DisplayClass57_0`  

