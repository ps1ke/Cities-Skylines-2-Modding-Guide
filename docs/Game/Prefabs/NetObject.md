# Game.Prefabs.NetObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.NetPieceRequirements[] m_SetCompositionState;
    public Game.Net.RoadTypes m_RequireRoad;
    public Game.Net.RoadTypes m_RoadPassThrough;
    public Game.Net.TrackTypes m_TrackPassThrough;
    public System.Single m_NodeOffset;
    public System.Boolean m_Attached;

    public NetObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NetPieceRequirements[] m_SetCompositionState`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_SetCompositionState;
```

- `public Game.Net.RoadTypes m_RequireRoad`  

```csharp
public Game.Net.RoadTypes m_RequireRoad;
```

- `public Game.Net.RoadTypes m_RoadPassThrough`  

```csharp
public Game.Net.RoadTypes m_RoadPassThrough;
```

- `public Game.Net.TrackTypes m_TrackPassThrough`  

```csharp
public Game.Net.TrackTypes m_TrackPassThrough;
```

- `public System.Single m_NodeOffset`  

```csharp
public System.Single m_NodeOffset;
```

- `public System.Boolean m_Attached`  

```csharp
public System.Boolean m_Attached;
```


## Constructors

- `public NetObject()`  

```csharp
public NetObject();
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


