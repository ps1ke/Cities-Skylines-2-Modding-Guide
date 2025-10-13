# Game.Prefabs.ObjectSubLanes

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ObjectSubLanes : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.ObjectSubLaneInfo[] m_SubLanes;

    public System.Boolean ignoreUnlockDependencies { get; }

    public ObjectSubLanes();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.ObjectSubLaneInfo[] m_SubLanes`  

```csharp
public Game.Prefabs.ObjectSubLaneInfo[] m_SubLanes;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public ObjectSubLanes()`  

```csharp
public ObjectSubLanes();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		bool flag = false;
		if (m_SubLanes != null)
		{
			for (int i = 0; i < m_SubLanes.Length; i++)
			{
				ObjectSubLaneInfo objectSubLaneInfo = m_SubLanes[i];
				if (objectSubLaneInfo.m_NodeIndex.x != objectSubLaneInfo.m_NodeIndex.y)
				{
					flag = true;
					break;
				}
			}
		}
		if (flag)
		{
			components.Add(ComponentType.ReadWrite<Game.Net.SubLane>());
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_SubLanes != null)
		{
			for (int i = 0; i < m_SubLanes.Length; i++)
			{
				prefabs.Add(m_SubLanes[i].m_LanePrefab);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<SubLane>());
	}
```


