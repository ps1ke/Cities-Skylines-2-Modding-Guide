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
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


