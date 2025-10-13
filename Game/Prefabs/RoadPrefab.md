# Game.Prefabs.RoadPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.NetGeometryPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RoadPrefab : Game.Prefabs.NetGeometryPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.RoadType m_RoadType;
    public System.Single m_SpeedLimit;
    public Game.Prefabs.ZoneBlockPrefab m_ZoneBlock;
    public System.Boolean m_TrafficLights;
    public System.Boolean m_HighwayRules;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public RoadPrefab();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.RoadType m_RoadType`  

```csharp
public Game.Prefabs.RoadType m_RoadType;
```

- `public System.Single m_SpeedLimit`  

```csharp
public System.Single m_SpeedLimit;
```

- `public Game.Prefabs.ZoneBlockPrefab m_ZoneBlock`  

```csharp
public Game.Prefabs.ZoneBlockPrefab m_ZoneBlock;
```

- `public System.Boolean m_TrafficLights`  

```csharp
public System.Boolean m_TrafficLights;
```

- `public System.Boolean m_HighwayRules`  

```csharp
public System.Boolean m_HighwayRules;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public RoadPrefab()`  

```csharp
public RoadPrefab();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		if (components.Contains(ComponentType.ReadWrite<Edge>()))
		{
			components.Add(ComponentType.ReadWrite<Road>());
			components.Add(ComponentType.ReadWrite<UpdateFrame>());
			components.Add(ComponentType.ReadWrite<LandValue>());
			components.Add(ComponentType.ReadWrite<EdgeColor>());
			components.Add(ComponentType.ReadWrite<NetCondition>());
			components.Add(ComponentType.ReadWrite<MaintenanceConsumer>());
			components.Add(ComponentType.ReadWrite<BorderDistrict>());
			if (m_ZoneBlock != null)
			{
				components.Add(ComponentType.ReadWrite<SubBlock>());
				components.Add(ComponentType.ReadWrite<ConnectedBuilding>());
				components.Add(ComponentType.ReadWrite<Game.Net.ServiceCoverage>());
				components.Add(ComponentType.ReadWrite<ResourceAvailability>());
				components.Add(ComponentType.ReadWrite<Density>());
			}
			else if (!m_HighwayRules)
			{
				components.Add(ComponentType.ReadWrite<ConnectedBuilding>());
			}
		}
		else if (components.Contains(ComponentType.ReadWrite<Game.Net.Node>()))
		{
			components.Add(ComponentType.ReadWrite<Road>());
			components.Add(ComponentType.ReadWrite<UpdateFrame>());
			components.Add(ComponentType.ReadWrite<LandValue>());
			components.Add(ComponentType.ReadWrite<NodeColor>());
			components.Add(ComponentType.ReadWrite<NetCondition>());
			components.Add(ComponentType.ReadWrite<Game.Objects.Surface>());
		}
		else if (components.Contains(ComponentType.ReadWrite<NetCompositionData>()))
		{
			components.Add(ComponentType.ReadWrite<RoadComposition>());
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_ZoneBlock != null)
		{
			prefabs.Add(m_ZoneBlock);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<RoadData>());
	}
```


## Nested types

- `Game.Prefabs.RoadPrefab+<get_modTags>d__9`  

