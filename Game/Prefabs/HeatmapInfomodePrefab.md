# Game.Prefabs.HeatmapInfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.GradientInfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IGradientInfomode`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class HeatmapInfomodePrefab : Game.Prefabs.GradientInfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IGradientInfomode
{
    public Game.Rendering.HeatmapData m_Type;

    public System.String infomodeTypeLocaleKey { get; }

    public HeatmapInfomodePrefab();

    public virtual System.Boolean CanActivateBoth(Game.Prefabs.InfomodePrefab other);
    public virtual System.Int32 GetColorGroup(System.Int32& secondaryGroup);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    private System.Boolean HasArrowsOnWater();
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Rendering.HeatmapData m_Type`  

```csharp
public Game.Rendering.HeatmapData m_Type;
```


## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

```csharp
public System.String infomodeTypeLocaleKey { get; }
```


## Constructors

- `public HeatmapInfomodePrefab()`  

```csharp
public HeatmapInfomodePrefab();
```


## Methods

- `public virtual CanActivateBoth(Game.Prefabs.InfomodePrefab other) : System.Boolean`  

```csharp
public override bool CanActivateBoth(InfomodePrefab other)
	{
		if (other is HeatmapInfomodePrefab heatmapInfomodePrefab && HasArrowsOnWater() && heatmapInfomodePrefab.HasArrowsOnWater())
		{
			return false;
		}
		return base.CanActivateBoth(other);
	}
```

- `public virtual GetColorGroup(System.Int32& secondaryGroup) : System.Int32`  

```csharp
public override int GetColorGroup(out int secondaryGroup)
	{
		switch (m_Type)
		{
		case HeatmapData.AirPollution:
		case HeatmapData.Wind:
		case HeatmapData.TelecomCoverage:
		case HeatmapData.Oil:
		case HeatmapData.Noise:
			secondaryGroup = 1;
			return 0;
		case HeatmapData.WaterFlow:
		case HeatmapData.WaterPollution:
		case HeatmapData.Fish:
			secondaryGroup = -1;
			return 1;
		default:
			secondaryGroup = -1;
			return 0;
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<InfoviewHeatmapData>());
	}
```

- `private HasArrowsOnWater() : System.Boolean`  

```csharp
private bool HasArrowsOnWater()
	{
		HeatmapData type = m_Type;
		if ((uint)(type - 4) <= 1u)
		{
			return true;
		}
		return false;
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new InfoviewHeatmapData
		{
			m_Type = m_Type
		});
	}
```


