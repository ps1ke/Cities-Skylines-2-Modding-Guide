# Game.Prefabs.EditorContainer

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EditorContainer : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public EditorContainer();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Constructors

- `public EditorContainer()`  

```csharp
public EditorContainer();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (components.Contains(ComponentType.ReadWrite<Edge>()))
		{
			components.Add(ComponentType.ReadWrite<Game.Tools.EditorContainer>());
			components.Add(ComponentType.ReadWrite<Game.Net.SubLane>());
			components.Add(ComponentType.ReadWrite<Curve>());
			components.Add(ComponentType.ReadWrite<CullingInfo>());
			components.Add(ComponentType.ReadWrite<PseudoRandomSeed>());
		}
		else if (components.Contains(ComponentType.ReadWrite<Node>()))
		{
			components.Add(ComponentType.ReadWrite<Game.Tools.EditorContainer>());
			components.Add(ComponentType.ReadWrite<CullingInfo>());
		}
		else if (components.Contains(ComponentType.ReadWrite<Game.Objects.Object>()))
		{
			components.Add(ComponentType.ReadWrite<Game.Tools.EditorContainer>());
			components.Add(ComponentType.ReadWrite<Game.Objects.SubObject>());
			components.Add(ComponentType.ReadWrite<Static>());
			components.Add(ComponentType.ReadWrite<CullingInfo>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<EditorContainerData>());
	}
```


