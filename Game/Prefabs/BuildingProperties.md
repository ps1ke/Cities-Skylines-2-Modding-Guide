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
public static void AddArchetypeComponents(HashSet<ComponentType> components, BuildingPropertyData propertyData)
	{
		components.Add(ComponentType.ReadWrite<Renter>());
		if (propertyData.m_ResidentialProperties > 0)
		{
			components.Add(ComponentType.ReadWrite<ResidentialProperty>());
			components.Add(ComponentType.ReadWrite<BuildingNotifications>());
			components.Add(ComponentType.ReadWrite<PropertyToBeOnMarket>());
		}
		if (propertyData.m_AllowedSold != Resource.NoResource)
		{
			components.Add(ComponentType.ReadWrite<CommercialProperty>());
			components.Add(ComponentType.ReadWrite<PropertyToBeOnMarket>());
			components.Add(ComponentType.ReadWrite<Efficiency>());
		}
		if (propertyData.m_AllowedManufactured != Resource.NoResource)
		{
			components.Add(ComponentType.ReadWrite<IndustrialProperty>());
			components.Add(ComponentType.ReadWrite<PropertyToBeOnMarket>());
			components.Add(ComponentType.ReadWrite<Efficiency>());
			if (EconomyUtils.IsExtractorResource(propertyData.m_AllowedManufactured))
			{
				components.Add(ComponentType.ReadWrite<ExtractorProperty>());
			}
			if (EconomyUtils.IsOfficeResource(propertyData.m_AllowedManufactured))
			{
				components.Add(ComponentType.ReadWrite<OfficeProperty>());
			}
		}
		if (propertyData.m_AllowedStored != Resource.NoResource)
		{
			components.Add(ComponentType.ReadWrite<IndustrialProperty>());
			components.Add(ComponentType.ReadWrite<StorageProperty>());
			components.Add(ComponentType.ReadWrite<PropertyToBeOnMarket>());
		}
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (!base.prefab.Has<PlaceholderBuilding>())
		{
			AddArchetypeComponents(components, GetPropertyData());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<BuildingPropertyData>());
		if (EconomyUtils.GetResources(m_AllowedStored, Resource.NoResource) != Resource.NoResource)
		{
			components.Add(ComponentType.ReadWrite<WarehouseData>());
		}
	}
```

- `public GetPropertyData() : Game.Prefabs.BuildingPropertyData`  

```csharp
public BuildingPropertyData GetPropertyData()
	{
		return new BuildingPropertyData
		{
			m_ResidentialProperties = m_ResidentialProperties,
			m_SpaceMultiplier = m_SpaceMultiplier,
			m_AllowedSold = EconomyUtils.GetResources(m_AllowedSold, Resource.NoResource),
			m_AllowedInput = EconomyUtils.GetResources(m_AllowedInput, EconomyUtils.GetAllResources()),
			m_AllowedManufactured = EconomyUtils.GetResources(m_AllowedManufactured, Resource.NoResource),
			m_AllowedStored = EconomyUtils.GetResources(m_AllowedStored, Resource.NoResource)
		};
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, GetPropertyData());
	}
```


