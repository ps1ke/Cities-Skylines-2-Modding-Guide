# Game.Prefabs.MapTilePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.AreaPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MapTilePrefab : Game.Prefabs.AreaPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_PurchaseCostFactor;
    public Game.Prefabs.MapTilePrefab+FeatureInfo[] m_MapFeatures;

    public MapTilePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_PurchaseCostFactor`  

```csharp
public System.Single m_PurchaseCostFactor;
```

- `public Game.Prefabs.MapTilePrefab+FeatureInfo[] m_MapFeatures`  

```csharp
public Game.Prefabs.MapTilePrefab+FeatureInfo[] m_MapFeatures;
```


## Constructors

- `public MapTilePrefab()`  

```csharp
public MapTilePrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<MapTile>());
		components.Add(ComponentType.ReadWrite<MapFeatureElement>());
		components.Add(ComponentType.ReadWrite<Geometry>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<MapTileData>());
		components.Add(ComponentType.ReadWrite<MapFeatureData>());
		components.Add(ComponentType.ReadWrite<AreaGeometryData>());
		components.Add(ComponentType.ReadWrite<TilePurchaseCostFactor>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		DynamicBuffer<MapFeatureData> buffer = entityManager.GetBuffer<MapFeatureData>(entity);
		CollectionUtils.ResizeInitialized(buffer, 9);
		for (int i = 0; i < m_MapFeatures.Length; i++)
		{
			FeatureInfo featureInfo = m_MapFeatures[i];
			buffer[(int)featureInfo.m_MapFeature] = new MapFeatureData(featureInfo.m_Cost);
		}
		TilePurchaseCostFactor componentData = new TilePurchaseCostFactor(m_PurchaseCostFactor);
		entityManager.SetComponentData(entity, componentData);
	}
```


## Nested types

- `Game.Prefabs.MapTilePrefab+FeatureInfo`  

