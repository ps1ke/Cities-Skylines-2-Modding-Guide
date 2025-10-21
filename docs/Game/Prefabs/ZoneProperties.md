# Game.Prefabs.ZoneProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IZoneBuildingComponent`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZoneProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IZoneBuildingComponent
{
    public System.Boolean m_ScaleResidentials;
    public System.Single m_ResidentialProperties;
    public System.Single m_SpaceMultiplier;
    public Game.Economy.ResourceInEditor[] m_AllowedSold;
    public Game.Economy.ResourceInEditor[] m_AllowedInput;
    public Game.Economy.ResourceInEditor[] m_AllowedManufactured;
    public Game.Economy.ResourceInEditor[] m_AllowedStored;
    public System.Single m_FireHazardMultiplier;
    public System.Boolean m_IgnoreLandValue;

    public ZoneProperties();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
    public System.Void GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
    private Game.Prefabs.BuildingPropertyData GetBuildingPropertyData(Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public System.Void InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
}
```


## Fields

- `public System.Boolean m_ScaleResidentials`  

```csharp
public System.Boolean m_ScaleResidentials;
```

- `public System.Single m_ResidentialProperties`  

```csharp
public System.Single m_ResidentialProperties;
```

- `public System.Single m_SpaceMultiplier`  

```csharp
public System.Single m_SpaceMultiplier;
```

- `public Game.Economy.ResourceInEditor[] m_AllowedSold`  

```csharp
public Game.Economy.ResourceInEditor[] m_AllowedSold;
```

- `public Game.Economy.ResourceInEditor[] m_AllowedInput`  

```csharp
public Game.Economy.ResourceInEditor[] m_AllowedInput;
```

- `public Game.Economy.ResourceInEditor[] m_AllowedManufactured`  

```csharp
public Game.Economy.ResourceInEditor[] m_AllowedManufactured;
```

- `public Game.Economy.ResourceInEditor[] m_AllowedStored`  

```csharp
public Game.Economy.ResourceInEditor[] m_AllowedStored;
```

- `public System.Single m_FireHazardMultiplier`  

```csharp
public System.Single m_FireHazardMultiplier;
```

- `public System.Boolean m_IgnoreLandValue`  

```csharp
public System.Boolean m_IgnoreLandValue;
```


## Constructors

- `public ZoneProperties()`  

```csharp
public ZoneProperties();
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

- `public GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public System.Void GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
```

- `private GetBuildingPropertyData(Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : Game.Prefabs.BuildingPropertyData`  

```csharp
private Game.Prefabs.BuildingPropertyData GetBuildingPropertyData(Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
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


