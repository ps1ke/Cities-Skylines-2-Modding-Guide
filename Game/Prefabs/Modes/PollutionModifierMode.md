# Game.Prefabs.Modes.PollutionModifierMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PollutionModifierMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.PollutionModifierMode+ModeData[] m_ModeDatas;

    public PollutionModifierMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.PollutionModifierMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.PollutionModifierMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public PollutionModifierMode()`  

```csharp
public PollutionModifierMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			ModeData modeData = m_ModeDatas[i];
			PollutionModifier component = modeData.m_Prefab.GetComponent<PollutionModifier>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			PollutionModifierData componentData = entityManager.GetComponentData<PollutionModifierData>(entity);
			componentData.m_GroundPollutionMultiplier = modeData.m_GroundPollutionMultiplier;
			componentData.m_AirPollutionMultiplier = modeData.m_AirPollutionMultiplier;
			componentData.m_NoisePollutionMultiplier = modeData.m_NoisePollutionMultiplier;
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
			PollutionModifier component = m_ModeDatas[i].m_Prefab.GetComponent<PollutionModifier>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			entityManager.GetComponentData<PollutionModifierData>(entity);
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			PollutionModifier component = m_ModeDatas[i].m_Prefab.GetComponent<PollutionModifier>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			PollutionModifierData componentData = entityManager.GetComponentData<PollutionModifierData>(entity);
			componentData.m_GroundPollutionMultiplier = component.m_GroundPollutionMultiplier;
			componentData.m_AirPollutionMultiplier = component.m_AirPollutionMultiplier;
			componentData.m_NoisePollutionMultiplier = component.m_NoisePollutionMultiplier;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.PollutionModifierMode+ModeData`  

