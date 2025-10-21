# Game.Prefabs.RouteConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RouteConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_PathfindNotification;
    public Game.Prefabs.RoutePrefab m_CarPathVisualization;
    public Game.Prefabs.RoutePrefab m_WatercraftPathVisualization;
    public Game.Prefabs.RoutePrefab m_AircraftPathVisualization;
    public Game.Prefabs.RoutePrefab m_TrainPathVisualization;
    public Game.Prefabs.RoutePrefab m_HumanPathVisualization;
    public Game.Prefabs.RoutePrefab m_MissingRoutePrefab;

    public RouteConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_PathfindNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_PathfindNotification;
```

- `public Game.Prefabs.RoutePrefab m_CarPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_CarPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_WatercraftPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_WatercraftPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_AircraftPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_AircraftPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_TrainPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_TrainPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_HumanPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_HumanPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_MissingRoutePrefab`  

```csharp
public Game.Prefabs.RoutePrefab m_MissingRoutePrefab;
```


## Constructors

- `public RouteConfigurationPrefab()`  

```csharp
public RouteConfigurationPrefab();
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


