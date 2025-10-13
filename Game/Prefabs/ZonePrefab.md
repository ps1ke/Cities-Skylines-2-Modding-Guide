# Game.Prefabs.ZonePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZonePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Zones.AreaType m_AreaType;
    public UnityEngine.Color m_Color;
    public UnityEngine.Color m_Edge;
    public System.Boolean m_Office;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public ZonePrefab();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public System.Void GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
    public System.Void GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level);
}
```


## Fields

- `public Game.Zones.AreaType m_AreaType`  

```csharp
public Game.Zones.AreaType m_AreaType;
```

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public UnityEngine.Color m_Edge`  

```csharp
public UnityEngine.Color m_Edge;
```

- `public System.Boolean m_Office`  

```csharp
public System.Boolean m_Office;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public ZonePrefab()`  

```csharp
public ZonePrefab();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

- `public GetBuildingArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void GetBuildingArchetypeComponents(HashSet<ComponentType> components, BuildingPrefab buildingPrefab, byte level)
	{
		List<IZoneBuildingComponent> list = new List<IZoneBuildingComponent>();
		if (!base.prefab.TryGet(list))
		{
			return;
		}
		foreach (IZoneBuildingComponent item in list)
		{
			item.GetBuildingArchetypeComponents(components, buildingPrefab, level);
		}
	}
```

- `public GetBuildingPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void GetBuildingPrefabComponents(HashSet<ComponentType> components, BuildingPrefab buildingPrefab, byte level)
	{
		if (m_Office)
		{
			components.Add(ComponentType.ReadWrite<OfficeBuilding>());
		}
		List<IZoneBuildingComponent> list = new List<IZoneBuildingComponent>();
		if (!base.prefab.TryGet(list))
		{
			return;
		}
		foreach (IZoneBuildingComponent item in list)
		{
			item.GetBuildingPrefabComponents(components, buildingPrefab, level);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ZoneData>());
		components.Add(ComponentType.ReadWrite<PlaceableInfoviewItem>());
		components.Add(ComponentType.ReadWrite<ProcessEstimate>());
	}
```

- `public InitializeBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.BuildingPrefab buildingPrefab, System.Byte level) : System.Void`  

```csharp
public void InitializeBuilding(EntityManager entityManager, Entity entity, BuildingPrefab buildingPrefab, byte level)
	{
		List<IZoneBuildingComponent> list = new List<IZoneBuildingComponent>();
		if (!base.prefab.TryGet(list))
		{
			return;
		}
		foreach (IZoneBuildingComponent item in list)
		{
			item.InitializeBuilding(entityManager, entity, buildingPrefab, level);
		}
	}
```


## Nested types

- `Game.Prefabs.ZonePrefab+<get_modTags>d__9`  

