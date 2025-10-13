# Game.Prefabs.Modes.EducationParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EducationParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_InoperableSchoolLeaveProbability;
    public System.Single m_EnterHighSchoolProbability;
    public System.Single m_AdultEnterHighSchoolProbability;
    public System.Single m_WorkerContinueEducationProbability;

    public EducationParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_InoperableSchoolLeaveProbability`  

```csharp
public System.Single m_InoperableSchoolLeaveProbability;
```

- `public System.Single m_EnterHighSchoolProbability`  

```csharp
public System.Single m_EnterHighSchoolProbability;
```

- `public System.Single m_AdultEnterHighSchoolProbability`  

```csharp
public System.Single m_AdultEnterHighSchoolProbability;
```

- `public System.Single m_WorkerContinueEducationProbability`  

```csharp
public System.Single m_WorkerContinueEducationProbability;
```


## Constructors

- `public EducationParametersMode()`  

```csharp
public EducationParametersMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		EducationParameterData componentData = entityManager.GetComponentData<EducationParameterData>(singletonEntity);
		componentData.m_InoperableSchoolLeaveProbability = m_InoperableSchoolLeaveProbability;
		componentData.m_EnterHighSchoolProbability = m_EnterHighSchoolProbability;
		componentData.m_AdultEnterHighSchoolProbability = m_AdultEnterHighSchoolProbability;
		componentData.m_WorkerContinueEducationProbability = m_WorkerContinueEducationProbability;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<EducationParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<EducationParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		EducationPrefab educationPrefab = prefabSystem.GetPrefab<EducationPrefab>(entity);
		EducationParameterData componentData = entityManager.GetComponentData<EducationParameterData>(entity);
		componentData.m_InoperableSchoolLeaveProbability = educationPrefab.m_InoperableSchoolLeaveProbability;
		componentData.m_EnterHighSchoolProbability = educationPrefab.m_EnterHighSchoolProbability;
		componentData.m_AdultEnterHighSchoolProbability = educationPrefab.m_AdultEnterHighSchoolProbability;
		componentData.m_WorkerContinueEducationProbability = educationPrefab.m_WorkerContinueEducationProbability;
		entityManager.SetComponentData(entity, componentData);
	}
```


