# Game.Prefabs.TransportDepot

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportDepot : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public Game.Prefabs.TransportType m_TransportType;
    public Game.Vehicles.EnergyTypes m_EnergyTypes;
    public Game.Vehicles.SizeClass m_SizeClass;
    public System.Int32 m_VehicleCapacity;
    public System.Single m_ProductionDuration;
    public System.Single m_MaintenanceDuration;
    public System.Boolean m_DispatchCenter;

    public TransportDepot();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public Game.Vehicles.EnergyTypes m_EnergyTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_EnergyTypes;
```

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public System.Int32 m_VehicleCapacity`  

```csharp
public System.Int32 m_VehicleCapacity;
```

- `public System.Single m_ProductionDuration`  

```csharp
public System.Single m_ProductionDuration;
```

- `public System.Single m_MaintenanceDuration`  

```csharp
public System.Single m_MaintenanceDuration;
```

- `public System.Boolean m_DispatchCenter`  

```csharp
public System.Boolean m_DispatchCenter;
```


## Constructors

- `public TransportDepot()`  

```csharp
public TransportDepot();
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

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


