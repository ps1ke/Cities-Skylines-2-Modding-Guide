# Game.Prefabs.PublicTransport

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ExcludeGeneratedModTag`, `ComponentMenu`  

## Code

```csharp
public class PublicTransport : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.TransportType m_TransportType;
    public System.Int32 m_PassengerCapacity;
    public Game.Prefabs.PublicTransportPurpose m_Purposes;
    public System.Single m_MaintenanceRange;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public PublicTransport();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
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

- `public System.Int32 m_PassengerCapacity`  

```csharp
public System.Int32 m_PassengerCapacity;
```

- `public Game.Prefabs.PublicTransportPurpose m_Purposes`  

```csharp
public Game.Prefabs.PublicTransportPurpose m_Purposes;
```

- `public System.Single m_MaintenanceRange`  

```csharp
public System.Single m_MaintenanceRange;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public PublicTransport()`  

```csharp
public PublicTransport();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

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


## Nested types

- `Game.Prefabs.PublicTransport+<get_modTags>d__8`  

