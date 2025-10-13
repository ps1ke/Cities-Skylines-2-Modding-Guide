# Game.Prefabs.ServiceUpgrade

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ServiceUpgrade : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.BuildingPrefab[] m_Buildings;
    public System.UInt32 m_UpgradeCost;
    public System.Int32 m_XPReward;
    public System.Int32 m_MaxPlacementOffset;
    public System.Single m_MaxPlacementDistance;

    public ServiceUpgrade();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.BuildingPrefab[] m_Buildings`  

```csharp
public Game.Prefabs.BuildingPrefab[] m_Buildings;
```

- `public System.UInt32 m_UpgradeCost`  

```csharp
public System.UInt32 m_UpgradeCost;
```

- `public System.Int32 m_XPReward`  

```csharp
public System.Int32 m_XPReward;
```

- `public System.Int32 m_MaxPlacementOffset`  

```csharp
public System.Int32 m_MaxPlacementOffset;
```

- `public System.Single m_MaxPlacementDistance`  

```csharp
public System.Single m_MaxPlacementDistance;
```


## Constructors

- `public ServiceUpgrade()`  

```csharp
public ServiceUpgrade();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.ServiceUpgrade>());
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Buildings != null)
		{
			for (int i = 0; i < m_Buildings.Length; i++)
			{
				prefabs.Add(m_Buildings[i]);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ServiceUpgradeData>());
		components.Add(ComponentType.ReadWrite<ServiceUpgradeBuilding>());
		if (GetComponent<BuildingPrefab>() != null)
		{
			components.Add(ComponentType.ReadWrite<PlaceableObjectData>());
			components.Add(ComponentType.ReadWrite<PlaceableInfoviewItem>());
		}
		if (base.prefab.TryGet<ServiceConsumption>(out var component) && component.m_Upkeep > 0)
		{
			components.Add(ComponentType.ReadWrite<ServiceUpkeepData>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new ServiceUpgradeData
		{
			m_UpgradeCost = m_UpgradeCost,
			m_XPReward = m_XPReward,
			m_MaxPlacementOffset = m_MaxPlacementOffset,
			m_MaxPlacementDistance = m_MaxPlacementDistance
		});
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		if (m_Buildings == null)
		{
			return;
		}
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		for (int i = 0; i < m_Buildings.Length; i++)
		{
			BuildingPrefab buildingPrefab = m_Buildings[i];
			if (!(buildingPrefab == null))
			{
				entityManager.GetBuffer<ServiceUpgradeBuilding>(entity).Add(new ServiceUpgradeBuilding(existingSystemManaged.GetEntity(buildingPrefab)));
				buildingPrefab.AddUpgrade(entityManager, this);
			}
		}
	}
```


