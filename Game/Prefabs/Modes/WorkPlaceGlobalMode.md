# Game.Prefabs.Modes.WorkPlaceGlobalMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WorkPlaceGlobalMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_WorkplacesMultiplier;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.WorkplaceData> m_OriginalWorkplaceData;

    public WorkPlaceGlobalMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_WorkplacesMultiplier`  

```csharp
public System.Single m_WorkplacesMultiplier;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.WorkplaceData> m_OriginalWorkplaceData`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.WorkplaceData> m_OriginalWorkplaceData;
```


## Constructors

- `public WorkPlaceGlobalMode()`  

```csharp
public WorkPlaceGlobalMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		return JobChunkExtensions.ScheduleParallel(new ModeJob
		{
			m_WorkplacesMultiplier = m_WorkplacesMultiplier,
			m_WorkplaceType = entityManager.GetComponentTypeHandle<WorkplaceData>(isReadOnly: false)
		}, requestedQuery, deps);
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[2]
		{
			ComponentType.ReadOnly<WorkplaceData>(),
			ComponentType.ReadOnly<BuildingData>()
		};
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<WorkplaceData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			WorkplaceData componentData = entityManager.GetComponentData<WorkplaceData>(entity);
			PrefabBase prefabBase;
			Workplace component;
			if (m_OriginalWorkplaceData.TryGetValue(entity, out var value))
			{
				componentData.m_MaxWorkers = value.m_MaxWorkers;
			}
			else if (prefabSystem.TryGetPrefab<PrefabBase>(entity, out prefabBase) && prefabBase.TryGetExactly<Workplace>(out component))
			{
				componentData.m_MaxWorkers = component.m_Workplaces;
			}
			else
			{
				m_OriginalWorkplaceData.Add(entity, entityManager.GetComponentData<WorkplaceData>(entity));
			}
			entityManager.SetComponentData(entity, componentData);
		}
	}
```

- `public virtual StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void StoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		m_OriginalWorkplaceData = new Dictionary<Entity, WorkplaceData>();
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			WorkplaceData componentData = entityManager.GetComponentData<WorkplaceData>(entity);
			if (prefabSystem.TryGetPrefab<PrefabBase>(entity, out var prefabBase) && prefabBase.TryGetExactly<Workplace>(out var _))
			{
				m_OriginalWorkplaceData[entity] = componentData;
			}
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.WorkPlaceGlobalMode+ModeJob`  

