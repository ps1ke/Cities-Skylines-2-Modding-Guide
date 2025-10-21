# Game.Prefabs.AreaTypePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AreaTypePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Areas.AreaType m_Type;
    public UnityEngine.Material m_Material;
    public UnityEngine.Material m_NameMaterial;

    public AreaTypePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Areas.AreaType m_Type`  

```csharp
public Game.Areas.AreaType m_Type;
```

- `public UnityEngine.Material m_Material`  

```csharp
public UnityEngine.Material m_Material;
```

- `public UnityEngine.Material m_NameMaterial`  

```csharp
public UnityEngine.Material m_NameMaterial;
```


## Constructors

- `public AreaTypePrefab()`  

```csharp
public AreaTypePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


