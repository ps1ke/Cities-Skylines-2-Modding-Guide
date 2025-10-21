# Game.Prefabs.CarTrailerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.CarBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CarTrailerPrefab : Game.Prefabs.CarBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.CarTrailerType m_TrailerType;
    public Game.Prefabs.TrailerMovementType m_MovementType;
    public Unity.Mathematics.float3 m_AttachOffset;
    public Game.Prefabs.CarBasePrefab m_FixedTractor;

    public CarTrailerPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.CarTrailerType m_TrailerType`  

```csharp
public Game.Prefabs.CarTrailerType m_TrailerType;
```

- `public Game.Prefabs.TrailerMovementType m_MovementType`  

```csharp
public Game.Prefabs.TrailerMovementType m_MovementType;
```

- `public Unity.Mathematics.float3 m_AttachOffset`  

```csharp
public Unity.Mathematics.float3 m_AttachOffset;
```

- `public Game.Prefabs.CarBasePrefab m_FixedTractor`  

```csharp
public Game.Prefabs.CarBasePrefab m_FixedTractor;
```


## Constructors

- `public CarTrailerPrefab()`  

```csharp
public CarTrailerPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


