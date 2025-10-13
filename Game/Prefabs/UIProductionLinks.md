# Game.Prefabs.UIProductionLinks

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UIProductionLinks : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.UIProductionLinkPrefab m_Producer;
    public Game.Prefabs.UIProductionLinkPrefab[] m_FinalConsumers;

    public UIProductionLinks();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.UIProductionLinkPrefab m_Producer`  

```csharp
public Game.Prefabs.UIProductionLinkPrefab m_Producer;
```

- `public Game.Prefabs.UIProductionLinkPrefab[] m_FinalConsumers`  

```csharp
public Game.Prefabs.UIProductionLinkPrefab[] m_FinalConsumers;
```


## Constructors

- `public UIProductionLinks()`  

```csharp
public UIProductionLinks();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Producer != null)
		{
			prefabs.Add(m_Producer);
		}
		if (m_FinalConsumers == null)
		{
			return;
		}
		for (int i = 0; i < m_FinalConsumers.Length; i++)
		{
			UIProductionLinkPrefab uIProductionLinkPrefab = m_FinalConsumers[i];
			if (uIProductionLinkPrefab != null)
			{
				prefabs.Add(uIProductionLinkPrefab);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<UIProductionLinksData>());
	}
```


