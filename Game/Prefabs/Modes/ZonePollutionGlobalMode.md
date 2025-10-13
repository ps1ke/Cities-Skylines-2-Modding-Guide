# Game.Prefabs.Modes.ZonePollutionGlobalMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZonePollutionGlobalMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_GroundPollutionMultiplier;
    public System.Single m_AirPollutionMultiplier;
    public System.Single m_NoisePollutionMultiplier;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.PollutionData> m_OriginalPollutionData;

    public ZonePollutionGlobalMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_GroundPollutionMultiplier`  

```csharp
public System.Single m_GroundPollutionMultiplier;
```

- `public System.Single m_AirPollutionMultiplier`  

```csharp
public System.Single m_AirPollutionMultiplier;
```

- `public System.Single m_NoisePollutionMultiplier`  

```csharp
public System.Single m_NoisePollutionMultiplier;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.PollutionData> m_OriginalPollutionData`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.PollutionData> m_OriginalPollutionData;
```


## Constructors

- `public ZonePollutionGlobalMode()`  

```csharp
public ZonePollutionGlobalMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		return JobChunkExtensions.ScheduleParallel(new ModeJob
		{
			m_GroundPollutionMultiplier = m_GroundPollutionMultiplier,
			m_AirPollutionMultiplier = m_AirPollutionMultiplier,
			m_NoisePollutionMultiplier = m_NoisePollutionMultiplier,
			m_PollutionType = entityManager.GetComponentTypeHandle<PollutionData>(isReadOnly: false)
		}, requestedQuery, deps);
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[3]
		{
			ComponentType.ReadOnly<SpawnableBuildingData>(),
			ComponentType.ReadOnly<BuildingSpawnGroupData>(),
			ComponentType.ReadOnly<PollutionData>()
		};
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<PollutionData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			if (m_OriginalPollutionData.TryGetValue(entity, out var value))
			{
				entityManager.SetComponentData(entity, value);
			}
			else
			{
				m_OriginalPollutionData.Add(entity, entityManager.GetComponentData<PollutionData>(entity));
			}
		}
	}
```

- `public virtual StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void StoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		m_OriginalPollutionData = new Dictionary<Entity, PollutionData>(entities.Length);
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			PollutionData componentData = entityManager.GetComponentData<PollutionData>(entity);
			m_OriginalPollutionData.Add(entity, componentData);
		}
		entities.Dispose();
	}
```


## Nested types

- `Game.Prefabs.Modes.ZonePollutionGlobalMode+ModeJob`  

