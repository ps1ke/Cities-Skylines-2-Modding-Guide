# Game.UI.InGame.StatisticsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  
- `private Game.UI.InGame.TimeUISystem m_TimeUISystem`  
- `private Unity.Entities.EntityQuery m_StatisticsCategoryQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Unity.Entities.EntityQuery m_UnlockedPrefabQuery`  
- `private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_GroupCache`  
- `private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SubGroupCache`  
- `private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SelectedStatistics`  
- `private System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> m_SelectedStatisticsTracker`  
- `private Unity.Entities.Entity m_ActiveCategory`  
- `private Unity.Entities.Entity m_ActiveGroup`  
- `private System.Int32 m_SampleRange`  
- `private System.Boolean m_Stacked`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_GroupsMapBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SampleRangeBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SampleCountBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_ActiveGroupBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_ActiveCategoryBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_StackedBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_SelectedStatisticsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_CategoriesBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_DataBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UnlockingRequirementsBinding`  
- `private System.Boolean m_ClearActive`  
- `private System.Int32 m_UnlockRequirementVersion`  
- `private static const System.String kGroup`  

## Constructors

- `public StatisticsUISystem()`  

## Methods

- `private <OnCreate>b__31_0() : Unity.Entities.Entity`  
- `private <OnCreate>b__31_1() : Unity.Entities.Entity`  
- `private <OnCreate>b__31_2() : System.Boolean`  
- `private <UpdateStackedStatus>b__53_0(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Boolean`  
- `private AddStat(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Boolean onlyTracker) : System.Void`  
- `private BindCategories(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindData(Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  
- `private BindGroups(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity parent) : System.Void`  
- `private BindSelectedStatistics(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindUnlockingRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  
- `private CacheChildren(Unity.Entities.Entity parentEntity, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache) : System.Void`  
- `private CacheParameterChildren(Unity.Entities.Entity parent, System.Boolean locked, Game.Prefabs.StatisticsData statisticsData, Game.Prefabs.PrefabData prefabData, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache) : System.Void`  
- `private CheckActiveCategory(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  
- `private CheckActiveGroup(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  
- `private ClearActive() : System.Void`  
- `private ClearStats() : System.Void`  
- `private DeepRemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  
- `private EnsureDataSize(Unity.Collections.NativeArray<System.Int64> data) : Unity.Collections.NativeArray<System.Int64>`  
- `private GetDataPoints(System.Int32 range, System.Int32 samples, Unity.Collections.NativeArray<System.Int64> data, Game.Common.TimeData timeData) : Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint>`  
- `private GetSampleInterval(System.Int32 range) : System.Int32`  
- `private GetSortedCategories() : Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+StatCategory>`  
- `private GetStatisticData(Game.UI.InGame.StatisticsUISystem+StatItem stat) : Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnStatisticsUpdated() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ProcessAddStat(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  
- `private ProcessAddStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  
- `private RemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Boolean keepTracker) : System.Void`  
- `private RemoveStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  
- `private RemoveStatParent(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  
- `private SetSampleRange(System.Int32 range) : System.Void`  
- `private TryAddChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache) : System.Boolean`  
- `private UpdateStackedStatus() : System.Void`  
- `private UpdateStats() : System.Void`  

## Nested types

- `Game.UI.InGame.StatisticsUISystem+StatCategory`  
- `Game.UI.InGame.StatisticsUISystem+DataPoint`  
- `Game.UI.InGame.StatisticsUISystem+StatItem`  
- `Game.UI.InGame.StatisticsUISystem+<>c`  
- `Game.UI.InGame.StatisticsUISystem+<>c__DisplayClass56_0`  
- `Game.UI.InGame.StatisticsUISystem+<>c__DisplayClass57_0`  

