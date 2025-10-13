# Game.Prefabs.Modes.LeisureParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LeisureParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_LeisureRandomFactor;
    public System.Int32 m_TouristLodgingConsumePerDay;
    public System.Int32 m_TouristServiceConsumePerDay;

    public LeisureParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Int32 m_LeisureRandomFactor`  

```csharp
public System.Int32 m_LeisureRandomFactor;
```

- `public System.Int32 m_TouristLodgingConsumePerDay`  

```csharp
public System.Int32 m_TouristLodgingConsumePerDay;
```

- `public System.Int32 m_TouristServiceConsumePerDay`  

```csharp
public System.Int32 m_TouristServiceConsumePerDay;
```


## Constructors

- `public LeisureParametersMode()`  

```csharp
public LeisureParametersMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		LeisureParametersData componentData = entityManager.GetComponentData<LeisureParametersData>(singletonEntity);
		componentData.m_LeisureRandomFactor = m_LeisureRandomFactor;
		componentData.m_TouristLodgingConsumePerDay = m_TouristLodgingConsumePerDay;
		componentData.m_TouristServiceConsumePerDay = m_TouristServiceConsumePerDay;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<LeisureParametersData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<LeisureParametersData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		LeisureParametersPrefab leisureParametersPrefab = prefabSystem.GetPrefab<LeisureParametersPrefab>(entity);
		LeisureParametersData componentData = entityManager.GetComponentData<LeisureParametersData>(entity);
		componentData.m_LeisureRandomFactor = leisureParametersPrefab.m_LeisureRandomFactor;
		componentData.m_TouristLodgingConsumePerDay = leisureParametersPrefab.m_TouristLodgingConsumePerDay;
		componentData.m_TouristServiceConsumePerDay = leisureParametersPrefab.m_TouristServiceConsumePerDay;
		entityManager.SetComponentData(entity, componentData);
	}
```


