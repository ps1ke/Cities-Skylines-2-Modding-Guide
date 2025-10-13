# Game.Prefabs.Modes.GroundWaterPoweredMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class GroundWaterPoweredMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.GroundWaterPoweredMode+ModeData[] m_ModeDatas;

    public GroundWaterPoweredMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.GroundWaterPoweredMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.GroundWaterPoweredMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public GroundWaterPoweredMode()`  

```csharp
public GroundWaterPoweredMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			ModeData modeData = m_ModeDatas[i];
			GroundWaterPowered component = modeData.m_Prefab.GetComponent<GroundWaterPowered>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			GroundWaterPoweredData componentData = entityManager.GetComponentData<GroundWaterPoweredData>(entity);
			componentData.m_MaximumGroundWater = (int)((float)componentData.m_MaximumGroundWater * modeData.m_MaximumGroundWaterMultiplier);
			componentData.m_Production = (int)((float)componentData.m_Production * modeData.m_ProductionMultiplier);
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
			GroundWaterPowered component = m_ModeDatas[i].m_Prefab.GetComponent<GroundWaterPowered>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			entityManager.GetComponentData<GroundWaterPoweredData>(entity);
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			GroundWaterPowered component = m_ModeDatas[i].m_Prefab.GetComponent<GroundWaterPowered>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			GroundWaterPoweredData componentData = entityManager.GetComponentData<GroundWaterPoweredData>(entity);
			componentData.m_MaximumGroundWater = component.m_MaximumGroundWater;
			componentData.m_Production = component.m_Production;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.GroundWaterPoweredMode+ModeData`  

