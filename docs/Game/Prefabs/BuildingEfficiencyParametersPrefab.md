# Game.Prefabs.BuildingEfficiencyParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingEfficiencyParametersPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
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

    public BuildingEfficiencyParametersPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
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

- `public BuildingEfficiencyParametersPrefab()`  

```csharp
public BuildingEfficiencyParametersPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


