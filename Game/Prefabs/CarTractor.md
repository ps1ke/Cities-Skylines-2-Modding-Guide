# Game.Prefabs.CarTractor

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CarTractor : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.CarTrailerType m_TrailerType;
    public Unity.Mathematics.float3 m_AttachOffset;
    public Game.Prefabs.CarTrailerPrefab m_FixedTrailer;

    public CarTractor();

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

- `public Unity.Mathematics.float3 m_AttachOffset`  

```csharp
public Unity.Mathematics.float3 m_AttachOffset;
```

- `public Game.Prefabs.CarTrailerPrefab m_FixedTrailer`  

```csharp
public Game.Prefabs.CarTrailerPrefab m_FixedTrailer;
```


## Constructors

- `public CarTractor()`  

```csharp
public CarTractor();
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


