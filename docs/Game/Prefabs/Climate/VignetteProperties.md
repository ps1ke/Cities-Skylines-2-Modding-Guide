# Game.Prefabs.Climate.VignetteProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.Climate.OverrideablePropertiesComponent`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class VignetteProperties : Game.Prefabs.Climate.OverrideablePropertiesComponent, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Rendering.ColorParameter m_Color;
    public UnityEngine.Rendering.Vector2Parameter m_Center;
    public UnityEngine.Rendering.ClampedFloatParameter m_Intensity;
    public UnityEngine.Rendering.ClampedFloatParameter m_Smoothness;
    public UnityEngine.Rendering.ClampedFloatParameter m_Roundness;
    public UnityEngine.Rendering.BoolParameter m_Rounded;

    public VignetteProperties();

    protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
}
```


## Fields

- `public UnityEngine.Rendering.ColorParameter m_Color`  

```csharp
public UnityEngine.Rendering.ColorParameter m_Color;
```

- `public UnityEngine.Rendering.Vector2Parameter m_Center`  

```csharp
public UnityEngine.Rendering.Vector2Parameter m_Center;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_Intensity`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_Intensity;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_Smoothness`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_Smoothness;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_Roundness`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_Roundness;
```

- `public UnityEngine.Rendering.BoolParameter m_Rounded`  

```csharp
public UnityEngine.Rendering.BoolParameter m_Rounded;
```


## Constructors

- `public VignetteProperties()`  

```csharp
public VignetteProperties();
```


## Methods

- `protected virtual OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
```


