# Game.Prefabs.CityBoundaryPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CityBoundaryPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public UnityEngine.Material m_Material;
    public System.Single m_Width;
    public System.Single m_TilingLength;
    public UnityEngine.Color m_CityBorderColor;
    public UnityEngine.Color m_MapBorderColor;

    public CityBoundaryPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public UnityEngine.Material m_Material`  

```csharp
public UnityEngine.Material m_Material;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public System.Single m_TilingLength`  

```csharp
public System.Single m_TilingLength;
```

- `public UnityEngine.Color m_CityBorderColor`  

```csharp
public UnityEngine.Color m_CityBorderColor;
```

- `public UnityEngine.Color m_MapBorderColor`  

```csharp
public UnityEngine.Color m_MapBorderColor;
```


## Constructors

- `public CityBoundaryPrefab()`  

```csharp
public CityBoundaryPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


