# Game.Prefabs.Modes.GarbageFacilityMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class GarbageFacilityMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.GarbageFacilityMode+ModeData[] m_ModeDatas;

    public GarbageFacilityMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.GarbageFacilityMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.GarbageFacilityMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public GarbageFacilityMode()`  

```csharp
public GarbageFacilityMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			ModeData modeData = m_ModeDatas[i];
			GarbageFacility component = modeData.m_Prefab.GetComponent<GarbageFacility>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			GarbageFacilityData componentData = entityManager.GetComponentData<GarbageFacilityData>(entity);
			componentData.m_GarbageCapacity = (int)((float)componentData.m_GarbageCapacity * modeData.m_GarbageCapacityMultiplier);
			componentData.m_ProcessingSpeed = (int)((float)componentData.m_ProcessingSpeed * modeData.m_ProcessingSpeedMultiplier);
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
			GarbageFacility component = m_ModeDatas[i].m_Prefab.GetComponent<GarbageFacility>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			entityManager.GetComponentData<GarbageFacilityData>(entity);
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			GarbageFacility component = m_ModeDatas[i].m_Prefab.GetComponent<GarbageFacility>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			GarbageFacilityData componentData = entityManager.GetComponentData<GarbageFacilityData>(entity);
			componentData.m_GarbageCapacity = component.m_GarbageCapacity;
			componentData.m_ProcessingSpeed = component.m_ProcessingSpeed;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.GarbageFacilityMode+ModeData`  

