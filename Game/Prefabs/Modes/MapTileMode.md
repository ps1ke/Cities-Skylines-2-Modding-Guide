# Game.Prefabs.Modes.MapTileMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MapTileMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.MapTilePrefab m_Prefab;
    public Game.Prefabs.MapTilePrefab+FeatureInfo[] m_MapFeatures;

    public MapTileMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.MapTilePrefab m_Prefab`  

```csharp
public Game.Prefabs.MapTilePrefab m_Prefab;
```

- `public Game.Prefabs.MapTilePrefab+FeatureInfo[] m_MapFeatures`  

```csharp
public Game.Prefabs.MapTilePrefab+FeatureInfo[] m_MapFeatures;
```


## Constructors

- `public MapTileMode()`  

```csharp
public MapTileMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		MapTilePrefab mapTilePrefab = m_Prefab;
		if (mapTilePrefab == null)
		{
			ComponentBase.baseLog.Critical($"Target not found {this}");
			return;
		}
		Entity entity = prefabSystem.GetEntity(mapTilePrefab);
		DynamicBuffer<MapFeatureData> buffer = entityManager.GetBuffer<MapFeatureData>(entity);
		for (int i = 0; i < m_MapFeatures.Length; i++)
		{
			MapTilePrefab.FeatureInfo featureInfo = m_MapFeatures[i];
			buffer[(int)featureInfo.m_MapFeature] = new MapFeatureData(featureInfo.m_Cost);
		}
		TilePurchaseCostFactor componentData = new TilePurchaseCostFactor(mapTilePrefab.m_PurchaseCostFactor);
		entityManager.SetComponentData(entity, componentData);
	}
```

- `public virtual RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RecordChanges(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		MapTilePrefab mapTilePrefab = m_Prefab;
		if (mapTilePrefab == null)
		{
			ComponentBase.baseLog.Critical($"Target not found {this}");
			return;
		}
		Entity entity = prefabSystem.GetEntity(mapTilePrefab);
		entityManager.GetComponentData<TilePurchaseCostFactor>(entity);
		entityManager.GetBuffer<MapFeatureData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		MapTilePrefab mapTilePrefab = m_Prefab;
		if (mapTilePrefab == null)
		{
			ComponentBase.baseLog.Critical($"Target not found {this}");
			return;
		}
		Entity entity = prefabSystem.GetEntity(mapTilePrefab);
		DynamicBuffer<MapFeatureData> buffer = entityManager.GetBuffer<MapFeatureData>(entity);
		for (int i = 0; i < mapTilePrefab.m_MapFeatures.Length; i++)
		{
			MapTilePrefab.FeatureInfo featureInfo = mapTilePrefab.m_MapFeatures[i];
			buffer[(int)featureInfo.m_MapFeature] = new MapFeatureData(featureInfo.m_Cost);
		}
		TilePurchaseCostFactor componentData = new TilePurchaseCostFactor(mapTilePrefab.m_PurchaseCostFactor);
		entityManager.SetComponentData(entity, componentData);
	}
```


