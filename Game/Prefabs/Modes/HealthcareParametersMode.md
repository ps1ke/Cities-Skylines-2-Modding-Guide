# Game.Prefabs.Modes.HealthcareParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class HealthcareParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_TransportWarningTime;
    public System.Single m_NoResourceTreatmentPenalty;
    public System.Single m_BuildingDestoryDeathRate;
    public UnityEngine.AnimationCurve m_DeathRate;

    public HealthcareParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_TransportWarningTime`  

```csharp
public System.Single m_TransportWarningTime;
```

- `public System.Single m_NoResourceTreatmentPenalty`  

```csharp
public System.Single m_NoResourceTreatmentPenalty;
```

- `public System.Single m_BuildingDestoryDeathRate`  

```csharp
public System.Single m_BuildingDestoryDeathRate;
```

- `public UnityEngine.AnimationCurve m_DeathRate`  

```csharp
public UnityEngine.AnimationCurve m_DeathRate;
```


## Constructors

- `public HealthcareParametersMode()`  

```csharp
public HealthcareParametersMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		HealthcareParameterData componentData = entityManager.GetComponentData<HealthcareParameterData>(singletonEntity);
		componentData.m_TransportWarningTime = m_TransportWarningTime;
		componentData.m_NoResourceTreatmentPenalty = m_NoResourceTreatmentPenalty;
		componentData.m_BuildingDestoryDeathRate = m_BuildingDestoryDeathRate;
		componentData.m_DeathRate = new AnimationCurve1(m_DeathRate);
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<HealthcareParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<HealthcareParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		HealthcarePrefab healthcarePrefab = prefabSystem.GetPrefab<HealthcarePrefab>(entity);
		HealthcareParameterData componentData = entityManager.GetComponentData<HealthcareParameterData>(entity);
		componentData.m_TransportWarningTime = healthcarePrefab.m_TransportWarningTime;
		componentData.m_NoResourceTreatmentPenalty = healthcarePrefab.m_NoResourceTreatmentPenalty;
		componentData.m_BuildingDestoryDeathRate = healthcarePrefab.m_BuildingDestoryDeathRate;
		componentData.m_DeathRate = new AnimationCurve1(healthcarePrefab.m_DeathRate);
		entityManager.SetComponentData(entity, componentData);
	}
```


