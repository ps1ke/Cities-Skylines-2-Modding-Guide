# Game.Prefabs.TransportStation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportStation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public Game.Vehicles.EnergyTypes m_CarRefuelTypes;
    public Game.Vehicles.EnergyTypes m_TrainRefuelTypes;
    public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes;
    public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes;
    public System.Single m_ComfortFactor;

    public TransportStation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Vehicles.EnergyTypes m_CarRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_CarRefuelTypes;
```

- `public Game.Vehicles.EnergyTypes m_TrainRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_TrainRefuelTypes;
```

- `public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes;
```

- `public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes;
```

- `public System.Single m_ComfortFactor`  

```csharp
public System.Single m_ComfortFactor;
```


## Constructors

- `public TransportStation()`  

```csharp
public TransportStation();
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


