# Game.Prefabs.AuxiliaryNets

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AuxiliaryNets : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_LinkEndOffsets;
    public Game.Prefabs.AuxiliaryNetInfo[] m_AuxiliaryNets;

    public System.Boolean ignoreUnlockDependencies { get; }

    public AuxiliaryNets();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Boolean m_LinkEndOffsets`  

```csharp
public System.Boolean m_LinkEndOffsets;
```

- `public Game.Prefabs.AuxiliaryNetInfo[] m_AuxiliaryNets`  

```csharp
public Game.Prefabs.AuxiliaryNetInfo[] m_AuxiliaryNets;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public AuxiliaryNets()`  

```csharp
public AuxiliaryNets();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Net.SubNet>());
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		for (int i = 0; i < m_AuxiliaryNets.Length; i++)
		{
			prefabs.Add(m_AuxiliaryNets[i].m_Prefab);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PlaceableNetData>());
		components.Add(ComponentType.ReadWrite<AuxiliaryNet>());
	}
```


