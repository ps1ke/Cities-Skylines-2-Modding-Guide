# Game.Prefabs.Modes.ServiceCoverageGlobalMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ServiceCoverageGlobalMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_RangeMultiplier;
    public System.Single m_CapacityMultiplier;
    public System.Single m_MagnitudeMultiplier;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.CoverageData> m_OriginalCoverageData;

    public ServiceCoverageGlobalMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_RangeMultiplier`  

```csharp
public System.Single m_RangeMultiplier;
```

- `public System.Single m_CapacityMultiplier`  

```csharp
public System.Single m_CapacityMultiplier;
```

- `public System.Single m_MagnitudeMultiplier`  

```csharp
public System.Single m_MagnitudeMultiplier;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.CoverageData> m_OriginalCoverageData`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.CoverageData> m_OriginalCoverageData;
```


## Constructors

- `public ServiceCoverageGlobalMode()`  

```csharp
public ServiceCoverageGlobalMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		return JobChunkExtensions.ScheduleParallel(new ModeJob
		{
			m_RangeMultiplier = m_RangeMultiplier,
			m_MagnitudeMultiplier = m_MagnitudeMultiplier,
			m_CapacityMultiplier = m_CapacityMultiplier,
			m_CoverageType = entityManager.GetComponentTypeHandle<CoverageData>(isReadOnly: false)
		}, requestedQuery, deps);
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<CoverageData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<CoverageData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			PrefabBase prefabBase;
			ServiceCoverage component;
			if (m_OriginalCoverageData.TryGetValue(entity, out var value))
			{
				entityManager.SetComponentData(entity, value);
			}
			else if (prefabSystem.TryGetPrefab<PrefabBase>(entity, out prefabBase) && prefabBase.TryGetExactly<ServiceCoverage>(out component))
			{
				CoverageData componentData = entityManager.GetComponentData<CoverageData>(entity);
				componentData.m_Range = component.m_Range;
				componentData.m_Capacity = component.m_Capacity;
				componentData.m_Magnitude = component.m_Magnitude;
				entityManager.SetComponentData(entity, componentData);
			}
			else
			{
				m_OriginalCoverageData.Add(entity, entityManager.GetComponentData<CoverageData>(entity));
			}
		}
	}
```

- `public virtual StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void StoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		m_OriginalCoverageData = new Dictionary<Entity, CoverageData>();
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			CoverageData componentData = entityManager.GetComponentData<CoverageData>(entity);
			if (prefabSystem.TryGetPrefab<PrefabBase>(entity, out var prefabBase) && prefabBase.TryGetExactly<ServiceCoverage>(out var _))
			{
				m_OriginalCoverageData[entity] = componentData;
			}
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.ServiceCoverageGlobalMode+ModeJob`  

