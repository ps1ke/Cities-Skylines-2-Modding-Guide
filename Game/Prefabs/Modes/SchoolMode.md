# Game.Prefabs.Modes.SchoolMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SchoolMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.Modes.SchoolMode+ModeData[] m_ModeDatas;

    public SchoolMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.Modes.SchoolMode+ModeData[] m_ModeDatas`  

```csharp
public Game.Prefabs.Modes.SchoolMode+ModeData[] m_ModeDatas;
```


## Constructors

- `public SchoolMode()`  

```csharp
public SchoolMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			ModeData modeData = m_ModeDatas[i];
			School component = modeData.m_Prefab.GetComponent<School>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			SchoolData componentData = entityManager.GetComponentData<SchoolData>(entity);
			componentData.m_StudentCapacity = (int)((float)componentData.m_StudentCapacity * modeData.m_StudentCapacityMultifier);
			componentData.m_GraduationModifier = modeData.m_GraduationModifier;
			componentData.m_StudentWellbeing = modeData.m_StudentWellbeing;
			componentData.m_StudentHealth = modeData.m_StudentHealth;
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
			School component = m_ModeDatas[i].m_Prefab.GetComponent<School>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			entityManager.GetComponentData<SchoolData>(entity);
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_ModeDatas.Length; i++)
		{
			School component = m_ModeDatas[i].m_Prefab.GetComponent<School>();
			if (component == null)
			{
				ComponentBase.baseLog.Critical($"Target not found {this}");
				continue;
			}
			Entity entity = prefabSystem.GetEntity(component.prefab);
			SchoolData componentData = entityManager.GetComponentData<SchoolData>(entity);
			componentData.m_StudentCapacity = component.m_StudentCapacity;
			componentData.m_GraduationModifier = component.m_GraduationModifier;
			componentData.m_StudentWellbeing = component.m_StudentWellbeing;
			componentData.m_StudentHealth = component.m_StudentHealth;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.SchoolMode+ModeData`  

