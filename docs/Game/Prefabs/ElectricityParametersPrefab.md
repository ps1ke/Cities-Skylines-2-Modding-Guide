# Game.Prefabs.ElectricityParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Single m_InitialBatteryCharge`  
- `public UnityEngine.AnimationCurve m_TemperatureConsumptionMultiplier`  
- `public System.Single m_CloudinessSolarPenalty`  
- `public Game.Prefabs.ServicePrefab m_ElectricityServicePrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_ElectricityNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_LowVoltageNotConnectedPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_HighVoltageNotConnectedPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_BottleneckNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_BuildingBottleneckNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughProductionNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_TransformerNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughConnectedNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_BatteryEmptyNotificationPrefab`  

## Constructors

- `public ElectricityParametersPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

