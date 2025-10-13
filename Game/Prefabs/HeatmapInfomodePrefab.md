# Game.Prefabs.HeatmapInfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.GradientInfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IGradientInfomode`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class HeatmapInfomodePrefab : Game.Prefabs.GradientInfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IGradientInfomode
{
    public Game.Rendering.HeatmapData m_Type;

    public System.String infomodeTypeLocaleKey { get; }

    public HeatmapInfomodePrefab();

    public virtual System.Boolean CanActivateBoth(Game.Prefabs.InfomodePrefab other);
    public virtual System.Int32 GetColorGroup(System.Int32& secondaryGroup);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    private System.Boolean HasArrowsOnWater();
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Rendering.HeatmapData m_Type`  

```csharp
public Game.Rendering.HeatmapData m_Type;
```


## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

```csharp
public System.String infomodeTypeLocaleKey { get; }
```


## Constructors

- `public HeatmapInfomodePrefab()`  

```csharp
public HeatmapInfomodePrefab();
```


## Methods

- `public virtual CanActivateBoth(Game.Prefabs.InfomodePrefab other) : System.Boolean`  

```csharp
public virtual System.Boolean CanActivateBoth(Game.Prefabs.InfomodePrefab other);
```

- `public virtual GetColorGroup(System.Int32& secondaryGroup) : System.Int32`  

```csharp
public virtual System.Int32 GetColorGroup(System.Int32& secondaryGroup);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `private HasArrowsOnWater() : System.Boolean`  

```csharp
private System.Boolean HasArrowsOnWater();
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


