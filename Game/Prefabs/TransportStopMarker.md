# Game.Prefabs.TransportStopMarker

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportStopMarker : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.TransportType m_TransportType;
    public System.Boolean m_PassengerTransport;
    public System.Boolean m_CargoTransport;
    public System.Boolean m_WorkStop;
    public System.Boolean m_WorkLocation;

    public TransportStopMarker();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public System.Boolean m_PassengerTransport`  

```csharp
public System.Boolean m_PassengerTransport;
```

- `public System.Boolean m_CargoTransport`  

```csharp
public System.Boolean m_CargoTransport;
```

- `public System.Boolean m_WorkStop`  

```csharp
public System.Boolean m_WorkStop;
```

- `public System.Boolean m_WorkLocation`  

```csharp
public System.Boolean m_WorkLocation;
```


## Constructors

- `public TransportStopMarker()`  

```csharp
public TransportStopMarker();
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


