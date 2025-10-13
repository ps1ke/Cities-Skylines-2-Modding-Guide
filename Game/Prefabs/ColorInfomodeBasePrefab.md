# Game.Prefabs.ColorInfomodeBasePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.InfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IColorInfomode`  

## Code

```csharp
public abstract class ColorInfomodeBasePrefab : Game.Prefabs.InfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IColorInfomode
{
    public UnityEngine.Color m_Color;

    public UnityEngine.Color color { get; }

    protected ColorInfomodeBasePrefab();

    public virtual System.Void GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill);
}
```


## Fields

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```


## Properties

- `public UnityEngine.Color color { get }`  

```csharp
public UnityEngine.Color color { get; }
```


## Constructors

- `protected ColorInfomodeBasePrefab()`  

```csharp
protected ColorInfomodeBasePrefab();
```


## Methods

- `public virtual GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill) : System.Void`  

```csharp
public virtual System.Void GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill);
```


