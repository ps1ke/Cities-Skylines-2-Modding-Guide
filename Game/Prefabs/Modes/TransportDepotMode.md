# Game.Prefabs.Modes.TransportDepotMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportDepotMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.TransportDepotMode+ModeData[] m_ModeDatas;

    public TransportDepotMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.TransportDepotMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.TransportDepotMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public TransportDepotMode()`  

```csharp
public TransportDepotMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			ModeData modeData = m_ModeDatas[i];
			TransportDepot component = modeData.m_Prefab.GetComponent<TransportDepot>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			TransportDepotData componentData = entityManager.GetComponentData<TransportDepotData>(entity);
			componentData.m_VehicleCapacity = modeData.m_VehicleCapacity;
			componentData.m_ProductionDuration = modeData.m_ProductionDuration;
			componentData.m_MaintenanceDuration = modeData.m_MaintenanceDuration;
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
			TransportDepot component = m_ModeDatas[i].m_Prefab.GetComponent<TransportDepot>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			entityManager.GetComponentData<TransportDepotData>(entity);
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			TransportDepot component = m_ModeDatas[i].m_Prefab.GetComponent<TransportDepot>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			TransportDepotData componentData = entityManager.GetComponentData<TransportDepotData>(entity);
			componentData.m_VehicleCapacity = component.m_VehicleCapacity;
			componentData.m_ProductionDuration = component.m_ProductionDuration;
			componentData.m_MaintenanceDuration = component.m_MaintenanceDuration;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.TransportDepotMode+ModeData`  

