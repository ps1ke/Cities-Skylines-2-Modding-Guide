# Game.Prefabs.WaterPipeParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WaterPipeParametersPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase m_WaterService;
    public Game.Prefabs.NotificationIconPrefab m_WaterNotification;
    public Game.Prefabs.NotificationIconPrefab m_DirtyWaterNotification;
    public Game.Prefabs.NotificationIconPrefab m_SewageNotification;
    public Game.Prefabs.NotificationIconPrefab m_WaterPipeNotConnectedNotification;
    public Game.Prefabs.NotificationIconPrefab m_SewagePipeNotConnectedNotification;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughWaterCapacityNotification;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughSewageCapacityNotification;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughGroundwaterNotification;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughSurfaceWaterNotification;
    public Game.Prefabs.NotificationIconPrefab m_DirtyWaterPumpNotification;
    public System.Single m_GroundwaterReplenish;
    public System.Int32 m_GroundwaterPurification;
    public System.Single m_GroundwaterUsageMultiplier;
    public System.Single m_GroundwaterPumpEffectiveAmount;
    public System.Single m_SurfaceWaterUsageMultiplier;
    public System.Single m_SurfaceWaterPumpEffectiveDepth;
    public System.Single m_MaxToleratedPollution;
    public System.Int32 m_WaterPipePollutionSpreadInterval;
    public System.Single m_StaleWaterPipePurification;

    public WaterPipeParametersPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase m_WaterService`  

```csharp
public Game.Prefabs.PrefabBase m_WaterService;
```

- `public Game.Prefabs.NotificationIconPrefab m_WaterNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_WaterNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_DirtyWaterNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_DirtyWaterNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_SewageNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_SewageNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_WaterPipeNotConnectedNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_WaterPipeNotConnectedNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_SewagePipeNotConnectedNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_SewagePipeNotConnectedNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughWaterCapacityNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughWaterCapacityNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughSewageCapacityNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughSewageCapacityNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughGroundwaterNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughGroundwaterNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughSurfaceWaterNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughSurfaceWaterNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_DirtyWaterPumpNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_DirtyWaterPumpNotification;
```

- `public System.Single m_GroundwaterReplenish`  

```csharp
public System.Single m_GroundwaterReplenish;
```

- `public System.Int32 m_GroundwaterPurification`  

```csharp
public System.Int32 m_GroundwaterPurification;
```

- `public System.Single m_GroundwaterUsageMultiplier`  

```csharp
public System.Single m_GroundwaterUsageMultiplier;
```

- `public System.Single m_GroundwaterPumpEffectiveAmount`  

```csharp
public System.Single m_GroundwaterPumpEffectiveAmount;
```

- `public System.Single m_SurfaceWaterUsageMultiplier`  

```csharp
public System.Single m_SurfaceWaterUsageMultiplier;
```

- `public System.Single m_SurfaceWaterPumpEffectiveDepth`  

```csharp
public System.Single m_SurfaceWaterPumpEffectiveDepth;
```

- `public System.Single m_MaxToleratedPollution`  

```csharp
public System.Single m_MaxToleratedPollution;
```

- `public System.Int32 m_WaterPipePollutionSpreadInterval`  

```csharp
public System.Int32 m_WaterPipePollutionSpreadInterval;
```

- `public System.Single m_StaleWaterPipePurification`  

```csharp
public System.Single m_StaleWaterPipePurification;
```


## Constructors

- `public WaterPipeParametersPrefab()`  

```csharp
public WaterPipeParametersPrefab();
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


