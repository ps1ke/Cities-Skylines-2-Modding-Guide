# Game.Prefabs.OverlayConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class OverlayConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public UnityEngine.Material m_CurveMaterial;
    public UnityEngine.Material m_ObjectBrushMaterial;
    public Game.Prefabs.FontInfo[] m_FontInfos;

    public OverlayConfigurationPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public UnityEngine.Material m_CurveMaterial`  

```csharp
public UnityEngine.Material m_CurveMaterial;
```

- `public UnityEngine.Material m_ObjectBrushMaterial`  

```csharp
public UnityEngine.Material m_ObjectBrushMaterial;
```

- `public Game.Prefabs.FontInfo[] m_FontInfos`  

```csharp
public Game.Prefabs.FontInfo[] m_FontInfos;
```


## Constructors

- `public OverlayConfigurationPrefab()`  

```csharp
public OverlayConfigurationPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


