# Game.Prefabs.Climate.ShadowsMidtonesHighlightsProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class public  

**Base:** `Game.Prefabs.Climate.OverrideablePropertiesComponent`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ShadowsMidtonesHighlightsProperties : Game.Prefabs.Climate.OverrideablePropertiesComponent, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Rendering.Vector4Parameter m_Shadows;
    public UnityEngine.Rendering.Vector4Parameter m_Midtones;
    public UnityEngine.Rendering.Vector4Parameter m_Highlights;
    public UnityEngine.Rendering.MinFloatParameter m_ShadowsStart;
    public UnityEngine.Rendering.MinFloatParameter m_ShadowsEnd;
    public UnityEngine.Rendering.MinFloatParameter m_HighlightsStart;
    public UnityEngine.Rendering.MinFloatParameter m_HighlightsEnd;

    public ShadowsMidtonesHighlightsProperties();

    protected virtual System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
}
```


## Fields

- `public UnityEngine.Rendering.Vector4Parameter m_Shadows`  

```csharp
public UnityEngine.Rendering.Vector4Parameter m_Shadows;
```

- `public UnityEngine.Rendering.Vector4Parameter m_Midtones`  

```csharp
public UnityEngine.Rendering.Vector4Parameter m_Midtones;
```

- `public UnityEngine.Rendering.Vector4Parameter m_Highlights`  

```csharp
public UnityEngine.Rendering.Vector4Parameter m_Highlights;
```

- `public UnityEngine.Rendering.MinFloatParameter m_ShadowsStart`  

```csharp
public UnityEngine.Rendering.MinFloatParameter m_ShadowsStart;
```

- `public UnityEngine.Rendering.MinFloatParameter m_ShadowsEnd`  

```csharp
public UnityEngine.Rendering.MinFloatParameter m_ShadowsEnd;
```

- `public UnityEngine.Rendering.MinFloatParameter m_HighlightsStart`  

```csharp
public UnityEngine.Rendering.MinFloatParameter m_HighlightsStart;
```

- `public UnityEngine.Rendering.MinFloatParameter m_HighlightsEnd`  

```csharp
public UnityEngine.Rendering.MinFloatParameter m_HighlightsEnd;
```


## Constructors

- `public ShadowsMidtonesHighlightsProperties()`  

```csharp
public ShadowsMidtonesHighlightsProperties();
```


## Methods

- `protected virtual OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
protected override void OnBindVolumeProperties(Volume volume)
	{
		ShadowsMidtonesHighlights component = null;
		VolumeHelper.GetOrCreateVolumeComponent(volume, ref component);
		m_Shadows = component.shadows;
		m_Midtones = component.midtones;
		m_Highlights = component.highlights;
		m_ShadowsStart = component.shadowsStart;
		m_ShadowsEnd = component.shadowsEnd;
		m_HighlightsStart = component.highlightsStart;
		m_HighlightsEnd = component.highlightsEnd;
	}
```


