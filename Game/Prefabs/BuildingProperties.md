# Game.Prefabs.BuildingProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_ResidentialProperties;
    public Game.Economy.ResourceInEditor[] m_AllowedSold;
    public Game.Economy.ResourceInEditor[] m_AllowedInput;
    public Game.Economy.ResourceInEditor[] m_AllowedManufactured;
    public Game.Economy.ResourceInEditor[] m_AllowedStored;
    public System.Single m_SpaceMultiplier;

    public BuildingProperties();

    public static System.Void AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPropertyData propertyData);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public Game.Prefabs.BuildingPropertyData GetPropertyData();
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_ResidentialProperties`  

```csharp
public System.Int32 m_ResidentialProperties;
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

- `public System.Single m_SpaceMultiplier`  

```csharp
public System.Single m_SpaceMultiplier;
```


## Constructors

- `public BuildingProperties()`  

```csharp
public BuildingProperties();
```


## Methods

- `public static AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPropertyData propertyData) : System.Void`  

```csharp
public static System.Void AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPropertyData propertyData);
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public GetPropertyData() : Game.Prefabs.BuildingPropertyData`  

```csharp
public Game.Prefabs.BuildingPropertyData GetPropertyData();
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


