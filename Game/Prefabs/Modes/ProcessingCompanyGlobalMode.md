# Game.Prefabs.Modes.ProcessingCompanyGlobalMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ProcessingCompanyGlobalMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_InputMultiplier;
    public System.Single m_OutputMultiplier;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.IndustrialProcessData> m_OriginalData;

    public ProcessingCompanyGlobalMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_InputMultiplier`  

```csharp
public System.Single m_InputMultiplier;
```

- `public System.Single m_OutputMultiplier`  

```csharp
public System.Single m_OutputMultiplier;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.IndustrialProcessData> m_OriginalData`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.IndustrialProcessData> m_OriginalData;
```


## Constructors

- `public ProcessingCompanyGlobalMode()`  

```csharp
public ProcessingCompanyGlobalMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		return JobChunkExtensions.ScheduleParallel(new ModeJob
		{
			m_InputMultiplier = m_InputMultiplier,
			m_OutputMultiplier = m_OutputMultiplier,
			m_ProcessingType = entityManager.GetComponentTypeHandle<IndustrialProcessData>(isReadOnly: false)
		}, requestedQuery, deps);
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<IndustrialProcessData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<IndustrialProcessData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			if (m_OriginalData.TryGetValue(entity, out var value))
			{
				entityManager.SetComponentData(entity, value);
			}
			else
			{
				m_OriginalData.Add(entity, entityManager.GetComponentData<IndustrialProcessData>(entity));
			}
		}
	}
```

- `public virtual StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void StoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		m_OriginalData = new Dictionary<Entity, IndustrialProcessData>(entities.Length);
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			IndustrialProcessData componentData = entityManager.GetComponentData<IndustrialProcessData>(entity);
			m_OriginalData.Add(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.ProcessingCompanyGlobalMode+ModeJob`  

