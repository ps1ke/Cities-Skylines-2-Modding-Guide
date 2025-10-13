# Game.Prefabs.RenderedArea

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RenderedArea : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Material m_Material;
    public System.Single m_Roundness;
    public System.Single m_LodBias;
    public System.Int32 m_RendererPriority;
    public Game.Rendering.DecalLayers m_DecalLayerMask;

    public RenderedArea();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public UnityEngine.Material m_Material`  

```csharp
public UnityEngine.Material m_Material;
```

- `public System.Single m_Roundness`  

```csharp
public System.Single m_Roundness;
```

- `public System.Single m_LodBias`  

```csharp
public System.Single m_LodBias;
```

- `public System.Int32 m_RendererPriority`  

```csharp
public System.Int32 m_RendererPriority;
```

- `public Game.Rendering.DecalLayers m_DecalLayerMask`  

```csharp
public Game.Rendering.DecalLayers m_DecalLayerMask;
```


## Constructors

- `public RenderedArea()`  

```csharp
public RenderedArea();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Batch>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<RenderedAreaData>());
	}
```


