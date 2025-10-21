# Game.Prefabs.AssetStampPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ObjectPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AssetStampPrefab : Game.Prefabs.ObjectPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_Width;
    public System.Int32 m_Depth;
    public System.UInt32 m_ConstructionCost;
    public System.UInt32 m_UpKeepCost;

    public System.Boolean canIgnoreUnlockDependencies { get; }

    public AssetStampPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Int32 m_Width`  

```csharp
public System.Int32 m_Width;
```

- `public System.Int32 m_Depth`  

```csharp
public System.Int32 m_Depth;
```

- `public System.UInt32 m_ConstructionCost`  

```csharp
public System.UInt32 m_ConstructionCost;
```

- `public System.UInt32 m_UpKeepCost`  

```csharp
public System.UInt32 m_UpKeepCost;
```


## Properties

- `public System.Boolean canIgnoreUnlockDependencies { get }`  

```csharp
public System.Boolean canIgnoreUnlockDependencies { get; }
```


## Constructors

- `public AssetStampPrefab()`  

```csharp
public AssetStampPrefab();
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


