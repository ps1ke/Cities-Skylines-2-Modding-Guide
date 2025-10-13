# Game.Prefabs.CitizenHappinessPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CitizenHappinessPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_PollutionDivisor;
    public System.Int32 m_MaxAirAndGroundPollution;
    public System.Int32 m_MaxNoisePollution;
    public System.Single m_ElectricityWellbeingPenalty;
    public System.Byte m_ElectricityPenaltyDelay;
    public UnityEngine.AnimationCurve m_ElectricityFeeWellbeingEffect;
    public System.Int32 m_WaterHealthPenalty;
    public System.Int32 m_WaterWellbeingPenalty;
    public System.Byte m_WaterPenaltyDelay;
    public System.Single m_WaterPollutionMultiplier;
    public System.Int32 m_SewageHealthEffect;
    public System.Int32 m_SewageWellbeingEffect;
    public System.Byte m_SewagePenaltyDelay;
    public UnityEngine.AnimationCurve m_WaterFeeHealthEffect;
    public UnityEngine.AnimationCurve m_WaterFeeWellbeingEffect;
    public Unity.Mathematics.int4 m_WealthyMoneyAmount;
    public System.Single m_HealthCareHealthMultiplier;
    public System.Single m_HealthCareWellbeingMultiplier;
    public System.Single m_EducationWellbeingMultiplier;
    public System.Single m_NeutralEducation;
    public System.Single m_EntertainmentWellbeingMultiplier;
    public System.Int32 m_NegligibleCrime;
    public System.Single m_CrimeMultiplier;
    public System.Int32 m_MaxCrimePenalty;
    public System.Single m_MailMultiplier;
    public System.Int32 m_NegligibleMail;
    public System.Single m_TelecomBaseline;
    public System.Single m_TelecomBonusMultiplier;
    public System.Single m_TelecomPenaltyMultiplier;
    public System.Single m_WelfareMultiplier;
    public System.Int32 m_HealthProblemHealthPenalty;
    public System.Int32 m_DeathWellbeingPenalty;
    public System.Int32 m_DeathHealthPenalty;
    public System.Single m_ConsumptionMultiplier;
    public System.Int32 m_LowWellbeing;
    public System.Int32 m_LowHealth;
    public System.Single m_TaxUneducatedMultiplier;
    public System.Single m_TaxPoorlyEducatedMultiplier;
    public System.Single m_TaxEducatedMultiplier;
    public System.Single m_TaxWellEducatedMultiplier;
    public System.Single m_TaxHighlyEducatedMultiplier;
    public System.Int32 m_PenaltyEffect;
    public System.Int32 m_HomelessHealthEffect;
    public System.Int32 m_HomelessWellbeingEffect;

    public CitizenHappinessPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_PollutionDivisor`  

```csharp
public System.Int32 m_PollutionDivisor;
```

- `public System.Int32 m_MaxAirAndGroundPollution`  

```csharp
public System.Int32 m_MaxAirAndGroundPollution;
```

- `public System.Int32 m_MaxNoisePollution`  

```csharp
public System.Int32 m_MaxNoisePollution;
```

- `public System.Single m_ElectricityWellbeingPenalty`  

```csharp
public System.Single m_ElectricityWellbeingPenalty;
```

- `public System.Byte m_ElectricityPenaltyDelay`  

```csharp
public System.Byte m_ElectricityPenaltyDelay;
```

- `public UnityEngine.AnimationCurve m_ElectricityFeeWellbeingEffect`  

```csharp
public UnityEngine.AnimationCurve m_ElectricityFeeWellbeingEffect;
```

- `public System.Int32 m_WaterHealthPenalty`  

```csharp
public System.Int32 m_WaterHealthPenalty;
```

- `public System.Int32 m_WaterWellbeingPenalty`  

```csharp
public System.Int32 m_WaterWellbeingPenalty;
```

- `public System.Byte m_WaterPenaltyDelay`  

```csharp
public System.Byte m_WaterPenaltyDelay;
```

- `public System.Single m_WaterPollutionMultiplier`  

```csharp
public System.Single m_WaterPollutionMultiplier;
```

- `public System.Int32 m_SewageHealthEffect`  

```csharp
public System.Int32 m_SewageHealthEffect;
```

- `public System.Int32 m_SewageWellbeingEffect`  

```csharp
public System.Int32 m_SewageWellbeingEffect;
```

- `public System.Byte m_SewagePenaltyDelay`  

```csharp
public System.Byte m_SewagePenaltyDelay;
```

- `public UnityEngine.AnimationCurve m_WaterFeeHealthEffect`  

```csharp
public UnityEngine.AnimationCurve m_WaterFeeHealthEffect;
```

- `public UnityEngine.AnimationCurve m_WaterFeeWellbeingEffect`  

```csharp
public UnityEngine.AnimationCurve m_WaterFeeWellbeingEffect;
```

- `public Unity.Mathematics.int4 m_WealthyMoneyAmount`  

```csharp
public Unity.Mathematics.int4 m_WealthyMoneyAmount;
```

- `public System.Single m_HealthCareHealthMultiplier`  

```csharp
public System.Single m_HealthCareHealthMultiplier;
```

- `public System.Single m_HealthCareWellbeingMultiplier`  

```csharp
public System.Single m_HealthCareWellbeingMultiplier;
```

- `public System.Single m_EducationWellbeingMultiplier`  

```csharp
public System.Single m_EducationWellbeingMultiplier;
```

- `public System.Single m_NeutralEducation`  

```csharp
public System.Single m_NeutralEducation;
```

- `public System.Single m_EntertainmentWellbeingMultiplier`  

```csharp
public System.Single m_EntertainmentWellbeingMultiplier;
```

- `public System.Int32 m_NegligibleCrime`  

```csharp
public System.Int32 m_NegligibleCrime;
```

- `public System.Single m_CrimeMultiplier`  

```csharp
public System.Single m_CrimeMultiplier;
```

- `public System.Int32 m_MaxCrimePenalty`  

```csharp
public System.Int32 m_MaxCrimePenalty;
```

- `public System.Single m_MailMultiplier`  

```csharp
public System.Single m_MailMultiplier;
```

- `public System.Int32 m_NegligibleMail`  

```csharp
public System.Int32 m_NegligibleMail;
```

- `public System.Single m_TelecomBaseline`  

```csharp
public System.Single m_TelecomBaseline;
```

- `public System.Single m_TelecomBonusMultiplier`  

```csharp
public System.Single m_TelecomBonusMultiplier;
```

- `public System.Single m_TelecomPenaltyMultiplier`  

```csharp
public System.Single m_TelecomPenaltyMultiplier;
```

- `public System.Single m_WelfareMultiplier`  

```csharp
public System.Single m_WelfareMultiplier;
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

