# Game.Prefabs.PlaceableNet

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PlaceableNet : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Colossal.Mathematics.Bounds1 m_ElevationRange;
    public System.Boolean m_AllowParallelMode;
    public Game.Prefabs.NetPrefab m_UndergroundPrefab;
    public System.Int32 m_XPReward;

    public PlaceableNet();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_ElevationRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_ElevationRange;
```

- `public System.Boolean m_AllowParallelMode`  

```csharp
public System.Boolean m_AllowParallelMode;
```

- `public Game.Prefabs.NetPrefab m_UndergroundPrefab`  

```csharp
public Game.Prefabs.NetPrefab m_UndergroundPrefab;
```

- `public System.Int32 m_XPReward`  

```csharp
public System.Int32 m_XPReward;
```


## Constructors

- `public PlaceableNet()`  

```csharp
public PlaceableNet();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (components.Contains(ComponentType.ReadWrite<NetCompositionData>()))
		{
			components.Add(ComponentType.ReadWrite<PlaceableNetComposition>());
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_UndergroundPrefab != null)
		{
			prefabs.Add(m_UndergroundPrefab);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PlaceableNetData>());
		components.Add(ComponentType.ReadWrite<PlaceableInfoviewItem>());
	}
```


