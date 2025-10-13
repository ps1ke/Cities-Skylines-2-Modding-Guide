# Game.Prefabs.DisasterConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DisasterConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_WeatherDamageNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_WeatherDestroyedNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_WaterDamageNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_WaterDestroyedNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_DestroyedNotificationPrefab;
    public System.Single m_FloodDamageRate;
    public UnityEngine.AnimationCurve m_EmergencyShelterDangerLevelExitProbability;
    public System.Single m_InoperableEmergencyShelterExitProbability;

    public DisasterConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_WeatherDamageNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_WeatherDamageNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_WeatherDestroyedNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_WeatherDestroyedNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_WaterDamageNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_WaterDamageNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_WaterDestroyedNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_WaterDestroyedNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_DestroyedNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_DestroyedNotificationPrefab;
```

- `public System.Single m_FloodDamageRate`  

```csharp
public System.Single m_FloodDamageRate;
```

- `public UnityEngine.AnimationCurve m_EmergencyShelterDangerLevelExitProbability`  

```csharp
public UnityEngine.AnimationCurve m_EmergencyShelterDangerLevelExitProbability;
```

- `public System.Single m_InoperableEmergencyShelterExitProbability`  

```csharp
public System.Single m_InoperableEmergencyShelterExitProbability;
```


## Constructors

- `public DisasterConfigurationPrefab()`  

```csharp
public DisasterConfigurationPrefab();
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


