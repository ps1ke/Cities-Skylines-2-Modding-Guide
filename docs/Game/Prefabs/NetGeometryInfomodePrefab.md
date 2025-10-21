# Game.Prefabs.NetGeometryInfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ColorInfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IColorInfomode`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetGeometryInfomodePrefab : Game.Prefabs.ColorInfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IColorInfomode
{
    public Game.Prefabs.NetType m_Type;

    public System.String infomodeTypeLocaleKey { get; }

    public NetGeometryInfomodePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NetType m_Type`  

```csharp
public Game.Prefabs.NetType m_Type;
```


## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

```csharp
public System.String infomodeTypeLocaleKey { get; }
```


## Constructors

- `public NetGeometryInfomodePrefab()`  

```csharp
public NetGeometryInfomodePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


