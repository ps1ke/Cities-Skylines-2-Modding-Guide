# Game.Prefabs.Modes.GarbagePoweredMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class GarbagePoweredMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.GarbagePoweredMode+ModeData[] m_ModeDatas;

    public GarbagePoweredMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.GarbagePoweredMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.GarbagePoweredMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public GarbagePoweredMode()`  

```csharp
public GarbagePoweredMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			ModeData modeData = m_ModeDatas[i];
			GarbagePowered component = modeData.m_Prefab.GetComponent<GarbagePowered>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			GarbagePoweredData componentData = entityManager.GetComponentData<GarbagePoweredData>(entity);
			componentData.m_ProductionPerUnit = (int)(componentData.m_ProductionPerUnit * modeData.m_ProductionPerUnitMultiplier);
			componentData.m_Capacity = (int)((float)componentData.m_Capacity * modeData.m_CapacityMultiplier);
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
			GarbagePowered component = m_ModeDatas[i].m_Prefab.GetComponent<GarbagePowered>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			entityManager.GetComponentData<GarbagePoweredData>(entity);
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			GarbagePowered component = m_ModeDatas[i].m_Prefab.GetComponent<GarbagePowered>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			GarbagePoweredData componentData = entityManager.GetComponentData<GarbagePoweredData>(entity);
			componentData.m_ProductionPerUnit = component.m_ProductionPerUnit;
			componentData.m_Capacity = component.m_Capacity;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.GarbagePoweredMode+ModeData`  

