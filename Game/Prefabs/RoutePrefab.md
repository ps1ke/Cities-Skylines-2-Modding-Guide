# Game.Prefabs.RoutePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IColored`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RoutePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IColored
{
    public UnityEngine.Material m_Material;
    public System.Single m_Width;
    public System.Single m_SegmentLength;
    public UnityEngine.Color m_Color;
    public System.String m_LocaleID;

    public UnityEngine.Color32 color { get; }

    public RoutePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
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

- `public System.Single m_SegmentLength`  

```csharp
public System.Single m_SegmentLength;
```

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public System.String m_LocaleID`  

```csharp
public System.String m_LocaleID;
```


## Properties

- `public UnityEngine.Color32 color { get }`  

```csharp
public UnityEngine.Color32 color { get; }
```


## Constructors

- `public RoutePrefab()`  

```csharp
public RoutePrefab();
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

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


