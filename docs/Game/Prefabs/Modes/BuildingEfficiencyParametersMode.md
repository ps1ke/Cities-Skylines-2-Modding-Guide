# Game.Prefabs.Modes.BuildingEfficiencyParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingEfficiencyParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public UnityEngine.AnimationCurve m_ServiceBudgetEfficiencyFactor;
    public System.Single m_LowEfficiencyThreshold;
    public System.Single m_ElectricityPenalty;
    public System.Int16 m_ElectricityPenaltyDelay;
    public UnityEngine.AnimationCurve m_ElectricityFeeFactor;
    public System.Single m_WaterPenalty;
    public System.Byte m_WaterPenaltyDelay;
    public System.Single m_WaterPollutionPenalty;
    public System.Single m_SewagePenalty;
    public System.Byte m_SewagePenaltyDelay;
    public UnityEngine.AnimationCurve m_WaterFeeFactor;
    public System.Single m_GarbagePenalty;
    public System.Int32 m_NegligibleMail;
    public System.Single m_MailEfficiencyPenalty;
    public System.Single m_TelecomBaseline;
    public System.Single m_MissingEmployeesEfficiencyPenalty;
    public System.Int16 m_MissingEmployeesEfficiencyDelay;
    public System.Int16 m_ServiceBuildingEfficiencyGracePeriod;
    public System.Single m_SickEmployeesEfficiencyPenalty;

    public BuildingEfficiencyParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public UnityEngine.AnimationCurve m_ServiceBudgetEfficiencyFactor`  

```csharp
public UnityEngine.AnimationCurve m_ServiceBudgetEfficiencyFactor;
```

- `public System.Single m_LowEfficiencyThreshold`  

```csharp
public System.Single m_LowEfficiencyThreshold;
```

- `public System.Single m_ElectricityPenalty`  

```csharp
public System.Single m_ElectricityPenalty;
```

- `public System.Int16 m_ElectricityPenaltyDelay`  

```csharp
public System.Int16 m_ElectricityPenaltyDelay;
```

- `public UnityEngine.AnimationCurve m_ElectricityFeeFactor`  

```csharp
public UnityEngine.AnimationCurve m_ElectricityFeeFactor;
```

- `public System.Single m_WaterPenalty`  

```csharp
public System.Single m_WaterPenalty;
```

- `public System.Byte m_WaterPenaltyDelay`  

```csharp
public System.Byte m_WaterPenaltyDelay;
```

- `public System.Single m_WaterPollutionPenalty`  

```csharp
public System.Single m_WaterPollutionPenalty;
```

- `public System.Single m_SewagePenalty`  

```csharp
public System.Single m_SewagePenalty;
```

- `public System.Byte m_SewagePenaltyDelay`  

```csharp
public System.Byte m_SewagePenaltyDelay;
```

- `public UnityEngine.AnimationCurve m_WaterFeeFactor`  

```csharp
public UnityEngine.AnimationCurve m_WaterFeeFactor;
```

- `public System.Single m_GarbagePenalty`  

```csharp
public System.Single m_GarbagePenalty;
```

- `public System.Int32 m_NegligibleMail`  

```csharp
public System.Int32 m_NegligibleMail;
```

- `public System.Single m_MailEfficiencyPenalty`  

```csharp
public System.Single m_MailEfficiencyPenalty;
```

- `public System.Single m_TelecomBaseline`  

```csharp
public System.Single m_TelecomBaseline;
```

- `public System.Single m_MissingEmployeesEfficiencyPenalty`  

```csharp
public System.Single m_MissingEmployeesEfficiencyPenalty;
```

- `public System.Int16 m_MissingEmployeesEfficiencyDelay`  

```csharp
public System.Int16 m_MissingEmployeesEfficiencyDelay;
```

- `public System.Int16 m_ServiceBuildingEfficiencyGracePeriod`  

```csharp
public System.Int16 m_ServiceBuildingEfficiencyGracePeriod;
```

- `public System.Single m_SickEmployeesEfficiencyPenalty`  

```csharp
public System.Single m_SickEmployeesEfficiencyPenalty;
```


## Constructors

- `public BuildingEfficiencyParametersMode()`  

```csharp
public BuildingEfficiencyParametersMode();
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


