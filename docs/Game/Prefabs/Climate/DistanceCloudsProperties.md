# Game.Prefabs.Climate.DistanceCloudsProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.Climate.OverrideablePropertiesComponent`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DistanceCloudsProperties : Game.Prefabs.Climate.OverrideablePropertiesComponent, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Rendering.ClampedFloatParameter m_Opacity;
    public UnityEngine.Rendering.ClampedFloatParameter m_CumulusStrength;
    public UnityEngine.Rendering.ClampedFloatParameter m_StratusStrength;
    public UnityEngine.Rendering.ClampedFloatParameter m_CirrusStrength;
    public UnityEngine.Rendering.ClampedFloatParameter m_WispyStrength;
    public UnityEngine.Rendering.MinFloatParameter m_Altitude;

    public DistanceCloudsProperties();

    protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
}
```


## Fields

- `public UnityEngine.Rendering.ClampedFloatParameter m_Opacity`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_Opacity;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_CumulusStrength`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_CumulusStrength;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_StratusStrength`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_StratusStrength;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_CirrusStrength`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_CirrusStrength;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_WispyStrength`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_WispyStrength;
```

- `public UnityEngine.Rendering.MinFloatParameter m_Altitude`  

```csharp
public UnityEngine.Rendering.MinFloatParameter m_Altitude;
```


## Constructors

- `public DistanceCloudsProperties()`  

```csharp
public DistanceCloudsProperties();
```


## Methods

- `protected virtual OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
```


