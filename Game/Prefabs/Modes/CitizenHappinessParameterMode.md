# Game.Prefabs.Modes.CitizenHappinessParameterMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CitizenHappinessParameterMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_PollutionBonusDivisor;
    public System.Int32 m_MaxAirAndGroundPollutionBonus;
    public System.Int32 m_MaxNoisePollutionBonus;
    public System.Single m_ElectricityWellbeingPenaltyMultiplier;
    public System.Byte m_ElectricityPenaltyDelayMultiplier;
    public UnityEngine.AnimationCurve m_ElectricityFeeWellbeingEffect;
    public System.Int32 m_WaterHealthPenaltyMultiplier;
    public System.Int32 m_WaterWellbeingPenaltyMultiplier;
    public System.Byte m_WaterPenaltyDelayMultiplier;
    public System.Single m_WaterPollutionMultiplierOverriden;
    public System.Int32 m_SewageHealthEffectMultiplier;
    public System.Int32 m_SewageWellbeingEffectMultiplier;
    public System.Byte m_SewagePenaltyDelayMultiplier;
    public UnityEngine.AnimationCurve m_WaterFeeHealthEffect;
    public UnityEngine.AnimationCurve m_WaterFeeWellbeingEffect;
    public System.Int32 m_HealthProblemHealthPenalty;
    public System.Int32 m_DeathWellbeingPenalty;
    public System.Int32 m_DeathHealthPenalty;
    public System.Int32 m_LowWellbeing;
    public System.Int32 m_LowHealth;
    public System.Int32 m_PenaltyEffect;
    public System.Int32 m_HomelessHealthEffect;
    public System.Int32 m_HomelessWellbeingEffect;

    public CitizenHappinessParameterMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Int32 m_PollutionBonusDivisor`  

```csharp
public System.Int32 m_PollutionBonusDivisor;
```

- `public System.Int32 m_MaxAirAndGroundPollutionBonus`  

```csharp
public System.Int32 m_MaxAirAndGroundPollutionBonus;
```

- `public System.Int32 m_MaxNoisePollutionBonus`  

```csharp
public System.Int32 m_MaxNoisePollutionBonus;
```

- `public System.Single m_ElectricityWellbeingPenaltyMultiplier`  

```csharp
public System.Single m_ElectricityWellbeingPenaltyMultiplier;
```

- `public System.Byte m_ElectricityPenaltyDelayMultiplier`  

```csharp
public System.Byte m_ElectricityPenaltyDelayMultiplier;
```

- `public UnityEngine.AnimationCurve m_ElectricityFeeWellbeingEffect`  

```csharp
public UnityEngine.AnimationCurve m_ElectricityFeeWellbeingEffect;
```

- `public System.Int32 m_WaterHealthPenaltyMultiplier`  

```csharp
public System.Int32 m_WaterHealthPenaltyMultiplier;
```

- `public System.Int32 m_WaterWellbeingPenaltyMultiplier`  

```csharp
public System.Int32 m_WaterWellbeingPenaltyMultiplier;
```

- `public System.Byte m_WaterPenaltyDelayMultiplier`  

```csharp
public System.Byte m_WaterPenaltyDelayMultiplier;
```

- `public System.Single m_WaterPollutionMultiplierOverriden`  

```csharp
public System.Single m_WaterPollutionMultiplierOverriden;
```

- `public System.Int32 m_SewageHealthEffectMultiplier`  

```csharp
public System.Int32 m_SewageHealthEffectMultiplier;
```

- `public System.Int32 m_SewageWellbeingEffectMultiplier`  

```csharp
public System.Int32 m_SewageWellbeingEffectMultiplier;
```

- `public System.Byte m_SewagePenaltyDelayMultiplier`  

```csharp
public System.Byte m_SewagePenaltyDelayMultiplier;
```

- `public UnityEngine.AnimationCurve m_WaterFeeHealthEffect`  

```csharp
public UnityEngine.AnimationCurve m_WaterFeeHealthEffect;
```

- `public UnityEngine.AnimationCurve m_WaterFeeWellbeingEffect`  

```csharp
public UnityEngine.AnimationCurve m_WaterFeeWellbeingEffect;
```

- `public System.Int32 m_HealthProblemHealthPenalty`  

```csharp
public System.Int32 m_HealthProblemHealthPenalty;
```

- `public System.Int32 m_DeathWellbeingPenalty`  

```csharp
public System.Int32 m_DeathWellbeingPenalty;
```

- `public System.Int32 m_DeathHealthPenalty`  

```csharp
public System.Int32 m_DeathHealthPenalty;
```

- `public System.Int32 m_LowWellbeing`  

```csharp
public System.Int32 m_LowWellbeing;
```

- `public System.Int32 m_LowHealth`  

```csharp
public System.Int32 m_LowHealth;
```

- `public System.Int32 m_PenaltyEffect`  

```csharp
public System.Int32 m_PenaltyEffect;
```

- `public System.Int32 m_HomelessHealthEffect`  

```csharp
public System.Int32 m_HomelessHealthEffect;
```

- `public System.Int32 m_HomelessWellbeingEffect`  

```csharp
public System.Int32 m_HomelessWellbeingEffect;
```


## Constructors

- `public CitizenHappinessParameterMode()`  

```csharp
public CitizenHappinessParameterMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		CitizenHappinessParameterData componentData = entityManager.GetComponentData<CitizenHappinessParameterData>(singletonEntity);
		componentData.m_PollutionBonusDivisor = m_PollutionBonusDivisor;
		componentData.m_MaxAirAndGroundPollutionBonus = m_MaxAirAndGroundPollutionBonus;
		componentData.m_MaxNoisePollutionBonus = m_MaxNoisePollutionBonus;
		componentData.m_ElectricityWellbeingPenalty = m_ElectricityWellbeingPenaltyMultiplier;
		componentData.m_ElectricityPenaltyDelay = (int)m_ElectricityPenaltyDelayMultiplier;
		componentData.m_ElectricityFeeWellbeingEffect = new AnimationCurve1(m_ElectricityFeeWellbeingEffect);
		componentData.m_WaterHealthPenalty = m_WaterHealthPenaltyMultiplier;
		componentData.m_WaterWellbeingPenalty = m_WaterWellbeingPenaltyMultiplier;
		componentData.m_WaterPenaltyDelay = (int)m_WaterPenaltyDelayMultiplier;
		componentData.m_SewageHealthEffect = m_SewageHealthEffectMultiplier;
		componentData.m_SewageWellbeingEffect = m_SewageWellbeingEffectMultiplier;
		componentData.m_SewagePenaltyDelay = (int)m_SewagePenaltyDelayMultiplier;
		componentData.m_WaterPollutionBonusMultiplier = m_WaterPollutionMultiplierOverriden;
		componentData.m_WaterFeeHealthEffect = new AnimationCurve1(m_WaterFeeHealthEffect);
		componentData.m_WaterFeeWellbeingEffect = new AnimationCurve1(m_WaterFeeWellbeingEffect);
		componentData.m_HealthProblemHealthPenalty = m_HealthProblemHealthPenalty;
		componentData.m_DeathWellbeingPenalty = m_DeathWellbeingPenalty;
		componentData.m_DeathHealthPenalty = m_DeathHealthPenalty;
		componentData.m_LowWellbeing = m_LowWellbeing;
		componentData.m_LowHealth = m_LowHealth;
		componentData.m_PenaltyEffect = m_PenaltyEffect;
		componentData.m_HomelessHealthEffect = m_HomelessHealthEffect;
		componentData.m_HomelessWellbeingEffect = m_HomelessWellbeingEffect;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<CitizenHappinessParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<CitizenHappinessParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		CitizenHappinessPrefab citizenHappinessPrefab = prefabSystem.GetPrefab<CitizenHappinessPrefab>(entity);
		CitizenHappinessParameterData componentData = entityManager.GetComponentData<CitizenHappinessParameterData>(entity);
		componentData.m_PollutionBonusDivisor = citizenHappinessPrefab.m_PollutionDivisor;
		componentData.m_MaxAirAndGroundPollutionBonus = citizenHappinessPrefab.m_MaxAirAndGroundPollution;
		componentData.m_MaxNoisePollutionBonus = citizenHappinessPrefab.m_MaxNoisePollution;
		componentData.m_ElectricityWellbeingPenalty = citizenHappinessPrefab.m_ElectricityWellbeingPenalty;
		componentData.m_ElectricityPenaltyDelay = (int)citizenHappinessPrefab.m_ElectricityPenaltyDelay;
		componentData.m_ElectricityFeeWellbeingEffect = new AnimationCurve1(citizenHappinessPrefab.m_ElectricityFeeWellbeingEffect);
		componentData.m_WaterHealthPenalty = citizenHappinessPrefab.m_WaterHealthPenalty;
		componentData.m_WaterWellbeingPenalty = citizenHappinessPrefab.m_WaterWellbeingPenalty;
		componentData.m_WaterPenaltyDelay = (int)citizenHappinessPrefab.m_WaterPenaltyDelay;
		componentData.m_SewageHealthEffect = citizenHappinessPrefab.m_SewageHealthEffect;
		componentData.m_SewageWellbeingEffect = citizenHappinessPrefab.m_SewageWellbeingEffect;
		componentData.m_SewagePenaltyDelay = (int)citizenHappinessPrefab.m_SewagePenaltyDelay;
		componentData.m_WaterPollutionBonusMultiplier = citizenHappinessPrefab.m_WaterPollutionMultiplier;
		componentData.m_WaterFeeHealthEffect = new AnimationCurve1(citizenHappinessPrefab.m_WaterFeeHealthEffect);
		componentData.m_WaterFeeWellbeingEffect = new AnimationCurve1(citizenHappinessPrefab.m_WaterFeeWellbeingEffect);
		componentData.m_HealthProblemHealthPenalty = citizenHappinessPrefab.m_HealthProblemHealthPenalty;
		componentData.m_DeathWellbeingPenalty = citizenHappinessPrefab.m_DeathWellbeingPenalty;
		componentData.m_DeathHealthPenalty = citizenHappinessPrefab.m_DeathHealthPenalty;
		componentData.m_LowWellbeing = citizenHappinessPrefab.m_LowWellbeing;
		componentData.m_LowHealth = citizenHappinessPrefab.m_LowHealth;
		componentData.m_PenaltyEffect = citizenHappinessPrefab.m_PenaltyEffect;
		componentData.m_HomelessHealthEffect = citizenHappinessPrefab.m_HomelessHealthEffect;
		componentData.m_HomelessWellbeingEffect = citizenHappinessPrefab.m_HomelessWellbeingEffect;
		entityManager.SetComponentData(entity, componentData);
	}
```


