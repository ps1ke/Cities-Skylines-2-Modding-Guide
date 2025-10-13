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
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<BuildingEfficiencyParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		entityManager.SetComponentData(entity, new BuildingEfficiencyParameterData
		{
			m_ServiceBudgetEfficiencyFactor = new AnimationCurve1(m_ServiceBudgetEfficiencyFactor),
			m_LowEfficiencyThreshold = m_LowEfficiencyThreshold,
			m_ElectricityPenalty = m_ElectricityPenalty,
			m_ElectricityPenaltyDelay = m_ElectricityPenaltyDelay,
			m_ElectricityFeeFactor = new AnimationCurve1(m_ElectricityFeeFactor),
			m_WaterPenalty = m_WaterPenalty,
			m_WaterPenaltyDelay = (int)m_WaterPenaltyDelay,
			m_WaterPollutionPenalty = m_WaterPollutionPenalty,
			m_SewagePenalty = m_SewagePenalty,
			m_SewagePenaltyDelay = (int)m_SewagePenaltyDelay,
			m_WaterFeeFactor = new AnimationCurve1(m_WaterFeeFactor),
			m_GarbagePenalty = m_GarbagePenalty,
			m_NegligibleMail = m_NegligibleMail,
			m_MailEfficiencyPenalty = m_MailEfficiencyPenalty,
			m_TelecomBaseline = m_TelecomBaseline,
			m_MissingEmployeesEfficiencyPenalty = m_MissingEmployeesEfficiencyPenalty,
			m_MissingEmployeesEfficiencyDelay = m_MissingEmployeesEfficiencyDelay,
			m_ServiceBuildingEfficiencyGracePeriod = m_ServiceBuildingEfficiencyGracePeriod,
			m_SickEmployeesEfficiencyPenalty = m_SickEmployeesEfficiencyPenalty
		});
	}
```


