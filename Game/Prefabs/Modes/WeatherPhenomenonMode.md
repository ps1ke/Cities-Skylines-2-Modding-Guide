# Game.Prefabs.Modes.WeatherPhenomenonMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WeatherPhenomenonMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.WeatherPhenomenonMode+ModeData[] m_ModeDatas;

    public WeatherPhenomenonMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.WeatherPhenomenonMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.WeatherPhenomenonMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public WeatherPhenomenonMode()`  

```csharp
public WeatherPhenomenonMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			ModeData modeData = m_ModeDatas[i];
			WeatherPhenomenon component = modeData.m_Prefab.GetComponent<WeatherPhenomenon>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			WeatherPhenomenonData componentData = entityManager.GetComponentData<WeatherPhenomenonData>(entity);
			componentData.m_OccurenceProbability = modeData.m_OccurrenceProbability;
			componentData.m_OccurenceTemperature = modeData.m_OccurenceTemperature;
			componentData.m_OccurenceRain = modeData.m_OccurenceRain;
			componentData.m_Duration = modeData.m_Duration;
			componentData.m_PhenomenonRadius = modeData.m_PhenomenonRadius;
			componentData.m_HotspotRadius = modeData.m_HotspotRadius;
			componentData.m_HotspotInstability = modeData.m_HotspotInstability;
			componentData.m_DamageSeverity = modeData.m_DamageSeverity;
			componentData.m_DangerLevel = modeData.m_DangerLevel;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```

- `public virtual RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RecordChanges(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			WeatherPhenomenon component = m_ModeDatas[i].m_Prefab.GetComponent<WeatherPhenomenon>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			entityManager.GetComponentData<WeatherPhenomenonData>(entity);
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			WeatherPhenomenon component = m_ModeDatas[i].m_Prefab.GetComponent<WeatherPhenomenon>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			WeatherPhenomenonData componentData = entityManager.GetComponentData<WeatherPhenomenonData>(entity);
			componentData.m_OccurenceProbability = component.m_OccurrenceProbability;
			componentData.m_OccurenceTemperature = component.m_OccurenceTemperature;
			componentData.m_OccurenceRain = component.m_OccurenceRain;
			componentData.m_Duration = component.m_Duration;
			componentData.m_PhenomenonRadius = component.m_PhenomenonRadius;
			componentData.m_HotspotRadius = component.m_HotspotRadius;
			componentData.m_HotspotInstability = component.m_HotspotInstability;
			componentData.m_DamageSeverity = component.m_DamageSeverity;
			componentData.m_DangerLevel = component.m_DangerLevel;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.WeatherPhenomenonMode+ModeData`  

