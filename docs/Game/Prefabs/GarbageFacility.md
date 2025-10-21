# Game.Prefabs.GarbageFacility

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class GarbageFacility : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_GarbageCapacity;
    public System.Int32 m_VehicleCapacity;
    public System.Int32 m_TransportCapacity;
    public System.Int32 m_ProcessingSpeed;
    public System.Boolean m_IndustrialWasteOnly;
    public System.Boolean m_LongTermStorage;

    public GarbageFacility();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_GarbageCapacity`  

```csharp
public System.Int32 m_GarbageCapacity;
```

- `public System.Int32 m_VehicleCapacity`  

```csharp
public System.Int32 m_VehicleCapacity;
```

- `public System.Int32 m_TransportCapacity`  

```csharp
public System.Int32 m_TransportCapacity;
```

- `public System.Int32 m_ProcessingSpeed`  

```csharp
public System.Int32 m_ProcessingSpeed;
```

- `public System.Boolean m_IndustrialWasteOnly`  

```csharp
public System.Boolean m_IndustrialWasteOnly;
```

- `public System.Boolean m_LongTermStorage`  

```csharp
public System.Boolean m_LongTermStorage;
```


## Constructors

- `public GarbageFacility()`  

```csharp
public GarbageFacility();
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


