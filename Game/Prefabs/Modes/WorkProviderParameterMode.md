# Game.Prefabs.Modes.WorkProviderParameterMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WorkProviderParameterMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int16 m_UneducatedNotificationDelay;
    public System.Int16 m_EducatedNotificationDelay;
    public System.Single m_UneducatedNotificationLimit;
    public System.Single m_EducatedNotificationLimit;
    public System.Int32 m_SeniorEmployeeLevel;

    public WorkProviderParameterMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Int16 m_UneducatedNotificationDelay`  

```csharp
public System.Int16 m_UneducatedNotificationDelay;
```

- `public System.Int16 m_EducatedNotificationDelay`  

```csharp
public System.Int16 m_EducatedNotificationDelay;
```

- `public System.Single m_UneducatedNotificationLimit`  

```csharp
public System.Single m_UneducatedNotificationLimit;
```

- `public System.Single m_EducatedNotificationLimit`  

```csharp
public System.Single m_EducatedNotificationLimit;
```

- `public System.Int32 m_SeniorEmployeeLevel`  

```csharp
public System.Int32 m_SeniorEmployeeLevel;
```


## Constructors

- `public WorkProviderParameterMode()`  

```csharp
public WorkProviderParameterMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		WorkProviderParameterData componentData = entityManager.GetComponentData<WorkProviderParameterData>(singletonEntity);
		componentData.m_UneducatedNotificationDelay = m_UneducatedNotificationDelay;
		componentData.m_EducatedNotificationDelay = m_EducatedNotificationDelay;
		componentData.m_UneducatedNotificationLimit = m_UneducatedNotificationLimit;
		componentData.m_EducatedNotificationLimit = m_EducatedNotificationLimit;
		componentData.m_SeniorEmployeeLevel = m_SeniorEmployeeLevel;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<WorkProviderParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<WorkProviderParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		WorkProviderParameterPrefab workProviderParameterPrefab = prefabSystem.GetPrefab<WorkProviderParameterPrefab>(entity);
		WorkProviderParameterData componentData = entityManager.GetComponentData<WorkProviderParameterData>(entity);
		componentData.m_UneducatedNotificationDelay = workProviderParameterPrefab.m_UneducatedNotificationDelay;
		componentData.m_EducatedNotificationDelay = workProviderParameterPrefab.m_EducatedNotificationDelay;
		componentData.m_UneducatedNotificationLimit = workProviderParameterPrefab.m_UneducatedNotificationLimit;
		componentData.m_EducatedNotificationLimit = workProviderParameterPrefab.m_EducatedNotificationLimit;
		componentData.m_SeniorEmployeeLevel = workProviderParameterPrefab.m_SeniorEmployeeLevel;
		entityManager.SetComponentData(entity, componentData);
	}
```


