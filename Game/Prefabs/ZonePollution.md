# Game.Prefabs.ZonePollution

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IZoneBuildingComponent`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZonePollution : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IZoneBuildingComponent
{
    public System.Single m_GroundPollution;
    public System.Single m_AirPollution;
    public System.Single m_NoisePollution;

    public ZonePollution();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
    private Game.Prefabs.PollutionData GetBuildingPollutionData(Game.Prefabs.BuildingPrefab buildingPrefab);
    public System.Void GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public System.Void InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
}
```


## Fields

- `public System.Single m_GroundPollution`  

```csharp
public System.Single m_GroundPollution;
```

- `public System.Single m_AirPollution`  

```csharp
public System.Single m_AirPollution;
```

- `public System.Single m_NoisePollution`  

```csharp
public System.Single m_NoisePollution;
```


## Constructors

- `public ZonePollution()`  

```csharp
public ZonePollution();
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
		GetBuildingPollutionData(buildingPrefab).AddArchetypeComponents(components);
	}
```

- `private GetBuildingPollutionData(Game.Prefabs.BuildingPrefab buildingPrefab) : Game.Prefabs.PollutionData`  

```csharp
private PollutionData GetBuildingPollutionData(BuildingPrefab buildingPrefab)
	{
		int lotSize = buildingPrefab.lotSize;
		return new PollutionData
		{
			m_GroundPollution = m_GroundPollution * (float)lotSize,
			m_AirPollution = m_AirPollution * (float)lotSize,
			m_NoisePollution = m_NoisePollution * (float)lotSize
		};
	}
```

- `public GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void GetBuildingPrefabComponents(HashSet<ComponentType> components, BuildingPrefab buildingPrefab, byte level)
	{
		components.Add(ComponentType.ReadWrite<PollutionData>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ZonePollutionData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new ZonePollutionData
		{
			m_GroundPollution = m_GroundPollution,
			m_AirPollution = m_AirPollution,
			m_NoisePollution = m_NoisePollution
		});
	}
```

- `public InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void InitializeBuilding(EntityManager entityManager, Entity entity, BuildingPrefab buildingPrefab, byte level)
	{
		if (!buildingPrefab.Has<Pollution>())
		{
			entityManager.SetComponentData(entity, GetBuildingPollutionData(buildingPrefab));
		}
	}
```


