# Game.Prefabs.ElectricityParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ElectricityParametersPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_InitialBatteryCharge;
    public UnityEngine.AnimationCurve m_TemperatureConsumptionMultiplier;
    public System.Single m_CloudinessSolarPenalty;
    public Game.Prefabs.ServicePrefab m_ElectricityServicePrefab;
    public Game.Prefabs.NotificationIconPrefab m_ElectricityNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_LowVoltageNotConnectedPrefab;
    public Game.Prefabs.NotificationIconPrefab m_HighVoltageNotConnectedPrefab;
    public Game.Prefabs.NotificationIconPrefab m_BottleneckNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_BuildingBottleneckNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughProductionNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_TransformerNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughConnectedNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_BatteryEmptyNotificationPrefab;

    public ElectricityParametersPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_InitialBatteryCharge`  

```csharp
public System.Single m_InitialBatteryCharge;
```

- `public UnityEngine.AnimationCurve m_TemperatureConsumptionMultiplier`  

```csharp
public UnityEngine.AnimationCurve m_TemperatureConsumptionMultiplier;
```

- `public System.Single m_CloudinessSolarPenalty`  

```csharp
public System.Single m_CloudinessSolarPenalty;
```

- `public Game.Prefabs.ServicePrefab m_ElectricityServicePrefab`  

```csharp
public Game.Prefabs.ServicePrefab m_ElectricityServicePrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_ElectricityNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_ElectricityNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_LowVoltageNotConnectedPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_LowVoltageNotConnectedPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_HighVoltageNotConnectedPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_HighVoltageNotConnectedPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_BottleneckNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_BottleneckNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_BuildingBottleneckNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_BuildingBottleneckNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughProductionNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughProductionNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_TransformerNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_TransformerNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughConnectedNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughConnectedNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_BatteryEmptyNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_BatteryEmptyNotificationPrefab;
```


## Constructors

- `public ElectricityParametersPrefab()`  

```csharp
public ElectricityParametersPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_ElectricityServicePrefab);
		prefabs.Add(m_ElectricityNotificationPrefab);
		prefabs.Add(m_LowVoltageNotConnectedPrefab);
		prefabs.Add(m_HighVoltageNotConnectedPrefab);
		prefabs.Add(m_BottleneckNotificationPrefab);
		prefabs.Add(m_BuildingBottleneckNotificationPrefab);
		prefabs.Add(m_NotEnoughProductionNotificationPrefab);
		prefabs.Add(m_TransformerNotificationPrefab);
		prefabs.Add(m_NotEnoughConnectedNotificationPrefab);
		prefabs.Add(m_BatteryEmptyNotificationPrefab);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ElectricityParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new ElectricityParameterData
		{
			m_InitialBatteryCharge = m_InitialBatteryCharge,
			m_TemperatureConsumptionMultiplier = new AnimationCurve1(m_TemperatureConsumptionMultiplier),
			m_CloudinessSolarPenalty = m_CloudinessSolarPenalty,
			m_ElectricityServicePrefab = orCreateSystemManaged.GetEntity(m_ElectricityServicePrefab),
			m_ElectricityNotificationPrefab = orCreateSystemManaged.GetEntity(m_ElectricityNotificationPrefab),
			m_LowVoltageNotConnectedPrefab = orCreateSystemManaged.GetEntity(m_LowVoltageNotConnectedPrefab),
			m_HighVoltageNotConnectedPrefab = orCreateSystemManaged.GetEntity(m_HighVoltageNotConnectedPrefab),
			m_BottleneckNotificationPrefab = orCreateSystemManaged.GetEntity(m_BottleneckNotificationPrefab),
			m_BuildingBottleneckNotificationPrefab = orCreateSystemManaged.GetEntity(m_BuildingBottleneckNotificationPrefab),
			m_NotEnoughProductionNotificationPrefab = orCreateSystemManaged.GetEntity(m_NotEnoughProductionNotificationPrefab),
			m_TransformerNotificationPrefab = orCreateSystemManaged.GetEntity(m_TransformerNotificationPrefab),
			m_NotEnoughConnectedNotificationPrefab = orCreateSystemManaged.GetEntity(m_NotEnoughConnectedNotificationPrefab),
			m_BatteryEmptyNotificationPrefab = orCreateSystemManaged.GetEntity(m_BatteryEmptyNotificationPrefab)
		});
	}
```


