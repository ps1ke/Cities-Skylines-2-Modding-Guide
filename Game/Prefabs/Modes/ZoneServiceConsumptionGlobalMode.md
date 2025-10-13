# Game.Prefabs.Modes.ZoneServiceConsumptionGlobalMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZoneServiceConsumptionGlobalMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_UpkeepMultiplier;
    public System.Single m_ElectricityConsumptionMultiplier;
    public System.Single m_WaterConsumptionMultiplier;
    public System.Single m_GarbageAccumlationMultiplier;
    public System.Single m_TelecomNeedMultiplier;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.ConsumptionData> m_OriginalConsumptionData;

    public ZoneServiceConsumptionGlobalMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_UpkeepMultiplier`  

```csharp
public System.Single m_UpkeepMultiplier;
```

- `public System.Single m_ElectricityConsumptionMultiplier`  

```csharp
public System.Single m_ElectricityConsumptionMultiplier;
```

- `public System.Single m_WaterConsumptionMultiplier`  

```csharp
public System.Single m_WaterConsumptionMultiplier;
```

- `public System.Single m_GarbageAccumlationMultiplier`  

```csharp
public System.Single m_GarbageAccumlationMultiplier;
```

- `public System.Single m_TelecomNeedMultiplier`  

```csharp
public System.Single m_TelecomNeedMultiplier;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.ConsumptionData> m_OriginalConsumptionData`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.ConsumptionData> m_OriginalConsumptionData;
```


## Constructors

- `public ZoneServiceConsumptionGlobalMode()`  

```csharp
public ZoneServiceConsumptionGlobalMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		return JobChunkExtensions.ScheduleParallel(new ModeJob
		{
			m_UpkeepMultiplier = m_UpkeepMultiplier,
			m_ElectricityConsumptionMultiplier = m_ElectricityConsumptionMultiplier,
			m_WaterConsumptionMultiplier = m_WaterConsumptionMultiplier,
			m_GarbageAccumlationMultiplier = m_GarbageAccumlationMultiplier,
			m_TelecomNeedMultiplier = m_TelecomNeedMultiplier,
			m_ConsumptionType = entityManager.GetComponentTypeHandle<ConsumptionData>(isReadOnly: false)
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
			ComponentType.ReadOnly<ConsumptionData>(),
			ComponentType.ReadOnly<SpawnableBuildingData>()
		};
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<ConsumptionData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			if (m_OriginalConsumptionData.TryGetValue(entity, out var value))
			{
				entityManager.SetComponentData(entity, value);
				continue;
			}
			value = entityManager.GetComponentData<ConsumptionData>(entity);
			m_OriginalConsumptionData.Add(entity, value);
		}
	}
```

- `public virtual StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void StoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		m_OriginalConsumptionData = new Dictionary<Entity, ConsumptionData>(entities.Length);
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			ConsumptionData componentData = entityManager.GetComponentData<ConsumptionData>(entity);
			m_OriginalConsumptionData.Add(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.ZoneServiceConsumptionGlobalMode+ModeJob`  

