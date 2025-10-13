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
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void GetBuildingArchetypeComponents(HashSet<ComponentType> components, BuildingPrefab buildingPrefab, byte level)
	{
		if (!buildingPrefab.Has<ServiceConsumption>())
		{
			GetBuildingConsumptionData().AddArchetypeComponents(components);
		}
	}
```

- `private GetBuildingConsumptionData() : Game.Prefabs.ConsumptionData`  

```csharp
private ConsumptionData GetBuildingConsumptionData()
	{
		return new ConsumptionData
		{
			m_Upkeep = 0,
			m_ElectricityConsumption = m_ElectricityConsumption,
			m_WaterConsumption = m_WaterConsumption,
			m_GarbageAccumulation = m_GarbageAccumulation,
			m_TelecomNeed = m_TelecomNeed
		};
	}
```

- `public GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void GetBuildingPrefabComponents(HashSet<ComponentType> components, BuildingPrefab buildingPrefab, byte level)
	{
		components.Add(ComponentType.ReadWrite<ConsumptionData>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ZoneServiceConsumptionData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new ZoneServiceConsumptionData
		{
			m_Upkeep = m_Upkeep,
			m_ElectricityConsumption = m_ElectricityConsumption,
			m_WaterConsumption = m_WaterConsumption,
			m_GarbageAccumulation = m_GarbageAccumulation,
			m_TelecomNeed = m_TelecomNeed
		});
	}
```

- `public InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void InitializeBuilding(EntityManager entityManager, Entity entity, BuildingPrefab buildingPrefab, byte level)
	{
		if (!buildingPrefab.Has<ServiceConsumption>())
		{
			entityManager.SetComponentData(entity, GetBuildingConsumptionData());
		}
	}
```


