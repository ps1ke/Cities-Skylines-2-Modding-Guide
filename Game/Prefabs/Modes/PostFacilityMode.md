# Game.Prefabs.Modes.PostFacilityMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PostFacilityMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.PostFacilityMode+ModeData[] m_ModeDatas;

    public PostFacilityMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.PostFacilityMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.PostFacilityMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public PostFacilityMode()`  

```csharp
public PostFacilityMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			ModeData modeData = m_ModeDatas[i];
			PostFacility component = modeData.m_Prefab.GetComponent<PostFacility>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			PostFacilityData componentData = entityManager.GetComponentData<PostFacilityData>(entity);
			componentData.m_MailCapacity = (int)((float)componentData.m_MailCapacity * modeData.m_MailStorageCapacityMultifier);
			componentData.m_SortingRate = (int)((float)componentData.m_SortingRate * modeData.m_SortingRateMultifier);
			entityManager.SetComponentData(entity, componentData);
			if (entityManager.HasComponent<MailBoxData>(entity))
			{
				MailBoxData componentData2 = entityManager.GetComponentData<MailBoxData>(entity);
				componentData2.m_MailCapacity = (int)((float)componentData2.m_MailCapacity * modeData.m_MailBoxCapacityMultifier);
				entityManager.SetComponentData(entity, componentData2);
			}
		}
	}
```

- `public virtual RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RecordChanges(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			PostFacility component = m_ModeDatas[i].m_Prefab.GetComponent<PostFacility>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			entityManager.GetComponentData<PostFacilityData>(entity);
			if (entityManager.HasComponent<MailBoxData>(entity))
			{
				entityManager.GetComponentData<MailBoxData>(entity);
			}
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			PostFacility component = m_ModeDatas[i].m_Prefab.GetComponent<PostFacility>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			PostFacilityData componentData = entityManager.GetComponentData<PostFacilityData>(entity);
			componentData.m_MailCapacity = component.m_MailStorageCapacity;
			componentData.m_SortingRate = component.m_SortingRate;
			entityManager.SetComponentData(entity, componentData);
			if (entityManager.HasComponent<MailBoxData>(entity))
			{
				MailBoxData componentData2 = entityManager.GetComponentData<MailBoxData>(entity);
				componentData2.m_MailCapacity = component.m_MailBoxCapacity;
				entityManager.SetComponentData(entity, componentData2);
			}
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.PostFacilityMode+ModeData`  

