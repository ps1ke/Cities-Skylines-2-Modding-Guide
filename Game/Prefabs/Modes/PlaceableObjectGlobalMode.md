# Game.Prefabs.Modes.PlaceableObjectGlobalMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PlaceableObjectGlobalMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_ConstructionCostMultiplier;
    public System.Single m_XPRewardMultiplier;

    public PlaceableObjectGlobalMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_ConstructionCostMultiplier`  

```csharp
public System.Single m_ConstructionCostMultiplier;
```

- `public System.Single m_XPRewardMultiplier`  

```csharp
public System.Single m_XPRewardMultiplier;
```


## Constructors

- `public PlaceableObjectGlobalMode()`  

```csharp
public PlaceableObjectGlobalMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		return JobChunkExtensions.ScheduleParallel(new ModeJob
		{
			m_ConstructionCostMultiplier = m_ConstructionCostMultiplier,
			m_XPRewardMultiplier = m_XPRewardMultiplier,
			m_PlaceableObjectType = entityManager.GetComponentTypeHandle<PlaceableObjectData>(isReadOnly: false)
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
			ComponentType.ReadOnly<PlaceableObjectData>(),
			ComponentType.ReadOnly<PlaceableInfoviewItem>()
		};
		entityQueryDesc.Any = new ComponentType[2]
		{
			ComponentType.ReadOnly<BuildingData>(),
			ComponentType.ReadOnly<BuildingExtensionData>()
		};
		entityQueryDesc.None = new ComponentType[3]
		{
			ComponentType.ReadOnly<SpawnableBuildingData>(),
			ComponentType.ReadOnly<TreeData>(),
			ComponentType.ReadOnly<PlantData>()
		};
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<PlaceableObjectData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			if (!prefabSystem.TryGetPrefab<PrefabBase>(entity, out var prefabBase) || !prefabBase.TryGetExactly<PlaceableObject>(out var component))
			{
				ComponentBase.baseLog.Warn($"Prefab data not found {this} : {entity.ToString()} : {prefabBase}");
				continue;
			}
			PlaceableObjectData componentData = entityManager.GetComponentData<PlaceableObjectData>(entity);
			componentData.m_ConstructionCost = component.m_ConstructionCost;
			componentData.m_XPReward = component.m_XPReward;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.PlaceableObjectGlobalMode+ModeJob`  

