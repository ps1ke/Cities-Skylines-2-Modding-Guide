# Game.Prefabs.Modes.MilestonesMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MilestonesMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.MilestonesMode+ModeData[] m_ModeDatas;

    public MilestonesMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.MilestonesMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.MilestonesMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public MilestonesMode()`  

```csharp
public MilestonesMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			ModeData modeData = m_ModeDatas[i];
			MilestonePrefab milestonePrefab = modeData.m_Prefab;
			if (milestonePrefab == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(milestonePrefab);
			MilestoneData componentData = entityManager.GetComponentData<MilestoneData>(entity);
			componentData.m_Reward = modeData.m_Reward;
			componentData.m_DevTreePoints = modeData.m_DevTreePoints;
			componentData.m_MapTiles = modeData.m_MapTiles;
			componentData.m_LoanLimit = modeData.m_LoanLimit;
			componentData.m_XpRequried = modeData.m_XpRequried;
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
			MilestonePrefab milestonePrefab = m_ModeDatas[i].m_Prefab;
			if (milestonePrefab == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(milestonePrefab);
			entityManager.GetComponentData<MilestoneData>(entity);
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			MilestonePrefab milestonePrefab = m_ModeDatas[i].m_Prefab;
			if (milestonePrefab == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(milestonePrefab);
			MilestoneData componentData = entityManager.GetComponentData<MilestoneData>(entity);
			componentData.m_Reward = milestonePrefab.m_Reward;
			componentData.m_DevTreePoints = milestonePrefab.m_DevTreePoints;
			componentData.m_MapTiles = milestonePrefab.m_MapTiles;
			componentData.m_LoanLimit = milestonePrefab.m_LoanLimit;
			componentData.m_XpRequried = milestonePrefab.m_XpRequried;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.MilestonesMode+ModeData`  

