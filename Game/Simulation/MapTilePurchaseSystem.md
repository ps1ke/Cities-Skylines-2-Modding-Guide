# Game.Simulation.MapTilePurchaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IMapTilePurchaseSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapTilePurchaseSystem : Game.GameSystemBase, Game.Simulation.IMapTilePurchaseSystem
{
    private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Areas.MapTileSystem m_MapTileSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_SelectionQuery;
    private Unity.Entities.EntityQuery m_OwnedTileQuery;
    private Unity.Entities.EntityQuery m_LockedMapTilesQuery;
    private Unity.Entities.EntityQuery m_UnlockedMilestoneQuery;
    private Unity.Entities.EntityQuery m_LockedMilestoneQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Collections.NativeArray<System.Single> m_FeatureAmounts;
    private System.Single m_Cost;
    private System.Single m_Upkeep;
    private Game.Simulation.TilePurchaseErrorFlags <status>k__BackingField;
    private Game.Simulation.MapTilePurchaseSystem+TypeHandle __TypeHandle;
    private static readonly System.Double kMapTileSizeModifier;
    private static readonly System.Double kResourceModifier;
    private static readonly System.Int32 kAutoUnlockedTiles;
    private static readonly System.Double[] kMapFeatureBaselineModifiers;

    public Game.Simulation.TilePurchaseErrorFlags status { get; private set; }
    public System.Boolean selecting { get; set; }
    public System.Int32 cost { get; }
    public System.Int32 upkeep { get; }

    public MapTilePurchaseSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Int32 CalculateOwnedTiles();
    private System.Single CalculateOwnedTilesCost();
    public System.Int32 CalculateOwnedTilesUpkeep();
    public System.Int32 GetAvailableTiles();
    private System.Double GetBaselineModifier(System.Int32 mapFeature);
    public System.Single GetFeatureAmount(Game.Areas.MapFeature feature);
    public System.Single GetMapTileUpkeepCostMultiplier(System.Int32 tileCount);
    public System.Boolean GetMapTileUpkeepEnabled();
    public System.Int32 GetSelectedTileCount();
    public System.Boolean IsMilestonesLeft();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PurchaseSelection();
    private System.Boolean TryGetSelections(System.Boolean isReadOnly, Unity.Entities.DynamicBuffer`1[[Game.Tools.SelectionElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& selections);
    public System.Void UnlockMapTiles();
    public static System.Void UnlockTile(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity area);
    private System.Void UpdateStatus();
}
```


## Fields

- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  

```csharp
private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Areas.MapTileSystem m_MapTileSystem`  

```csharp
private Game.Areas.MapTileSystem m_MapTileSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_SelectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_SelectionQuery;
```

- `private Unity.Entities.EntityQuery m_OwnedTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnedTileQuery;
```

- `private Unity.Entities.EntityQuery m_LockedMapTilesQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedMapTilesQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedMilestoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedMilestoneQuery;
```

- `private Unity.Entities.EntityQuery m_LockedMilestoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedMilestoneQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_FeatureAmounts`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_FeatureAmounts;
```

- `private System.Single m_Cost`  

```csharp
private System.Single m_Cost;
```

- `private System.Single m_Upkeep`  

```csharp
private System.Single m_Upkeep;
```

- `private Game.Simulation.TilePurchaseErrorFlags <status>k__BackingField`  

```csharp
private Game.Simulation.TilePurchaseErrorFlags <status>k__BackingField;
```

- `private Game.Simulation.MapTilePurchaseSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.MapTilePurchaseSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Double kMapTileSizeModifier`  

```csharp
private static readonly System.Double kMapTileSizeModifier;
```

- `private static readonly System.Double kResourceModifier`  

```csharp
private static readonly System.Double kResourceModifier;
```

- `private static readonly System.Int32 kAutoUnlockedTiles`  

```csharp
private static readonly System.Int32 kAutoUnlockedTiles;
```

- `private static readonly System.Double[] kMapFeatureBaselineModifiers`  

```csharp
private static readonly System.Double[] kMapFeatureBaselineModifiers;
```


## Properties

- `public Game.Simulation.TilePurchaseErrorFlags status { get; private set }`  

```csharp
public Game.Simulation.TilePurchaseErrorFlags status { get; private set; }
```

- `public System.Boolean selecting { get; set }`  

```csharp
public System.Boolean selecting { get; set; }
```

- `public System.Int32 cost { get }`  

```csharp
public System.Int32 cost { get; }
```

- `public System.Int32 upkeep { get }`  

```csharp
public System.Int32 upkeep { get; }
```


## Constructors

- `public MapTilePurchaseSystem()`  

```csharp
[Preserve]
	public MapTilePurchaseSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private CalculateOwnedTiles() : System.Int32`  

```csharp
private int CalculateOwnedTiles()
	{
		return m_OwnedTileQuery.CalculateEntityCountWithoutFiltering();
	}
```

- `private CalculateOwnedTilesCost() : System.Single`  

```csharp
private float CalculateOwnedTilesCost()
	{
		ComponentLookup<PrefabRef> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<TilePurchaseCostFactor> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TilePurchaseCostFactor_RO_ComponentLookup, ref base.CheckedStateRef);
		NativeList<Entity> startTiles = m_MapTileSystem.GetStartTiles();
		NativeArray<Entity> nativeArray;
		if (TryGetSelections(isReadOnly: true, out var selections) && selections.Length != 0)
		{
			nativeArray = new NativeArray<Entity>(selections.Length, Allocator.TempJob);
			for (int i = 0; i < selections.Length; i++)
			{
				nativeArray[i] = selections[i].m_Entity;
			}
		}
		else
		{
			nativeArray = m_OwnedTileQuery.ToEntityArray(Allocator.TempJob);
		}
		float num = 0f;
		for (int j = 0; j < nativeArray.Length; j++)
		{
			if (startTiles.Contains(nativeArray[j]) || !base.EntityManager.TryGetBuffer(nativeArray[j], isReadOnly: true, out DynamicBuffer<MapFeatureElement> buffer))
			{
				continue;
			}
			Entity prefab = componentLookup[nativeArray[j]].m_Prefab;
			float amount = componentLookup2[prefab].m_Amount;
			if (base.EntityManager.TryGetBuffer(prefab, isReadOnly: true, out DynamicBuffer<MapFeatureData> buffer2))
			{
				for (int k = 0; k < buffer.Length; k++)
				{
					float amount2 = buffer[k].m_Amount;
					m_FeatureAmounts[k] += amount2;
					double baselineModifier = GetBaselineModifier(k);
					num += (float)((double)amount2 * baselineModifier * 10.0 * (double)buffer2[k].m_Cost * (double)amount);
				}
			}
		}
		nativeArray.Dispose();
		return num;
	}
```

- `public CalculateOwnedTilesUpkeep() : System.Int32`  

```csharp
public int CalculateOwnedTilesUpkeep()
	{
		return Mathf.RoundToInt(CalculateOwnedTilesCost() * GetMapTileUpkeepCostMultiplier(CalculateOwnedTiles()));
	}
```

- `public GetAvailableTiles() : System.Int32`  

```csharp
public int GetAvailableTiles()
	{
		int num = CalculateOwnedTiles();
		int num2 = kAutoUnlockedTiles;
		NativeArray<MilestoneData> nativeArray = m_UnlockedMilestoneQuery.ToComponentDataArray<MilestoneData>(Allocator.Temp);
		try
		{
			foreach (MilestoneData item in nativeArray)
			{
				num2 += item.m_MapTiles;
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		return Mathf.Max(num2 - num, 0);
	}
```

- `private GetBaselineModifier(System.Int32 mapFeature) : System.Double`  

```csharp
private double GetBaselineModifier(int mapFeature)
	{
		if (mapFeature >= 0 && mapFeature < kMapFeatureBaselineModifiers.Length)
		{
			return kMapFeatureBaselineModifiers[mapFeature];
		}
		return 1.0;
	}
```

- `public GetFeatureAmount(Game.Areas.MapFeature feature) : System.Single`  

```csharp
public float GetFeatureAmount(MapFeature feature)
	{
		float num = m_FeatureAmounts[(int)feature];
		if (feature != MapFeature.FertileLand)
		{
			return num;
		}
		return m_NaturalResourceSystem.ResourceAmountToArea(num);
	}
```

- `public GetMapTileUpkeepCostMultiplier(System.Int32 tileCount) : System.Single`  

```csharp
public float GetMapTileUpkeepCostMultiplier(int tileCount)
	{
		if (tileCount <= kAutoUnlockedTiles)
		{
			return 0f;
		}
		return m_EconomyParameterQuery.GetSingleton<EconomyParameterData>().m_MapTileUpkeepCostMultiplier.Evaluate(tileCount);
	}
```

- `public GetMapTileUpkeepEnabled() : System.Boolean`  

```csharp
public bool GetMapTileUpkeepEnabled()
	{
		if (m_CityConfigurationSystem.unlockMapTiles)
		{
			return false;
		}
		EconomyParameterData singleton = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>();
		float num = 0f;
		for (int i = 0; i <= 100; i += 10)
		{
			num = singleton.m_MapTileUpkeepCostMultiplier.Evaluate(i);
			if (num > 0f)
			{
				return true;
			}
		}
		return num != 0f;
	}
```

- `public GetSelectedTileCount() : System.Int32`  

```csharp
public int GetSelectedTileCount()
	{
		if (TryGetSelections(isReadOnly: true, out var selections))
		{
			return selections.Length;
		}
		return 0;
	}
```

- `public IsMilestonesLeft() : System.Boolean`  

```csharp
public bool IsMilestonesLeft()
	{
		NativeArray<MilestoneData> nativeArray = m_LockedMilestoneQuery.ToComponentDataArray<MilestoneData>(Allocator.Temp);
		try
		{
			return nativeArray.Length != 0;
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SelectionToolSystem = base.World.GetOrCreateSystemManaged<SelectionToolSystem>();
		m_DefaultToolSystem = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		m_MapTileSystem = base.World.GetOrCreateSystemManaged<MapTileSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_SelectionQuery = GetEntityQuery(ComponentType.ReadOnly<SelectionElement>());
		m_OwnedTileQuery = GetEntityQuery(ComponentType.ReadOnly<MapTile>(), ComponentType.Exclude<Native>());
		m_LockedMapTilesQuery = GetEntityQuery(ComponentType.ReadWrite<MapTile>(), ComponentType.ReadOnly<Native>(), ComponentType.ReadOnly<Area>());
		m_UnlockedMilestoneQuery = GetEntityQuery(ComponentType.ReadOnly<MilestoneData>(), ComponentType.Exclude<Locked>());
		m_LockedMilestoneQuery = GetEntityQuery(ComponentType.ReadOnly<MilestoneData>(), ComponentType.ReadOnly<Locked>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_FeatureAmounts = new NativeArray<float>(9, Allocator.Persistent);
		RequireForUpdate(m_EconomyParameterQuery);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		m_FeatureAmounts.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		UpdateStatus();
	}
```

- `public PurchaseSelection() : System.Void`  

```csharp
public void PurchaseSelection()
	{
		UpdateStatus();
		if (status != TilePurchaseErrorFlags.None)
		{
			return;
		}
		PlayerMoney componentData = base.EntityManager.GetComponentData<PlayerMoney>(m_CitySystem.City);
		componentData.Subtract(cost);
		base.EntityManager.SetComponentData(m_CitySystem.City, componentData);
		if (!TryGetSelections(isReadOnly: false, out var selections))
		{
			return;
		}
		NativeArray<SelectionElement> nativeArray = selections.ToNativeArray(Allocator.Temp);
		try
		{
			selections.Clear();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity entity = nativeArray[i].m_Entity;
				UnlockTile(base.EntityManager, entity);
			}
			PlatformManager.instance.IndicateAchievementProgress(new AchievementId[2]
			{
				Game.Achievements.Achievements.TheExplorer,
				Game.Achievements.Achievements.EverythingTheLightTouches
			}, CalculateOwnedTiles());
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `private TryGetSelections(System.Boolean isReadOnly, Unity.Entities.DynamicBuffer`1[[Game.Tools.SelectionElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& selections) : System.Boolean`  

```csharp
private bool TryGetSelections(bool isReadOnly, out DynamicBuffer<SelectionElement> selections)
	{
		if (selecting && !m_SelectionQuery.IsEmptyIgnoreFilter)
		{
			Entity singletonEntity = m_SelectionQuery.GetSingletonEntity();
			if (base.EntityManager.TryGetBuffer(singletonEntity, isReadOnly, out selections))
			{
				return true;
			}
		}
		selections = default(DynamicBuffer<SelectionElement>);
		return false;
	}
```

- `public UnlockMapTiles() : System.Void`  

```csharp
public void UnlockMapTiles()
	{
		if (!m_LockedMapTilesQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray = m_LockedMapTilesQuery.ToEntityArray(Allocator.Temp);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity area = nativeArray[i];
				UnlockTile(base.EntityManager, area);
			}
			nativeArray.Dispose();
		}
	}
```

- `public static UnlockTile(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity area) : System.Void`  

```csharp
public static void UnlockTile(EntityManager entityManager, Entity area)
	{
		if (entityManager.HasComponent<Native>(area))
		{
			entityManager.RemoveComponent<Native>(area);
			entityManager.AddComponentData(area, default(Updated));
		}
	}
```

- `private UpdateStatus() : System.Void`  

```csharp
private void UpdateStatus()
	{
		m_FeatureAmounts.Fill(0f);
		m_Cost = 0f;
		m_Upkeep = 0f;
		int availableTiles = GetAvailableTiles();
		if (availableTiles == 0)
		{
			status = (IsMilestonesLeft() ? TilePurchaseErrorFlags.NoCurrentlyAvailable : TilePurchaseErrorFlags.NoAvailable);
			return;
		}
		if (!TryGetSelections(isReadOnly: true, out var selections) || selections.Length == 0)
		{
			status = TilePurchaseErrorFlags.NoSelection;
			return;
		}
		status = TilePurchaseErrorFlags.None;
		ComponentLookup<PrefabRef> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<TilePurchaseCostFactor> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TilePurchaseCostFactor_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Native> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<MapTile> componentLookup4 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_MapTile_RO_ComponentLookup, ref base.CheckedStateRef);
		NativeList<float> list = new NativeList<float>(Allocator.Temp);
		int num = 0;
		int num2 = CalculateOwnedTiles();
		float num3 = CalculateOwnedTilesCost();
		float num4 = num3 * GetMapTileUpkeepCostMultiplier(num2);
		float num5 = num3;
		for (int i = 0; i < selections.Length; i++)
		{
			Entity entity = selections[i].m_Entity;
			if (!componentLookup4.HasComponent(entity) || !componentLookup3.HasComponent(entity))
			{
				continue;
			}
			num++;
			if (!base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<MapFeatureElement> buffer))
			{
				continue;
			}
			Entity prefab = componentLookup[entity].m_Prefab;
			float amount = componentLookup2[prefab].m_Amount;
			if (base.EntityManager.TryGetBuffer(prefab, isReadOnly: true, out DynamicBuffer<MapFeatureData> buffer2))
			{
				float value = 0f;
				for (int j = 0; j < buffer.Length; j++)
				{
					float amount2 = buffer[j].m_Amount;
					m_FeatureAmounts[j] += amount2;
					double baselineModifier = GetBaselineModifier(j);
					value += (float)((double)amount2 * baselineModifier * 10.0 * (double)buffer2[j].m_Cost * (double)amount);
					num5 += (float)((double)amount2 * baselineModifier * 10.0 * (double)buffer2[j].m_Cost * (double)amount);
				}
				list.Add(in value);
			}
		}
		list.Sort();
		for (int k = 0; k < list.Length; k++)
		{
			m_Cost += list[list.Length - k - 1] * (float)(num2 + k);
		}
		list.Dispose();
		m_Upkeep = num5 * GetMapTileUpkeepCostMultiplier(num2 + num) - num4;
		if (num > 0 && num > availableTiles)
		{
			status |= TilePurchaseErrorFlags.InsufficientPermits;
		}
		if (cost > m_CitySystem.moneyAmount)
		{
			status |= TilePurchaseErrorFlags.InsufficientFunds;
		}
	}
```


## Nested types

- `Game.Simulation.MapTilePurchaseSystem+TypeHandle`  

