# Game.Prefabs.Climate.WhiteBalanceProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.Climate.OverrideablePropertiesComponent`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WhiteBalanceProperties : Game.Prefabs.Climate.OverrideablePropertiesComponent, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Rendering.ClampedFloatParameter m_Temperature;
    public UnityEngine.Rendering.ClampedFloatParameter m_Tint;

    public WhiteBalanceProperties();

    protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
}
```


## Fields

- `public UnityEngine.Rendering.ClampedFloatParameter m_Temperature`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_Temperature;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_Tint`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_Tint;
```


## Constructors

- `public WhiteBalanceProperties()`  

```csharp
public WhiteBalanceProperties();
```


## Methods

- `protected virtual OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
```


