# Game.Prefabs.SpawnLocation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SpawnLocation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.RouteConnectionType m_ConnectionType;
    public Game.Net.TrackTypes m_TrackTypes;
    public Game.Net.RoadTypes m_RoadTypes;
    public System.Boolean m_RequireAuthorization;
    public System.Boolean m_HangaroundOnLane;

    public SpawnLocation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.RouteConnectionType m_ConnectionType`  

```csharp
public Game.Prefabs.RouteConnectionType m_ConnectionType;
```

- `public Game.Net.TrackTypes m_TrackTypes`  

```csharp
public Game.Net.TrackTypes m_TrackTypes;
```

- `public Game.Net.RoadTypes m_RoadTypes`  

```csharp
public Game.Net.RoadTypes m_RoadTypes;
```

- `public System.Boolean m_RequireAuthorization`  

```csharp
public System.Boolean m_RequireAuthorization;
```

- `public System.Boolean m_HangaroundOnLane`  

```csharp
public System.Boolean m_HangaroundOnLane;
```


## Constructors

- `public SpawnLocation()`  

```csharp
public SpawnLocation();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


