# Game.Prefabs.Modes.ServiceConsumptionGlobalMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ServiceConsumptionGlobalMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_UpkeepMultiplier;
    public System.Single m_ElectricityConsumptionMultiplier;
    public System.Single m_WaterConsumptionMultiplier;
    public System.Single m_GarbageAccumlationMultiplier;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.ServiceUpkeepData> m_CachedUpkeepDatasDatas;

    public ServiceConsumptionGlobalMode();

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

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.ServiceUpkeepData> m_CachedUpkeepDatasDatas`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Prefabs.ServiceUpkeepData> m_CachedUpkeepDatasDatas;
```


## Constructors

- `public ServiceConsumptionGlobalMode()`  

```csharp
public ServiceConsumptionGlobalMode();
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
			m_ConsumptionType = entityManager.GetComponentTypeHandle<ConsumptionData>(isReadOnly: false),
			m_ServiceUpkeepType = entityManager.GetBufferTypeHandle<ServiceUpkeepData>(isReadOnly: false)
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
			ComponentType.ReadOnly<ServiceUpkeepData>()
		};
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
		entityManager.GetBuffer<ServiceUpkeepData>(entity);
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
			if (!prefabSystem.TryGetPrefab<PrefabBase>(entity, out var prefabBase) || !prefabBase.TryGetExactly<ServiceConsumption>(out var component))
			{
				ComponentBase.baseLog.Warn($"Prefab data not found {this} : {entity.ToString()} : {prefabBase}");
				continue;
			}
			ConsumptionData componentData = entityManager.GetComponentData<ConsumptionData>(entity);
			componentData.m_Upkeep = component.m_Upkeep;
			componentData.m_ElectricityConsumption = component.m_ElectricityConsumption;
			componentData.m_WaterConsumption = component.m_WaterConsumption;
			componentData.m_GarbageAccumulation = component.m_GarbageAccumulation;
			entityManager.SetComponentData(entity, componentData);
			DynamicBuffer<ServiceUpkeepData> buffer = entityManager.GetBuffer<ServiceUpkeepData>(entity);
			for (int j = 0; j < buffer.Length; j++)
			{
				if (buffer[j].m_Upkeep.m_Resource == Resource.Money)
				{
					if (!m_CachedUpkeepDatasDatas.TryGetValue(entity, out var value))
					{
						ComponentBase.baseLog.Critical("Cached ServiceUpkeepData not found " + entity.ToString());
						continue;
					}
					ServiceUpkeepData value2 = buffer[j];
					value2.m_Upkeep.m_Amount = value.m_Upkeep.m_Amount;
					buffer[j] = value2;
				}
			}
		}
	}
```

- `public virtual StoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void StoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		m_CachedUpkeepDatasDatas = new Dictionary<Entity, ServiceUpkeepData>(entities.Length);
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			DynamicBuffer<ServiceUpkeepData> buffer = entityManager.GetBuffer<ServiceUpkeepData>(entity);
			for (int j = 0; j < buffer.Length; j++)
			{
				if (buffer[j].m_Upkeep.m_Resource == Resource.Money)
				{
					m_CachedUpkeepDatasDatas.Add(entity, buffer[j]);
				}
			}
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.ServiceConsumptionGlobalMode+ModeJob`  

