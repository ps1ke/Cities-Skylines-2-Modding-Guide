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
[Preserve]
	public StatisticsUISystem()
	{
	}
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
private void AddStat(StatItem stat, bool onlyTracker)
	{
		if (!m_SelectedStatisticsTracker.Contains(stat))
		{
			m_SelectedStatisticsTracker.Add(stat);
		}
		if (!onlyTracker && !m_SelectedStatistics.Contains(stat))
		{
			m_SelectedStatistics.Add(stat);
		}
	}
```

- `private BindCategories(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindCategories(IJsonWriter binder)
	{
		NativeList<StatCategory> sortedCategories = GetSortedCategories();
		binder.ArrayBegin(sortedCategories.Length);
		for (int i = 0; i < sortedCategories.Length; i++)
		{
			StatCategory statCategory = sortedCategories[i];
			PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(statCategory.m_PrefabData);
			bool value = base.EntityManager.HasEnabledComponent<Locked>(statCategory.m_Entity);
			binder.TypeBegin("statistics.StatCategory");
			binder.PropertyName("entity");
			binder.Write(statCategory.m_Entity);
			binder.PropertyName("key");
			binder.Write(prefab.name);
			binder.PropertyName("locked");
			binder.Write(value);
			binder.TypeEnd();
		}
		binder.ArrayEnd();
	}
```

- `private BindData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindData(IJsonWriter binder, StatItem stat)
	{
		binder.TypeBegin("statistics.ChartDataSets");
		binder.PropertyName("label");
		binder.Write(stat.key);
		binder.PropertyName("data");
		NativeList<DataPoint> statisticData = GetStatisticData(stat);
		binder.ArrayBegin(statisticData.Length);
		for (int i = 0; i < statisticData.Length; i++)
		{
			binder.Write(statisticData[i]);
		}
		binder.ArrayEnd();
		binder.PropertyName("borderColor");
		binder.Write(stat.color.ToHexCode());
		binder.PropertyName("backgroundColor");
		binder.Write($"rgba({Mathf.RoundToInt(stat.color.r * 255f)}, {Mathf.RoundToInt(stat.color.g * 255f)}, {Mathf.RoundToInt(stat.color.b * 255f)}, 0.5)");
		binder.PropertyName("fill");
		if (m_Stacked)
		{
			binder.Write("origin");
		}
		else
		{
			binder.Write("false");
		}
		binder.TypeEnd();
	}
```

- `private BindData(Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private void BindData(IJsonWriter binder, StatItem stat)
	{
		binder.TypeBegin("statistics.ChartDataSets");
		binder.PropertyName("label");
		binder.Write(stat.key);
		binder.PropertyName("data");
		NativeList<DataPoint> statisticData = GetStatisticData(stat);
		binder.ArrayBegin(statisticData.Length);
		for (int i = 0; i < statisticData.Length; i++)
		{
			binder.Write(statisticData[i]);
		}
		binder.ArrayEnd();
		binder.PropertyName("borderColor");
		binder.Write(stat.color.ToHexCode());
		binder.PropertyName("backgroundColor");
		binder.Write($"rgba({Mathf.RoundToInt(stat.color.r * 255f)}, {Mathf.RoundToInt(stat.color.g * 255f)}, {Mathf.RoundToInt(stat.color.b * 255f)}, 0.5)");
		binder.PropertyName("fill");
		if (m_Stacked)
		{
			binder.Write("origin");
		}
		else
		{
			binder.Write("false");
		}
		binder.TypeEnd();
	}
```

- `private BindGroups(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity parent) : System.Void`  

```csharp
private void BindGroups(IJsonWriter binder, Entity parent)
	{
		CacheChildren(parent, m_GroupCache);
		binder.ArrayBegin(m_GroupCache.Count);
		for (int i = 0; i < m_GroupCache.Count; i++)
		{
			binder.Write(m_GroupCache[i]);
		}
		binder.ArrayEnd();
	}
```

- `private BindSelectedStatistics(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindSelectedStatistics(IJsonWriter binder)
	{
		binder.ArrayBegin(m_SelectedStatistics.Count);
		for (int i = 0; i < m_SelectedStatistics.Count; i++)
		{
			StatItem value = m_SelectedStatistics[i];
			binder.Write(value);
		}
		binder.ArrayEnd();
	}
```

- `private BindUnlockingRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
private void BindUnlockingRequirements(IJsonWriter writer, Entity prefabEntity)
	{
		m_PrefabUISystem.BindPrefabRequirements(writer, prefabEntity);
	}
```

- `private CacheChildren(Unity.Entities.Entity parentEntity, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache) : System.Void`  

```csharp
private void CacheChildren(Entity parentEntity, List<StatItem> cache)
	{
		cache.Clear();
		bool flag = base.EntityManager.HasComponent<UIStatisticsCategoryData>(parentEntity);
		StatisticsData component4;
		PrefabData component5;
		if (base.EntityManager.TryGetBuffer(parentEntity, isReadOnly: true, out DynamicBuffer<UIGroupElement> buffer))
		{
			NativeList<UIObjectInfo> sortedObjects = UIObjectInfo.GetSortedObjects(base.EntityManager, buffer, Allocator.TempJob);
			for (int i = 0; i < sortedObjects.Length; i++)
			{
				Entity category = Entity.Null;
				Entity entity = Entity.Null;
				Entity entity2 = sortedObjects[i].entity;
				PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(entity2);
				StatisticUnitType unitType = StatisticUnitType.None;
				StatisticType statisticType = StatisticType.Invalid;
				bool locked = base.EntityManager.HasEnabledComponent<Locked>(entity2);
				bool isSubgroup = (!flag && base.EntityManager.HasComponent<UIStatisticsGroupData>(entity2)) || (prefab is ParametricStatistic parametricStatistic && parametricStatistic.GetParameters().Count() > 1);
				bool stacked = true;
				Color color = new Color(0f, 0f, 0f, 0f);
				if (!m_MapTilePurchaseSystem.GetMapTileUpkeepEnabled() && prefab.name == "MapTileUpkeep")
				{
					continue;
				}
				if (base.EntityManager.TryGetComponent<StatisticsData>(entity2, out var component))
				{
					if (m_CityConfigurationSystem.unlimitedMoney && (component.m_StatisticType == StatisticType.Money || prefab.name == "LoanInterest"))
					{
						continue;
					}
					unitType = component.m_UnitType;
					statisticType = component.m_StatisticType;
					entity = component.m_Group;
					category = component.m_Category;
					color = component.m_Color;
					stacked = component.m_Stacked;
				}
				if (base.EntityManager.TryGetComponent<UIStatisticsGroupData>(entity2, out var component2) && base.EntityManager.TryGetComponent<UIObjectData>(entity2, out var component3))
				{
					entity = ((component3.m_Group == component2.m_Category) ? entity2 : component3.m_Group);
					unitType = component2.m_UnitType;
					category = component2.m_Category;
					color = component2.m_Color;
					stacked = component2.m_Stacked;
				}
				cache.Add(new StatItem(i, category, entity, entity2, (int)statisticType, unitType, 0, prefab.name, color, locked, flag, isSubgroup, stacked));
			}
			sortedObjects.Dispose();
		}
		else if (base.EntityManager.TryGetComponent<StatisticsData>(parentEntity, out component4) && base.EntityManager.TryGetComponent<PrefabData>(parentEntity, out component5))
		{
			bool locked2 = base.EntityManager.HasEnabledComponent<Locked>(parentEntity);
			CacheParameterChildren(parentEntity, locked2, component4, component5, cache);
		}
	}
```

- `private CacheParameterChildren(Unity.Entities.Entity parent, System.Boolean locked, Game.Prefabs.StatisticsData statisticsData, Game.Prefabs.PrefabData prefabData, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache) : System.Void`  

```csharp
private void CacheParameterChildren(Entity parent, bool locked, StatisticsData statisticsData, PrefabData prefabData, List<StatItem> cache)
	{
		ParametricStatistic prefab = m_PrefabSystem.GetPrefab<ParametricStatistic>(prefabData);
		if (base.EntityManager.TryGetBuffer(parent, isReadOnly: true, out DynamicBuffer<StatisticParameterData> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				cache.Add(new StatItem(i, statisticsData.m_Category, (statisticsData.m_Group == Entity.Null) ? parent : statisticsData.m_Group, parent, (int)prefab.m_StatisticsType, prefab.m_UnitType, i, prefab.name + prefab.GetParameterName(buffer[i].m_Value), buffer[i].m_Color, locked, isGroup: false, isSubgroup: false, statisticsData.m_Stacked));
			}
		}
	}
```

- `private CheckActiveCategory(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private void CheckActiveCategory(StatItem stat)
	{
		if (stat.category != m_ActiveCategory)
		{
			m_SelectedStatistics.Clear();
			m_SelectedStatisticsTracker.Clear();
			m_ActiveCategory = stat.category;
			m_ActiveCategoryBinding.Update();
		}
	}
```

- `private CheckActiveGroup(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private void CheckActiveGroup(StatItem stat)
	{
		if (m_ActiveGroup == Entity.Null || stat.isGroup || stat.group != m_ActiveGroup)
		{
			m_SelectedStatistics.Clear();
			m_SelectedStatisticsTracker.Clear();
			m_ActiveGroup = (stat.isGroup ? stat.entity : stat.group);
			m_ActiveGroupBinding.Update();
		}
	}
```

- `private ClearActive() : System.Void`  

```csharp
private void ClearActive()
	{
		m_ActiveGroup = Entity.Null;
		m_ActiveGroupBinding.Update();
		m_ActiveCategory = Entity.Null;
		m_ActiveCategoryBinding.Update();
	}
```

- `private ClearStats() : System.Void`  

```csharp
private void ClearStats()
	{
		m_SelectedStatistics.Clear();
		m_SelectedStatisticsTracker.Clear();
		UpdateStats();
		ClearActive();
	}
```

- `private DeepRemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private void DeepRemoveStat(StatItem stat)
	{
		if (!m_SelectedStatisticsTracker.Contains(stat))
		{
			int num = m_SelectedStatisticsTracker.FindIndex((StatItem s) => s.entity == stat.group);
			int num2 = m_SelectedStatisticsTracker.FindIndex((StatItem s) => s.entity == stat.entity && s.isSubgroup);
			if (num >= 0)
			{
				StatItem stat2 = m_SelectedStatisticsTracker[num];
				if (num2 >= 0)
				{
					StatItem stat3 = m_SelectedStatisticsTracker[num2];
					DeepRemoveStat(stat2);
					ProcessAddStat(stat3);
				}
				else
				{
					DeepRemoveStat(stat2);
				}
			}
		}
		int num3 = m_SelectedStatisticsTracker.Count((StatItem s) => s.isSubgroup);
		RemoveStat(stat, keepTracker: false);
		RemoveStatChildren(stat);
		int num4 = m_SelectedStatisticsTracker.Count((StatItem s) => s.isSubgroup);
		if (num3 > 1 && num4 == 1)
		{
			StatItem stat4 = m_SelectedStatisticsTracker.First((StatItem s) => s.isSubgroup);
			RemoveStat(stat4, keepTracker: false);
			ProcessAddStat(stat4);
		}
		if (m_ClearActive && m_SelectedStatistics.Count == 0 && m_SelectedStatisticsTracker.Count <= 1)
		{
			ClearStats();
		}
		else
		{
			UpdateStats();
		}
		m_ClearActive = true;
		UpdateStackedStatus();
	}
```

- `private EnsureDataSize(Unity.Collections.NativeArray<System.Int64> data) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
private NativeArray<long> EnsureDataSize(NativeArray<long> data)
	{
		if (data.Length < m_CityStatisticsSystem.sampleCount)
		{
			NativeArray<long> result = CollectionHelper.CreateNativeArray<long>(m_CityStatisticsSystem.sampleCount, Allocator.Temp);
			int num = 0;
			for (int i = 0; i < result.Length; i++)
			{
				if (i < result.Length - data.Length)
				{
					result[i] = 0L;
				}
				else
				{
					result[i] = data[num++];
				}
			}
			return result;
		}
		return data;
	}
```

- `private GetDataPoints(System.Int32 range, System.Int32 samples, Unity.Collections.NativeArray<System.Int64> data, Game.Common.TimeData timeData) : Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint>`  

```csharp
private NativeList<DataPoint> GetDataPoints(int range, int samples, NativeArray<long> data, TimeData timeData)
	{
		int sampleInterval = GetSampleInterval(range);
		NativeList<DataPoint> result = new NativeList<DataPoint>(data.Length / sampleInterval, Allocator.Temp);
		int num = 0;
		uint num2 = (uint)math.max((int)(m_CityStatisticsSystem.GetSampleFrameIndex(samples - range) - timeData.m_FirstFrame), 0);
		DataPoint value = new DataPoint
		{
			x = (uint)math.max(num2, m_TimeUISystem.GetTicks() - 8192 * m_SampleRange),
			y = data[0]
		};
		result.Add(in value);
		if (data.Length > 2)
		{
			for (int i = 1; i < data.Length - 1; i++)
			{
				if (num % sampleInterval == 0)
				{
					uint sampleFrameIndex = m_CityStatisticsSystem.GetSampleFrameIndex(samples - range + i);
					value = new DataPoint
					{
						x = sampleFrameIndex - timeData.m_FirstFrame,
						y = data[i]
					};
					result.Add(in value);
				}
				num++;
			}
		}
		m_CityStatisticsSystem.GetSampleFrameIndex(samples);
		value = new DataPoint
		{
			x = (uint)(m_TimeUISystem.GetTicks() + 182 + 1)
		};
		value.y = data[data.Length - 1];
		result.Add(in value);
		return result;
	}
```

- `private GetSampleInterval(System.Int32 range) : System.Int32`  

```csharp
private int GetSampleInterval(int range)
	{
		int num = 32;
		if (range <= num)
		{
			return 1;
		}
		int num2 = num - 2;
		return Math.Max(1, (range - 2) / num2);
	}
```

- `private GetSortedCategories() : Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+StatCategory>`  

```csharp
private NativeList<StatCategory> GetSortedCategories()
	{
		NativeArray<Entity> nativeArray = m_StatisticsCategoryQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<UIObjectData> nativeArray2 = m_StatisticsCategoryQuery.ToComponentDataArray<UIObjectData>(Allocator.TempJob);
		NativeArray<PrefabData> nativeArray3 = m_StatisticsCategoryQuery.ToComponentDataArray<PrefabData>(Allocator.TempJob);
		NativeList<StatCategory> nativeList = new NativeList<StatCategory>(nativeArray.Length, Allocator.Temp);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			nativeList.Add(new StatCategory(nativeArray[i], nativeArray2[i], nativeArray3[i]));
		}
		nativeArray.Dispose();
		nativeArray2.Dispose();
		nativeArray3.Dispose();
		nativeList.Sort();
		return nativeList;
	}
```

- `private GetStatisticData(Game.UI.InGame.StatisticsUISystem+StatItem stat) : Unity.Collections.NativeList<Game.UI.InGame.StatisticsUISystem+DataPoint>`  

```csharp
private NativeList<DataPoint> GetStatisticData(StatItem stat)
	{
		m_CityStatisticsSystem.CompleteWriters();
		StatisticsPrefab prefab = m_PrefabSystem.GetPrefab<StatisticsPrefab>(stat.entity);
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		TimeData singleton = TimeData.GetSingleton(m_TimeDataQuery);
		int sampleCount = m_CityStatisticsSystem.sampleCount;
		int num = math.min(m_SampleRange + 1, sampleCount);
		if (sampleCount <= 1)
		{
			NativeList<DataPoint> result = new NativeList<DataPoint>(1, Allocator.Temp);
			DataPoint value = new DataPoint
			{
				x = singleton.m_FirstFrame,
				y = 0L
			};
			result.Add(in value);
			return result;
		}
		NativeArray<long> data = CollectionHelper.CreateNativeArray<long>(num, Allocator.Temp);
		StatisticParameterData[] array = ((prefab is ParametricStatistic parametricStatistic) ? parametricStatistic.GetParameters().ToArray() : new StatisticParameterData[1]
		{
			new StatisticParameterData
			{
				m_Value = 0
			}
		});
		if (stat.isSubgroup)
		{
			for (int i = 0; i < array.Length; i++)
			{
				int value2 = array[i].m_Value;
				NativeArray<long> statisticDataArrayLong = m_CityStatisticsSystem.GetStatisticDataArrayLong((StatisticType)stat.statisticType, value2);
				statisticDataArrayLong = EnsureDataSize(statisticDataArrayLong);
				for (int j = 0; j < num; j++)
				{
					long num2 = statisticDataArrayLong[statisticDataArrayLong.Length - num + j];
					if (stat.statisticType == 4 && prefab is ResourceStatistic resourceStatistic)
					{
						Resource resource = EconomyUtils.GetResource(resourceStatistic.m_Resources[i].m_Resource);
						Entity entity = prefabs[resource];
						ResourceData componentData = base.EntityManager.GetComponentData<ResourceData>(entity);
						num2 *= (int)EconomyUtils.GetMarketPrice(componentData);
					}
					data[j] += num2;
				}
			}
		}
		else
		{
			int value3 = array[stat.parameterIndex].m_Value;
			NativeArray<long> statisticDataArrayLong2 = m_CityStatisticsSystem.GetStatisticDataArrayLong((StatisticType)stat.statisticType, value3);
			NativeArray<long> nativeArray = CollectionHelper.CreateNativeArray<long>(0, Allocator.Temp);
			if (stat.statisticType == 16 || stat.statisticType == 15)
			{
				nativeArray = m_CityStatisticsSystem.GetStatisticDataArrayLong(StatisticType.Population);
				nativeArray = EnsureDataSize(nativeArray);
			}
			statisticDataArrayLong2 = EnsureDataSize(statisticDataArrayLong2);
			for (int k = 0; k < num; k++)
			{
				long num3 = statisticDataArrayLong2[statisticDataArrayLong2.Length - num + k];
				if (stat.statisticType == 4 && prefab is ResourceStatistic resourceStatistic2)
				{
					Resource resource2 = EconomyUtils.GetResource(resourceStatistic2.m_Resources[stat.parameterIndex].m_Resource);
					Entity entity2 = prefabs[resource2];
					ResourceData componentData2 = base.EntityManager.GetComponentData<ResourceData>(entity2);
					num3 *= (int)EconomyUtils.GetMarketPrice(componentData2);
				}
				if (nativeArray.Length > 0 && (stat.statisticType == 16 || stat.statisticType == 15))
				{
					long num4 = nativeArray[nativeArray.Length - num + k];
					if (num4 > 0)
					{
						num3 /= num4;
					}
				}
				data[k] += num3;
			}
		}
		return GetDataPoints(num, sampleCount, data, singleton);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_StatisticsCategoryQuery = GetEntityQuery(ComponentType.ReadOnly<UIObjectData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<UIStatisticsCategoryData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_UnlockedPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_GroupCache = new List<StatItem>();
		m_SubGroupCache = new List<StatItem>();
		m_SelectedStatistics = new List<StatItem>();
		m_SelectedStatisticsTracker = new List<StatItem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		ICityStatisticsSystem cityStatisticsSystem = m_CityStatisticsSystem;
		cityStatisticsSystem.eventStatisticsUpdated = (Action)Delegate.Combine(cityStatisticsSystem.eventStatisticsUpdated, new Action(OnStatisticsUpdated));
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_TimeUISystem = base.World.GetOrCreateSystemManaged<TimeUISystem>();
		m_MapTilePurchaseSystem = base.World.GetOrCreateSystemManaged<MapTilePurchaseSystem>();
		AddBinding(m_GroupsMapBinding = new RawMapBinding<Entity>("statistics", "groups", BindGroups));
		AddBinding(m_SampleRangeBinding = new ValueBinding<int>("statistics", "sampleRange", m_SampleRange));
		AddBinding(m_SampleCountBinding = new ValueBinding<int>("statistics", "sampleCount", m_CityStatisticsSystem.sampleCount));
		AddBinding(m_ActiveGroupBinding = new GetterValueBinding<Entity>("statistics", "activeGroup", () => m_ActiveGroup));
		AddBinding(m_ActiveCategoryBinding = new GetterValueBinding<Entity>("statistics", "activeCategory", () => m_ActiveCategory));
		AddBinding(m_StackedBinding = new GetterValueBinding<bool>("statistics", "stacked", () => m_Stacked));
		AddBinding(m_CategoriesBinding = new RawValueBinding("statistics", "categories", BindCategories));
		AddBinding(m_DataBinding = new RawValueBinding("statistics", "data", BindData));
		AddBinding(m_SelectedStatisticsBinding = new RawValueBinding("statistics", "selectedStatistics", BindSelectedStatistics));
		AddBinding(m_UnlockingRequirementsBinding = new RawMapBinding<Entity>("statistics", "unlockingRequirements", BindUnlockingRequirements));
		AddBinding(new GetterValueBinding<int>("statistics", "updatesPerDay", () => 32));
		AddBinding(new TriggerBinding<StatItem>("statistics", "addStat", ProcessAddStat, new ValueReader<StatItem>()));
		AddBinding(new TriggerBinding<StatItem>("statistics", "addStatChildren", ProcessAddStatChildren, new ValueReader<StatItem>()));
		AddBinding(new TriggerBinding<StatItem>("statistics", "removeStat", DeepRemoveStat, new ValueReader<StatItem>()));
		AddBinding(new TriggerBinding("statistics", "clearStats", ClearStats));
		AddBinding(new TriggerBinding<int>("statistics", "setSampleRange", SetSampleRange));
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		ICityStatisticsSystem cityStatisticsSystem = m_CityStatisticsSystem;
		cityStatisticsSystem.eventStatisticsUpdated = (Action)Delegate.Remove(cityStatisticsSystem.eventStatisticsUpdated, new Action(OnStatisticsUpdated));
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_SelectedStatistics.Clear();
		m_SampleRange = 32;
	}
```

- `private OnStatisticsUpdated() : System.Void`  

```csharp
private void OnStatisticsUpdated()
	{
		m_DataBinding.Update();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_SampleCountBinding.Update(m_CityStatisticsSystem.sampleCount);
		m_SampleRangeBinding.Update(m_SampleRange);
		int componentOrderVersion = base.EntityManager.GetComponentOrderVersion<UnlockRequirementData>();
		if (PrefabUtils.HasUnlockedPrefab<UIObjectData>(base.EntityManager, m_UnlockedPrefabQuery) || m_UnlockRequirementVersion != componentOrderVersion)
		{
			m_UnlockingRequirementsBinding.UpdateAll();
			m_GroupsMapBinding.UpdateAll();
			m_CategoriesBinding.Update();
		}
		m_UnlockRequirementVersion = componentOrderVersion;
	}
```

- `private ProcessAddStat(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private void ProcessAddStat(StatItem stat)
	{
		if (stat.locked)
		{
			return;
		}
		CheckActiveCategory(stat);
		CheckActiveGroup(stat);
		if (stat.isGroup)
		{
			AddStat(stat, onlyTracker: true);
			if (!TryAddChildren(stat, m_GroupCache))
			{
				m_SelectedStatistics.Add(stat);
			}
		}
		else if (stat.isSubgroup)
		{
			RemoveStatChildren(stat);
			AddStat(stat, onlyTracker: false);
		}
		else
		{
			RemoveStatParent(stat);
			AddStat(stat, onlyTracker: false);
		}
		UpdateStackedStatus();
		UpdateStats();
	}
```

- `private ProcessAddStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private void ProcessAddStatChildren(StatItem stat)
	{
		if (!stat.locked)
		{
			CheckActiveCategory(stat);
			CheckActiveGroup(stat);
			if (stat.isSubgroup)
			{
				RemoveStat(stat, keepTracker: true);
				TryAddChildren(stat, m_SubGroupCache);
			}
		}
	}
```

- `private RemoveStat(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Boolean keepTracker) : System.Void`  

```csharp
private void RemoveStat(StatItem stat, bool keepTracker)
	{
		m_SelectedStatistics.Remove(stat);
		if (!keepTracker)
		{
			m_SelectedStatisticsTracker.Remove(stat);
		}
	}
```

- `private RemoveStatChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private void RemoveStatChildren(StatItem stat)
	{
		if (stat.isGroup)
		{
			for (int num = m_SelectedStatistics.Count - 1; num >= 0; num--)
			{
				if (m_SelectedStatistics[num].group == stat.entity)
				{
					m_SelectedStatistics.RemoveAt(num);
				}
			}
			for (int num2 = m_SelectedStatisticsTracker.Count - 1; num2 >= 0; num2--)
			{
				if (m_SelectedStatisticsTracker[num2].group == stat.entity)
				{
					m_SelectedStatisticsTracker.RemoveAt(num2);
				}
			}
		}
		else
		{
			if (!stat.isSubgroup)
			{
				return;
			}
			for (int num3 = m_SelectedStatistics.Count - 1; num3 >= 0; num3--)
			{
				if (m_SelectedStatistics[num3].entity == stat.entity)
				{
					m_SelectedStatistics.RemoveAt(num3);
				}
			}
			for (int num4 = m_SelectedStatisticsTracker.Count - 1; num4 >= 0; num4--)
			{
				if (m_SelectedStatisticsTracker[num4].entity == stat.entity)
				{
					m_SelectedStatisticsTracker.RemoveAt(num4);
				}
			}
		}
	}
```

- `private RemoveStatParent(Game.UI.InGame.StatisticsUISystem+StatItem stat) : System.Void`  

```csharp
private void RemoveStatParent(StatItem stat)
	{
		int num = m_SelectedStatisticsTracker.FindIndex((StatItem s) => s.entity == stat.entity && s.isSubgroup);
		if (num != -1)
		{
			StatItem stat2 = m_SelectedStatisticsTracker[num];
			RemoveStat(stat2, keepTracker: true);
		}
	}
```

- `private SetSampleRange(System.Int32 range) : System.Void`  

```csharp
private void SetSampleRange(int range)
	{
		m_SampleRange = range;
		m_SampleRangeBinding.Update(m_SampleRange);
		UpdateStats();
	}
```

- `private TryAddChildren(Game.UI.InGame.StatisticsUISystem+StatItem stat, System.Collections.Generic.List<Game.UI.InGame.StatisticsUISystem+StatItem> cache) : System.Boolean`  

```csharp
private bool TryAddChildren(StatItem stat, List<StatItem> cache)
	{
		CacheChildren(stat.entity, cache);
		for (int i = 0; i < cache.Count; i++)
		{
			ProcessAddStat(cache[i]);
		}
		return cache.Count > 0;
	}
```

- `private UpdateStackedStatus() : System.Void`  

```csharp
private void UpdateStackedStatus()
	{
		if (m_SelectedStatisticsTracker.Count((StatItem stat) => stat.isSubgroup && stat.group == m_ActiveGroup) > 1 && base.EntityManager.TryGetComponent<UIStatisticsGroupData>(m_ActiveGroup, out var component))
		{
			m_Stacked = component.m_Stacked;
		}
		else if (m_SelectedStatisticsTracker.Count > 0)
		{
			m_Stacked = false;
			for (int num = 0; num < m_SelectedStatisticsTracker.Count; num++)
			{
				if (m_SelectedStatisticsTracker[num].stacked)
				{
					m_Stacked = true;
					break;
				}
			}
		}
		else
		{
			m_Stacked = false;
		}
		m_StackedBinding.Update();
	}
```

- `private UpdateStats() : System.Void`  

```csharp
private void UpdateStats()
	{
		m_SelectedStatistics.Sort();
		m_SelectedStatisticsBinding.Update();
		m_DataBinding.Update();
	}
```


## Nested types

- `Game.UI.InGame.StatisticsUISystem+StatCategory`  
- `Game.UI.InGame.StatisticsUISystem+DataPoint`  
- `Game.UI.InGame.StatisticsUISystem+StatItem`  
- `Game.UI.InGame.StatisticsUISystem+<>c`  
- `Game.UI.InGame.StatisticsUISystem+<>c__DisplayClass56_0`  
- `Game.UI.InGame.StatisticsUISystem+<>c__DisplayClass57_0`  

