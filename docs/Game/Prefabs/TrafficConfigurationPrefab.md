# Game.Prefabs.TrafficConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TrafficConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_BottleneckNotification;
    public Game.Prefabs.NotificationIconPrefab m_DeadEndNotification;
    public Game.Prefabs.NotificationIconPrefab m_RoadConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_TrackConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_CarConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_ShipConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_TrainConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_PedestrianConnectionNotification;

    public TrafficConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_BottleneckNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_BottleneckNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_DeadEndNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_DeadEndNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_RoadConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_RoadConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_TrackConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_TrackConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_CarConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_CarConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_ShipConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_ShipConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_TrainConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_TrainConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_PedestrianConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_PedestrianConnectionNotification;
```


## Constructors

- `public TrafficConfigurationPrefab()`  

```csharp
public TrafficConfigurationPrefab();
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


