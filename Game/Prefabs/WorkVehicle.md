# Game.Prefabs.WorkVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WorkVehicle : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Vehicles.VehicleWorkType m_WorkType;
    public Game.Areas.MapFeature m_MapFeature;
    public Game.Economy.ResourceInEditor[] m_Resources;
    public System.Single m_MaxWorkAmount;

    public WorkVehicle();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Vehicles.VehicleWorkType m_WorkType`  

```csharp
public Game.Vehicles.VehicleWorkType m_WorkType;
```

- `public Game.Areas.MapFeature m_MapFeature`  

```csharp
public Game.Areas.MapFeature m_MapFeature;
```

- `public Game.Economy.ResourceInEditor[] m_Resources`  

```csharp
public Game.Economy.ResourceInEditor[] m_Resources;
```

- `public System.Single m_MaxWorkAmount`  

```csharp
public System.Single m_MaxWorkAmount;
```


## Constructors

- `public WorkVehicle()`  

```csharp
public WorkVehicle();
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


