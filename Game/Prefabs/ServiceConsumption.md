# Game.Prefabs.ServiceConsumption

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ServiceConsumption : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_Upkeep;
    public System.Int32 m_ElectricityConsumption;
    public System.Int32 m_WaterConsumption;
    public System.Int32 m_GarbageAccumulation;
    public System.Single m_TelecomNeed;

    public ServiceConsumption();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    private Game.Prefabs.ConsumptionData GetConsumptionData();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_Upkeep`  

```csharp
public System.Int32 m_Upkeep;
```

- `public System.Int32 m_ElectricityConsumption`  

```csharp
public System.Int32 m_ElectricityConsumption;
```

- `public System.Int32 m_WaterConsumption`  

```csharp
public System.Int32 m_WaterConsumption;
```

- `public System.Int32 m_GarbageAccumulation`  

```csharp
public System.Int32 m_GarbageAccumulation;
```

- `public System.Single m_TelecomNeed`  

```csharp
public System.Single m_TelecomNeed;
```


## Constructors

- `public ServiceConsumption()`  

```csharp
public ServiceConsumption();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `private GetConsumptionData() : Game.Prefabs.ConsumptionData`  

```csharp
private Game.Prefabs.ConsumptionData GetConsumptionData();
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


