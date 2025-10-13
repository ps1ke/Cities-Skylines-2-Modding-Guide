# Game.Prefabs.Modes.PlaceableNetPieceGlobalMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PlaceableNetPieceGlobalMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_ConstructionCostMultiplier;
    public System.Single m_ElevationCostMultiplier;
    public System.Single m_UpkeepCostMultiplier;

    public PlaceableNetPieceGlobalMode();

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

- `public System.Single m_ElevationCostMultiplier`  

```csharp
public System.Single m_ElevationCostMultiplier;
```

- `public System.Single m_UpkeepCostMultiplier`  

```csharp
public System.Single m_UpkeepCostMultiplier;
```


## Constructors

- `public PlaceableNetPieceGlobalMode()`  

```csharp
public PlaceableNetPieceGlobalMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		return JobChunkExtensions.ScheduleParallel(new ModeJob
		{
			m_ConstructionCostMultiplier = m_ConstructionCostMultiplier,
			m_ElevationCostMultiplier = m_ElevationCostMultiplier,
			m_UpkeepCostMultiplier = m_UpkeepCostMultiplier,
			m_PlaceableNetPieceType = entityManager.GetComponentTypeHandle<PlaceableNetPieceData>(isReadOnly: false)
		}, requestedQuery, deps);
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<PlaceableNetPieceData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<PlaceableNetPieceData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < entities.Length; i++)
		{
			Entity entity = entities[i];
			if (!prefabSystem.TryGetPrefab<PrefabBase>(entity, out var prefabBase) || !prefabBase.TryGetExactly<PlaceableNetPiece>(out var component))
			{
				ComponentBase.baseLog.Warn($"Prefab data not found {this} : {entity.ToString()} : {prefabBase}");
				continue;
			}
			PlaceableNetPieceData componentData = entityManager.GetComponentData<PlaceableNetPieceData>(entity);
			componentData.m_ConstructionCost = component.m_ConstructionCost;
			componentData.m_ElevationCost = component.m_ElevationCost;
			componentData.m_UpkeepCost = component.m_UpkeepCost;
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.Modes.PlaceableNetPieceGlobalMode+ModeJob`  

