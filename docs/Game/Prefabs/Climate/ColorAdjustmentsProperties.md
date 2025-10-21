# Game.Prefabs.Climate.ColorAdjustmentsProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.Climate.OverrideablePropertiesComponent`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ColorAdjustmentsProperties : Game.Prefabs.Climate.OverrideablePropertiesComponent, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Rendering.FloatParameter m_PostExposure;
    public UnityEngine.Rendering.ClampedFloatParameter m_Contrast;
    public UnityEngine.Rendering.ColorParameter m_ColorFilter;
    public UnityEngine.Rendering.ClampedFloatParameter m_HueShift;
    public UnityEngine.Rendering.ClampedFloatParameter m_Saturation;

    public ColorAdjustmentsProperties();

    protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
}
```


## Fields

- `public UnityEngine.Rendering.FloatParameter m_PostExposure`  

```csharp
public UnityEngine.Rendering.FloatParameter m_PostExposure;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_Contrast`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_Contrast;
```

- `public UnityEngine.Rendering.ColorParameter m_ColorFilter`  

```csharp
public UnityEngine.Rendering.ColorParameter m_ColorFilter;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_HueShift`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_HueShift;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_Saturation`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_Saturation;
```


## Constructors

- `public ColorAdjustmentsProperties()`  

```csharp
public ColorAdjustmentsProperties();
```


## Methods

- `protected virtual OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
```


