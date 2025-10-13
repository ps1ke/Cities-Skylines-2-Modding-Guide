# Game.Prefabs.Modes.PoliceConfigurationMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PoliceConfigurationMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_MaxCrimeAccumulationMultiplier;
    public System.Single m_CrimeAccumulationToleranceMultiplier;
    public System.Int32 m_HomeCrimeEffectMultiplier;
    public System.Int32 m_WorkplaceCrimeEffectMultiplier;
    public System.Single m_WelfareCrimeRecurrenceFactor;
    public System.Single m_CrimePoliceCoverageFactorMultiflier;
    public System.Single m_CrimePopulationReductionMultiplier;

    public PoliceConfigurationMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_MaxCrimeAccumulationMultiplier`  

```csharp
public System.Single m_MaxCrimeAccumulationMultiplier;
```

- `public System.Single m_CrimeAccumulationToleranceMultiplier`  

```csharp
public System.Single m_CrimeAccumulationToleranceMultiplier;
```

- `public System.Int32 m_HomeCrimeEffectMultiplier`  

```csharp
public System.Int32 m_HomeCrimeEffectMultiplier;
```

- `public System.Int32 m_WorkplaceCrimeEffectMultiplier`  

```csharp
public System.Int32 m_WorkplaceCrimeEffectMultiplier;
```

- `public System.Single m_WelfareCrimeRecurrenceFactor`  

```csharp
public System.Single m_WelfareCrimeRecurrenceFactor;
```

- `public System.Single m_CrimePoliceCoverageFactorMultiflier`  

```csharp
public System.Single m_CrimePoliceCoverageFactorMultiflier;
```

- `public System.Single m_CrimePopulationReductionMultiplier`  

```csharp
public System.Single m_CrimePopulationReductionMultiplier;
```


## Constructors

- `public PoliceConfigurationMode()`  

```csharp
public PoliceConfigurationMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		PoliceConfigurationData componentData = entityManager.GetComponentData<PoliceConfigurationData>(singletonEntity);
		componentData.m_MaxCrimeAccumulation *= m_MaxCrimeAccumulationMultiplier;
		componentData.m_CrimeAccumulationTolerance *= m_CrimeAccumulationToleranceMultiplier;
		componentData.m_HomeCrimeEffect *= m_HomeCrimeEffectMultiplier;
		componentData.m_WorkplaceCrimeEffect *= m_WorkplaceCrimeEffectMultiplier;
		componentData.m_WelfareCrimeRecurrenceFactor = m_WelfareCrimeRecurrenceFactor;
		componentData.m_CrimePoliceCoverageFactor *= m_CrimePoliceCoverageFactorMultiflier;
		componentData.m_CrimePopulationReduction *= m_CrimePopulationReductionMultiplier;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<PoliceConfigurationData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<PoliceConfigurationData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		PoliceConfigurationPrefab policeConfigurationPrefab = prefabSystem.GetPrefab<PoliceConfigurationPrefab>(entity);
		PoliceConfigurationData componentData = entityManager.GetComponentData<PoliceConfigurationData>(entity);
		componentData.m_MaxCrimeAccumulation = policeConfigurationPrefab.m_MaxCrimeAccumulation;
		componentData.m_CrimeAccumulationTolerance = policeConfigurationPrefab.m_CrimeAccumulationTolerance;
		componentData.m_HomeCrimeEffect = policeConfigurationPrefab.m_HomeCrimeEffect;
		componentData.m_WorkplaceCrimeEffect = policeConfigurationPrefab.m_WorkplaceCrimeEffect;
		componentData.m_WelfareCrimeRecurrenceFactor = policeConfigurationPrefab.m_WelfareCrimeRecurrenceFactor;
		componentData.m_CrimePoliceCoverageFactor = policeConfigurationPrefab.m_CrimePoliceCoverageFactor;
		componentData.m_CrimePopulationReduction = policeConfigurationPrefab.m_CrimePopulationReduction;
		entityManager.SetComponentData(entity, componentData);
	}
```


