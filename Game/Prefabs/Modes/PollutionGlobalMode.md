# Game.Prefabs.Modes.PollutionGlobalMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PollutionGlobalMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_GroundPollutionMultiplier;
    public System.Single m_AirPollutionMultiplier;
    public System.Single m_NoisePollutionMultiplier;

    public PollutionGlobalMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
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


## Constructors

- `public PollutionGlobalMode()`  

```csharp
public PollutionGlobalMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		return JobChunkExtensions.ScheduleParallel(new ModeJob
		{
			m_GroundPollutionMultiplier = m_GroundPollutionMultiplier,
			m_NoisePollutionMultiplier = m_NoisePollutionMultiplier,
			m_AirPollutionMultiplier = m_AirPollutionMultiplier,
			m_PollutionType = entityManager.GetComponentTypeHandle<PollutionData>(isReadOnly: false)
		}, requestedQuery, deps);
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<PollutionData>() };
		entityQueryDesc.Any = new ComponentType[2]
		{
			ComponentType.ReadOnly<BuildingData>(),
			ComponentType.ReadOnly<BuildingExtensionData>()
		};
		entityQueryDesc.None = new ComponentType[1] { ComponentType.ReadOnly<SpawnableBuildingData>() };
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
			if (!prefabSystem.TryGetPrefab<PrefabBase>(entity, out var prefabBase) || !prefabBase.TryGetExactly<Pollution>(out var component))
			{
				ComponentBase.baseLog.Warn($"Prefab data not found {this} : {entity.ToString()} : {prefabBase}");
				continue;
			}
			PollutionData componentData = entityManager.GetComponentData<PollutionData>(entity);
			componentData.m_GroundPollution = component.m_GroundPollution;
			componentData.m_AirPollution = component.m_AirPollution;
			componentData.m_NoisePollution = component.m_NoisePollution;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.PollutionGlobalMode+ModeJob`  

