# Game.Prefabs.InfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class InfomodePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_Priority;

    public System.String infomodeTypeLocaleKey { get; }

    protected InfomodePrefab();

    public virtual System.Boolean CanActivateBoth(Game.Prefabs.InfomodePrefab other);
    public virtual System.Int32 GetColorGroup(System.Int32& secondaryGroup);
    public virtual System.Void GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```


## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

```csharp
public System.String infomodeTypeLocaleKey { get; }
```


## Constructors

- `protected InfomodePrefab()`  

```csharp
protected InfomodePrefab();
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

- `public virtual GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill) : System.Void`  

```csharp
public virtual System.Void GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


