# Game.Prefabs.NetStatusInfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.GradientInfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IGradientInfomode`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetStatusInfomodePrefab : Game.Prefabs.GradientInfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IGradientInfomode
{
    public Game.Prefabs.NetStatusType m_Type;
    public Colossal.Mathematics.Bounds1 m_Range;
    public System.Single m_FlowSpeed;
    public System.Single m_FlowTiling;
    public System.Single m_MinFlow;

    public System.String infomodeTypeLocaleKey { get; }

    public NetStatusInfomodePrefab();

    public virtual System.Boolean CanActivateBoth(Game.Prefabs.InfomodePrefab other);
    public virtual System.Void GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    private System.Boolean VisibleOnRoadSurface();
}
```


## Fields

- `public Game.Prefabs.NetStatusType m_Type`  

```csharp
public Game.Prefabs.NetStatusType m_Type;
```

- `public Colossal.Mathematics.Bounds1 m_Range`  

```csharp
public Colossal.Mathematics.Bounds1 m_Range;
```

- `public System.Single m_FlowSpeed`  

```csharp
public System.Single m_FlowSpeed;
```

- `public System.Single m_FlowTiling`  

```csharp
public System.Single m_FlowTiling;
```

- `public System.Single m_MinFlow`  

```csharp
public System.Single m_MinFlow;
```


## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

```csharp
public System.String infomodeTypeLocaleKey { get; }
```


## Constructors

- `public NetStatusInfomodePrefab()`  

```csharp
public NetStatusInfomodePrefab();
```


## Methods

- `public virtual CanActivateBoth(Game.Prefabs.InfomodePrefab other) : System.Boolean`  

```csharp
public virtual System.Boolean CanActivateBoth(Game.Prefabs.InfomodePrefab other);
```

- `public virtual GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill) : System.Void`  

```csharp
public virtual System.Void GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `private VisibleOnRoadSurface() : System.Boolean`  

```csharp
private System.Boolean VisibleOnRoadSurface();
```


