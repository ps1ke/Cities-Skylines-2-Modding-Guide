# Game.Prefabs.Climate.VolumetricCloudsProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.Climate.OverrideablePropertiesComponent`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class VolumetricCloudsProperties : Game.Prefabs.Climate.OverrideablePropertiesComponent, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Rendering.MinFloatParameter m_BottomAltitude;
    public UnityEngine.Rendering.MinFloatParameter m_AltitudeRange;
    public UnityEngine.Rendering.ClampedFloatParameter m_DensityMultiplier;
    public UnityEngine.Rendering.AnimationCurveParameter m_DensityCurve;
    public UnityEngine.Rendering.ClampedFloatParameter m_ShapeFactor;
    public UnityEngine.Rendering.Vector3Parameter m_ShapeOffset;
    public UnityEngine.Rendering.ClampedFloatParameter m_ErosionFactor;
    public UnityEngine.Rendering.ClampedFloatParameter m_ErosionOcclusion;
    public UnityEngine.Rendering.AnimationCurveParameter m_ErosionCurve;
    public UnityEngine.Rendering.AnimationCurveParameter m_AmbientOcclusionCurve;
    public UnityEngine.Rendering.ClampedFloatParameter m_MultiScattering;

    public VolumetricCloudsProperties();

    protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
}
```


## Fields

- `public UnityEngine.Rendering.MinFloatParameter m_BottomAltitude`  

```csharp
public UnityEngine.Rendering.MinFloatParameter m_BottomAltitude;
```

- `public UnityEngine.Rendering.MinFloatParameter m_AltitudeRange`  

```csharp
public UnityEngine.Rendering.MinFloatParameter m_AltitudeRange;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_DensityMultiplier`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_DensityMultiplier;
```

- `public UnityEngine.Rendering.AnimationCurveParameter m_DensityCurve`  

```csharp
public UnityEngine.Rendering.AnimationCurveParameter m_DensityCurve;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_ShapeFactor`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_ShapeFactor;
```

- `public UnityEngine.Rendering.Vector3Parameter m_ShapeOffset`  

```csharp
public UnityEngine.Rendering.Vector3Parameter m_ShapeOffset;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_ErosionFactor`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_ErosionFactor;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_ErosionOcclusion`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_ErosionOcclusion;
```

- `public UnityEngine.Rendering.AnimationCurveParameter m_ErosionCurve`  

```csharp
public UnityEngine.Rendering.AnimationCurveParameter m_ErosionCurve;
```

- `public UnityEngine.Rendering.AnimationCurveParameter m_AmbientOcclusionCurve`  

```csharp
public UnityEngine.Rendering.AnimationCurveParameter m_AmbientOcclusionCurve;
```

- `public UnityEngine.Rendering.ClampedFloatParameter m_MultiScattering`  

```csharp
public UnityEngine.Rendering.ClampedFloatParameter m_MultiScattering;
```


## Constructors

- `public VolumetricCloudsProperties()`  

```csharp
public VolumetricCloudsProperties();
```


## Methods

- `protected virtual OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
protected override void OnBindVolumeProperties(Volume volume)
	{
		VolumetricClouds component = null;
		VolumeHelper.GetOrCreateVolumeComponent(volume, ref component);
		m_BottomAltitude = component.bottomAltitude;
		m_AltitudeRange = component.altitudeRange;
		m_DensityMultiplier = component.densityMultiplier;
		m_DensityCurve = component.densityCurve;
		m_ShapeFactor = component.shapeFactor;
		m_ShapeOffset = component.shapeOffset;
		m_ErosionFactor = component.erosionFactor;
		m_ErosionOcclusion = component.erosionOcclusion;
		m_ErosionCurve = component.erosionCurve;
		m_AmbientOcclusionCurve = component.ambientOcclusionCurve;
		m_MultiScattering = component.multiScattering;
		component.m_CloudPreset.Override(VolumetricClouds.CloudPresets.Custom);
	}
```


