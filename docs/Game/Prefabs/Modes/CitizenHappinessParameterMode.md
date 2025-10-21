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
public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
```