- `public System.Single m_ConsumptionMultiplier`  

```csharp
public System.Single m_ConsumptionMultiplier;
```

- `public System.Int32 m_LowWellbeing`  

```csharp
public System.Int32 m_LowWellbeing;
```

- `public System.Int32 m_LowHealth`  

```csharp
public System.Int32 m_LowHealth;
```

- `public System.Single m_TaxUneducatedMultiplier`  

```csharp
public System.Single m_TaxUneducatedMultiplier;
```

- `public System.Single m_TaxPoorlyEducatedMultiplier`  

```csharp
public System.Single m_TaxPoorlyEducatedMultiplier;
```

- `public System.Single m_TaxEducatedMultiplier`  

```csharp
public System.Single m_TaxEducatedMultiplier;
```

- `public System.Single m_TaxWellEducatedMultiplier`  

```csharp
public System.Single m_TaxWellEducatedMultiplier;
```

- `public System.Single m_TaxHighlyEducatedMultiplier`  

```csharp
public System.Single m_TaxHighlyEducatedMultiplier;
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

- `public CitizenHappinessPrefab()`  

```csharp
public CitizenHappinessPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<CitizenHappinessParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		entityManager.SetComponentData(entity, new CitizenHappinessParameterData
		{
			m_WaterPollutionBonusMultiplier = m_WaterPollutionMultiplier,
			m_PollutionBonusDivisor = m_PollutionDivisor,
			m_MaxAirAndGroundPollutionBonus = m_MaxAirAndGroundPollution,
			m_MaxNoisePollutionBonus = m_MaxNoisePollution,
			m_ElectricityWellbeingPenalty = m_ElectricityWellbeingPenalty,
			m_ElectricityPenaltyDelay = (int)m_ElectricityPenaltyDelay,
			m_ElectricityFeeWellbeingEffect = new AnimationCurve1(m_ElectricityFeeWellbeingEffect),
			m_WaterHealthPenalty = m_WaterHealthPenalty,
			m_WaterWellbeingPenalty = m_WaterWellbeingPenalty,
			m_WaterPenaltyDelay = (int)m_WaterPenaltyDelay,
			m_SewageHealthEffect = m_SewageHealthEffect,
			m_SewageWellbeingEffect = m_SewageWellbeingEffect,
			m_SewagePenaltyDelay = (int)m_SewagePenaltyDelay,
			m_WaterFeeHealthEffect = new AnimationCurve1(m_WaterFeeHealthEffect),
			m_WaterFeeWellbeingEffect = new AnimationCurve1(m_WaterFeeWellbeingEffect),
			m_WealthyMoneyAmount = m_WealthyMoneyAmount,
			m_HealthCareHealthMultiplier = m_HealthCareHealthMultiplier,
			m_HealthCareWellbeingMultiplier = m_HealthCareWellbeingMultiplier,
			m_EducationWellbeingMultiplier = m_EducationWellbeingMultiplier,
			m_NeutralEducation = m_NeutralEducation,
			m_EntertainmentWellbeingMultiplier = m_EntertainmentWellbeingMultiplier,
			m_NegligibleCrime = m_NegligibleCrime,
			m_CrimeMultiplier = m_CrimeMultiplier,
			m_MaxCrimePenalty = m_MaxCrimePenalty,
			m_MailMultiplier = m_MailMultiplier,
			m_NegligibleMail = m_NegligibleMail,
			m_TelecomBaseline = m_TelecomBaseline,
			m_TelecomBonusMultiplier = m_TelecomBonusMultiplier,
			m_TelecomPenaltyMultiplier = m_TelecomPenaltyMultiplier,
			m_WelfareMultiplier = m_WelfareMultiplier,
			m_HealthProblemHealthPenalty = m_HealthProblemHealthPenalty,
			m_DeathHealthPenalty = m_DeathHealthPenalty,
			m_DeathWellbeingPenalty = m_DeathWellbeingPenalty,
			m_ConsumptionMultiplier = m_ConsumptionMultiplier,
			m_LowWellbeing = m_LowWellbeing,
			m_LowHealth = m_LowHealth,
			m_TaxUneducatedMultiplier = m_TaxUneducatedMultiplier,
			m_TaxPoorlyEducatedMultiplier = m_TaxPoorlyEducatedMultiplier,
			m_TaxEducatedMultiplier = m_TaxEducatedMultiplier,
			m_TaxWellEducatedMultiplier = m_TaxWellEducatedMultiplier,
			m_TaxHighlyEducatedMultiplier = m_TaxHighlyEducatedMultiplier,
			m_PenaltyEffect = m_PenaltyEffect,
			m_HomelessHealthEffect = m_HomelessHealthEffect,
			m_HomelessWellbeingEffect = m_HomelessWellbeingEffect
		});
	}
```


