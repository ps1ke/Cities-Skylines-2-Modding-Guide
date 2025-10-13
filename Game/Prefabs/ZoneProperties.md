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
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void GetBuildingArchetypeComponents(HashSet<ComponentType> components, BuildingPrefab buildingPrefab, byte level)
	{
		if (!buildingPrefab.Has<BuildingProperties>())
		{
			BuildingPropertyData buildingPropertyData = GetBuildingPropertyData(buildingPrefab, level);
			BuildingProperties.AddArchetypeComponents(components, buildingPropertyData);
		}
	}
```

- `public GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void GetBuildingPrefabComponents(HashSet<ComponentType> components, BuildingPrefab buildingPrefab, byte level)
	{
		components.Add(ComponentType.ReadWrite<BuildingPropertyData>());
	}
```

- `private GetBuildingPropertyData(Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : Game.Prefabs.BuildingPropertyData`  

```csharp
private BuildingPropertyData GetBuildingPropertyData(BuildingPrefab buildingPrefab, byte level)
	{
		float num = (m_ScaleResidentials ? ((1f + 0.25f * (float)(level - 1)) * (float)buildingPrefab.lotSize) : 1f);
		return new BuildingPropertyData
		{
			m_ResidentialProperties = (int)math.round(num * m_ResidentialProperties),
			m_AllowedSold = EconomyUtils.GetResources(m_AllowedSold, Resource.NoResource),
			m_AllowedInput = EconomyUtils.GetResources(m_AllowedInput, EconomyUtils.GetAllResources()),
			m_AllowedManufactured = EconomyUtils.GetResources(m_AllowedManufactured, Resource.NoResource),
			m_AllowedStored = EconomyUtils.GetResources(m_AllowedStored, Resource.NoResource),
			m_SpaceMultiplier = m_SpaceMultiplier
		};
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ZonePropertiesData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new ZonePropertiesData
		{
			m_ScaleResidentials = m_ScaleResidentials,
			m_ResidentialProperties = m_ResidentialProperties,
			m_SpaceMultiplier = m_SpaceMultiplier,
			m_FireHazardMultiplier = m_FireHazardMultiplier,
			m_IgnoreLandValue = m_IgnoreLandValue,
			m_AllowedSold = EconomyUtils.GetResources(m_AllowedSold, Resource.NoResource),
			m_AllowedManufactured = EconomyUtils.GetResources(m_AllowedManufactured, Resource.NoResource),
			m_AllowedStored = EconomyUtils.GetResources(m_AllowedStored, Resource.NoResource)
		});
	}
```

- `public InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void InitializeBuilding(EntityManager entityManager, Entity entity, BuildingPrefab buildingPrefab, byte level)
	{
		if (!buildingPrefab.Has<BuildingProperties>())
		{
			BuildingPropertyData buildingPropertyData = GetBuildingPropertyData(buildingPrefab, level);
			entityManager.SetComponentData(entity, buildingPropertyData);
		}
	}
```


