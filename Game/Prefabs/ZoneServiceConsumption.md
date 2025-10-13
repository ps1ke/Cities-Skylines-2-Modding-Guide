# Game.Prefabs.ZoneServiceConsumption

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IZoneBuildingComponent`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZoneServiceConsumption : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IZoneBuildingComponent
{
    public System.Single m_Upkeep;
    public System.Single m_ElectricityConsumption;
    public System.Single m_WaterConsumption;
    public System.Single m_GarbageAccumulation;
    public System.Single m_TelecomNeed;

    public ZoneServiceConsumption();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
    private Game.Prefabs.ConsumptionData GetBuildingConsumptionData();
    public System.Void GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public System.Void InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
}
```


## Fields

- `public System.Single m_Upkeep`  

```csharp
public System.Single m_Upkeep;
```

- `public System.Single m_ElectricityConsumption`  

```csharp
public System.Single m_ElectricityConsumption;
```

- `public System.Single m_WaterConsumption`  

```csharp
public System.Single m_WaterConsumption;
```

- `public System.Single m_GarbageAccumulation`  

```csharp
public System.Single m_GarbageAccumulation;
```

- `public System.Single m_TelecomNeed`  

```csharp
public System.Single m_TelecomNeed;
```


## Constructors

- `public ZoneServiceConsumption()`  

```csharp
public ZoneServiceConsumption();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public System.Void GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
```

- `private GetBuildingConsumptionData() : Game.Prefabs.ConsumptionData`  

```csharp
private Game.Prefabs.ConsumptionData GetBuildingConsumptionData();
```

- `public GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public System.Void GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public System.Void InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
```


