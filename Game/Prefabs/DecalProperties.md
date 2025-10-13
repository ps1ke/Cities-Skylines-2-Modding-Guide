# Game.Prefabs.DecalProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DecalProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Colossal.Mathematics.Bounds2 m_TextureArea;
    public System.Int32 m_RendererPriority;
    public Game.Rendering.DecalLayers m_LayerMask;
    public System.Boolean m_EnableInfoviewColor;

    public DecalProperties();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Colossal.Mathematics.Bounds2 m_TextureArea`  

```csharp
public Colossal.Mathematics.Bounds2 m_TextureArea;
```

- `public System.Int32 m_RendererPriority`  

```csharp
public System.Int32 m_RendererPriority;
```

- `public Game.Rendering.DecalLayers m_LayerMask`  

```csharp
public Game.Rendering.DecalLayers m_LayerMask;
```

- `public System.Boolean m_EnableInfoviewColor`  

```csharp
public System.Boolean m_EnableInfoviewColor;
```


## Constructors

- `public DecalProperties()`  

```csharp
public DecalProperties();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


