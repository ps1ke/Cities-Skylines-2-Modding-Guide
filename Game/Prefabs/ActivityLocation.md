# Game.Prefabs.ActivityLocation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ActivityLocation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.ActivityLocation+LocationInfo[] m_Locations;
    public Game.Prefabs.NetInvertMode m_InvertWhen;
    public System.String m_AnimatedPropName;
    public System.Boolean m_RequireAuthorization;

    public System.Boolean ignoreUnlockDependencies { get; }

    public ActivityLocation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ActivityLocation+LocationInfo[] m_Locations`  

```csharp
public Game.Prefabs.ActivityLocation+LocationInfo[] m_Locations;
```

- `public Game.Prefabs.NetInvertMode m_InvertWhen`  

```csharp
public Game.Prefabs.NetInvertMode m_InvertWhen;
```

- `public System.String m_AnimatedPropName`  

```csharp
public System.String m_AnimatedPropName;
```

- `public System.Boolean m_RequireAuthorization`  

```csharp
public System.Boolean m_RequireAuthorization;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public ActivityLocation()`  

```csharp
public ActivityLocation();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (!(base.prefab is VehiclePrefab) && !(base.prefab is BuildingPrefab))
		{
			components.Add(ComponentType.ReadWrite<Game.Objects.SpawnLocation>());
			components.Add(ComponentType.ReadWrite<Game.Objects.ActivityLocation>());
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Locations != null)
		{
			for (int i = 0; i < m_Locations.Length; i++)
			{
				prefabs.Add(m_Locations[i].m_Activity);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		if (!(base.prefab is VehiclePrefab) && !(base.prefab is BuildingPrefab))
		{
			components.Add(ComponentType.ReadWrite<SpawnLocationData>());
		}
		components.Add(ComponentType.ReadWrite<ActivityLocationElement>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		SpawnLocationData componentData = default(SpawnLocationData);
		componentData.m_ConnectionType = RouteConnectionType.Pedestrian;
		componentData.m_ActivityMask = default(ActivityMask);
		componentData.m_RoadTypes = RoadTypes.None;
		componentData.m_TrackTypes = TrackTypes.None;
		componentData.m_RequireAuthorization = m_RequireAuthorization;
		componentData.m_HangaroundOnLane = false;
		if (m_Locations != null && m_Locations.Length != 0)
		{
			DynamicBuffer<ActivityLocationElement> buffer = entityManager.GetBuffer<ActivityLocationElement>(entity);
			buffer.ResizeUninitialized(m_Locations.Length);
			PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
			AnimatedPropID propID = entityManager.World.GetExistingSystemManaged<AnimatedSystem>().GetPropID(m_AnimatedPropName);
			for (int i = 0; i < m_Locations.Length; i++)
			{
				LocationInfo locationInfo = m_Locations[i];
				ActivityLocationElement value = new ActivityLocationElement
				{
					m_Prefab = existingSystemManaged.GetEntity(locationInfo.m_Activity),
					m_Position = locationInfo.m_Position,
					m_Rotation = locationInfo.m_Rotation,
					m_PropID = propID
				};
				switch (m_InvertWhen)
				{
				case NetInvertMode.LefthandTraffic:
					value.m_ActivityFlags |= ActivityFlags.InvertLefthandTraffic;
					break;
				case NetInvertMode.RighthandTraffic:
					value.m_ActivityFlags |= ActivityFlags.InvertRighthandTraffic;
					break;
				case NetInvertMode.Always:
					value.m_ActivityFlags |= ActivityFlags.InvertLefthandTraffic | ActivityFlags.InvertRighthandTraffic;
					break;
				}
				ActivityLocationData componentData2 = entityManager.GetComponentData<ActivityLocationData>(value.m_Prefab);
				value.m_ActivityMask = componentData2.m_ActivityMask;
				componentData.m_ActivityMask.m_Mask |= componentData2.m_ActivityMask.m_Mask;
				buffer[i] = value;
			}
		}
		else
		{
			ComponentBase.baseLog.ErrorFormat(base.prefab, "Empty activity location array: {0}", base.prefab.name);
		}
		if (!(base.prefab is VehiclePrefab) && !(base.prefab is BuildingPrefab))
		{
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.ActivityLocation+LocationInfo`  

