# Game.Prefabs.CargoTransport

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CargoTransport : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_CargoCapacity;
    public System.Int32 m_MaxResourceCount;
    public System.Single m_MaintenanceRange;
    public Game.Economy.ResourceInEditor[] m_TransportedResources;

    public CargoTransport();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_CargoCapacity`  

```csharp
public System.Int32 m_CargoCapacity;
```

- `public System.Int32 m_MaxResourceCount`  

```csharp
public System.Int32 m_MaxResourceCount;
```

- `public System.Single m_MaintenanceRange`  

```csharp
public System.Single m_MaintenanceRange;
```

- `public Game.Economy.ResourceInEditor[] m_TransportedResources`  

```csharp
public Game.Economy.ResourceInEditor[] m_TransportedResources;
```


## Constructors

- `public CargoTransport()`  

```csharp
public CargoTransport();
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


