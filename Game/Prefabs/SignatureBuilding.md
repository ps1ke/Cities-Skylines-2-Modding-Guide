# Game.Prefabs.SignatureBuilding

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SignatureBuilding : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.ZonePrefab m_ZoneType;
    public System.Int32 m_XPReward;
    public System.String m_UnlockEventImage;
    public static const System.Int32 kStatLevel;

    public SignatureBuilding();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ZonePrefab m_ZoneType`  

```csharp
public Game.Prefabs.ZonePrefab m_ZoneType;
```

- `public System.Int32 m_XPReward`  

```csharp
public System.Int32 m_XPReward;
```

- `public System.String m_UnlockEventImage`  

```csharp
public System.String m_UnlockEventImage;
```

- `public static const System.Int32 kStatLevel`  

```csharp
public static const System.Int32 kStatLevel;
```


## Constructors

- `public SignatureBuilding()`  

```csharp
public SignatureBuilding();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<BuildingCondition>());
		components.Add(ComponentType.ReadWrite<Signature>());
		components.Add(ComponentType.ReadWrite<Game.Objects.UniqueObject>());
		if (m_ZoneType != null)
		{
			m_ZoneType.GetBuildingArchetypeComponents(components, (BuildingPrefab)base.prefab, 5);
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_ZoneType);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<SignatureBuildingData>());
		components.Add(ComponentType.ReadWrite<SpawnableBuildingData>());
		components.Add(ComponentType.ReadWrite<PlaceableObjectData>());
		components.Add(ComponentType.ReadWrite<PlaceableInfoviewItem>());
		if (m_ZoneType != null)
		{
			m_ZoneType.GetBuildingPrefabComponents(components, (BuildingPrefab)base.prefab, 5);
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		PlaceableObjectData componentData = entityManager.GetComponentData<PlaceableObjectData>(entity);
		componentData.m_XPReward = m_XPReward;
		if ((componentData.m_Flags & (PlacementFlags.Shoreline | PlacementFlags.Floating | PlacementFlags.Hovering)) == 0)
		{
			componentData.m_Flags |= PlacementFlags.OnGround;
		}
		componentData.m_Flags |= PlacementFlags.Unique;
		entityManager.SetComponentData(entity, componentData);
		if (m_ZoneType != null)
		{
			m_ZoneType.InitializeBuilding(entityManager, entity, (BuildingPrefab)base.prefab, 5);
		}
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		SpawnableBuildingData componentData = new SpawnableBuildingData
		{
			m_Level = 5
		};
		if (m_ZoneType != null)
		{
			componentData.m_ZonePrefab = existingSystemManaged.GetEntity(m_ZoneType);
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


