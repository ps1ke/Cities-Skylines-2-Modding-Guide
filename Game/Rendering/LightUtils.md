# Game.Rendering.LightUtils

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class LightUtils
{
    private static System.Single s_LuminanceToEvFactor { private get; }
    private static System.Single s_EvToLuminanceFactor { private get; }

    public static System.Void CalculateAnglesForPyramid(System.Single aspectRatio, System.Single spotAngle, System.Single& angleA, System.Single& angleB);
    public static System.Single CalculateLineLightLumenToLuminance(System.Single intensity, System.Single lineWidth);
    public static System.Single CalculateLineLightLuminanceToLumen(System.Single intensity, System.Single lineWidth);
    public static System.Single ConvertAreaLightEvToLumen(Game.Rendering.AreaLightShape AreaLightShape, System.Single ev, System.Single width, System.Single height);
    public static System.Single ConvertAreaLightLumenToEv(Game.Rendering.AreaLightShape AreaLightShape, System.Single lumen, System.Single width, System.Single height);
    public static System.Single ConvertAreaLightLumenToLuminance(Game.Rendering.AreaLightShape areaLightShape, System.Single lumen, System.Single width, System.Single height);
    public static System.Single ConvertAreaLightLuminanceToLumen(Game.Rendering.AreaLightShape areaLightShape, System.Single luminance, System.Single width, System.Single height);
    public static System.Single ConvertCandelaToEv(System.Single candela);
    public static System.Single ConvertCandelaToLux(System.Single candela, System.Single distance);
    public static System.Single ConvertEvToCandela(System.Single ev);
    public static System.Single ConvertEvToLuminance(System.Single ev);
    public static System.Single ConvertEvToLux(System.Single ev, System.Single distance);
    public static System.Single ConvertFrustrumLightCandelaToLumen(System.Single intensity, System.Single angleA, System.Single angleB);
    public static System.Single ConvertFrustrumLightLumenToCandela(System.Single intensity, System.Single angleA, System.Single angleB);
    public static System.Single ConvertLightIntensity(Game.Rendering.LightUnit oldLightUnit, Game.Rendering.LightUnit newLightUnit, Game.Prefabs.Effects.LightEffect editor, System.Single intensity);
    public static System.Single ConvertLuminanceToEv(System.Single luminance);
    public static System.Single ConvertLuxToCandela(System.Single lux, System.Single distance);
    public static System.Single ConvertLuxToEv(System.Single lux, System.Single distance);
    public static System.Single ConvertPointLightCandelaToLumen(System.Single intensity);
    public static System.Single ConvertPointLightLumenToCandela(System.Single intensity);
    public static System.Single ConvertPunctualLightCandelaToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single candela, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio);
    public static System.Single ConvertPunctualLightEvToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single ev, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio);
    public static System.Single ConvertPunctualLightLumenToCandela(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector);
    public static System.Single ConvertPunctualLightLumenToEv(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector);
    public static System.Single ConvertPunctualLightLumenToLux(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector, System.Single distance);
    public static System.Single ConvertPunctualLightLuxToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single lux, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio, System.Single distance);
    public static System.Single ConvertRectLightLumenToLuminance(System.Single intensity, System.Single width, System.Single height);
    public static System.Single ConvertRectLightLuminanceToLumen(System.Single intensity, System.Single width, System.Single height);
    public static System.Single ConvertSpotLightCandelaToLumen(System.Single intensity, System.Single angle, System.Boolean exact);
    public static System.Single ConvertSpotLightLumenToCandela(System.Single intensity, System.Single angle, System.Boolean exact);
}
```


## Properties

- `private static System.Single s_LuminanceToEvFactor { private get }`  

```csharp
private static System.Single s_LuminanceToEvFactor { private get; }
```

- `private static System.Single s_EvToLuminanceFactor { private get }`  

```csharp
private static System.Single s_EvToLuminanceFactor { private get; }
```


## Methods

- `public static CalculateAnglesForPyramid(System.Single aspectRatio, System.Single spotAngle, System.Single& angleA, System.Single& angleB) : System.Void`  

```csharp
public static void CalculateAnglesForPyramid(float aspectRatio, float spotAngle, out float angleA, out float angleB)
	{
		if (aspectRatio < 1f)
		{
			aspectRatio = 1f / aspectRatio;
		}
		angleA = spotAngle;
		float f = angleA * 0.5f;
		f = Mathf.Atan(Mathf.Tan(f) * aspectRatio);
		angleB = f * 2f;
	}
```

- `public static CalculateLineLightLumenToLuminance(System.Single intensity, System.Single lineWidth) : System.Single`  

```csharp
public static float CalculateLineLightLumenToLuminance(float intensity, float lineWidth)
	{
		return intensity / (MathF.PI * 4f * lineWidth);
	}
```

- `public static CalculateLineLightLuminanceToLumen(System.Single intensity, System.Single lineWidth) : System.Single`  

```csharp
public static float CalculateLineLightLuminanceToLumen(float intensity, float lineWidth)
	{
		return intensity * (MathF.PI * 4f * lineWidth);
	}
```

- `public static ConvertAreaLightEvToLumen(Game.Rendering.AreaLightShape AreaLightShape, System.Single ev, System.Single width, System.Single height) : System.Single`  

```csharp
public static float ConvertAreaLightEvToLumen(AreaLightShape AreaLightShape, float ev, float width, float height)
	{
		float luminance = ConvertEvToLuminance(ev);
		return ConvertAreaLightLuminanceToLumen(AreaLightShape, luminance, width, height);
	}
```

- `public static ConvertAreaLightLumenToEv(Game.Rendering.AreaLightShape AreaLightShape, System.Single lumen, System.Single width, System.Single height) : System.Single`  

```csharp
public static float ConvertAreaLightLumenToEv(AreaLightShape AreaLightShape, float lumen, float width, float height)
	{
		return ConvertLuminanceToEv(ConvertAreaLightLumenToLuminance(AreaLightShape, lumen, width, height));
	}
```

- `public static ConvertAreaLightLumenToLuminance(Game.Rendering.AreaLightShape areaLightShape, System.Single lumen, System.Single width, System.Single height = 0) : System.Single`  

```csharp
public static float ConvertAreaLightLumenToLuminance(AreaLightShape areaLightShape, float lumen, float width, float height = 0f)
	{
		return areaLightShape switch
		{
			AreaLightShape.Tube => CalculateLineLightLumenToLuminance(lumen, width), 
			AreaLightShape.Rectangle => ConvertRectLightLumenToLuminance(lumen, width, height), 
			_ => lumen, 
		};
	}
```

- `public static ConvertAreaLightLuminanceToLumen(Game.Rendering.AreaLightShape areaLightShape, System.Single luminance, System.Single width, System.Single height = 0) : System.Single`  

```csharp
public static float ConvertAreaLightLuminanceToLumen(AreaLightShape areaLightShape, float luminance, float width, float height = 0f)
	{
		return areaLightShape switch
		{
			AreaLightShape.Tube => CalculateLineLightLuminanceToLumen(luminance, width), 
			AreaLightShape.Rectangle => ConvertRectLightLuminanceToLumen(luminance, width, height), 
			_ => luminance, 
		};
	}
```

- `public static ConvertCandelaToEv(System.Single candela) : System.Single`  

```csharp
public static float ConvertCandelaToEv(float candela)
	{
		return ConvertLuminanceToEv(candela);
	}
```

- `public static ConvertCandelaToLux(System.Single candela, System.Single distance) : System.Single`  

```csharp
public static float ConvertCandelaToLux(float candela, float distance)
	{
		return candela / (distance * distance);
	}
```

- `public static ConvertEvToCandela(System.Single ev) : System.Single`  

```csharp
public static float ConvertEvToCandela(float ev)
	{
		return ConvertEvToLuminance(ev);
	}
```

- `public static ConvertEvToLuminance(System.Single ev) : System.Single`  

```csharp
public static float ConvertEvToLuminance(float ev)
	{
		return Mathf.Pow(2f, ev + s_EvToLuminanceFactor);
	}
```

- `public static ConvertEvToLux(System.Single ev, System.Single distance) : System.Single`  

```csharp
public static float ConvertEvToLux(float ev, float distance)
	{
		return ConvertCandelaToLux(ConvertEvToLuminance(ev), distance);
	}
```

- `public static ConvertFrustrumLightCandelaToLumen(System.Single intensity, System.Single angleA, System.Single angleB) : System.Single`  

```csharp
public static float ConvertFrustrumLightCandelaToLumen(float intensity, float angleA, float angleB)
	{
		return intensity * (4f * Mathf.Asin(Mathf.Sin(angleA / 2f) * Mathf.Sin(angleB / 2f)));
	}
```

- `public static ConvertFrustrumLightLumenToCandela(System.Single intensity, System.Single angleA, System.Single angleB) : System.Single`  

```csharp
public static float ConvertFrustrumLightLumenToCandela(float intensity, float angleA, float angleB)
	{
		return intensity / (4f * Mathf.Asin(Mathf.Sin(angleA / 2f) * Mathf.Sin(angleB / 2f)));
	}
```

- `public static ConvertLightIntensity(Game.Rendering.LightUnit oldLightUnit, Game.Rendering.LightUnit newLightUnit, Game.Prefabs.Effects.LightEffect editor, System.Single intensity) : System.Single`  

```csharp
public static float ConvertLightIntensity(LightUnit oldLightUnit, LightUnit newLightUnit, LightEffect editor, float intensity)
	{
		LightType type = editor.m_Type;
		switch (type)
		{
		case LightType.Spot:
		case LightType.Point:
			if (oldLightUnit == LightUnit.Lumen && newLightUnit == LightUnit.Candela)
			{
				intensity = ConvertPunctualLightLumenToCandela(type, intensity, intensity, editor.m_EnableSpotReflector);
			}
			else if (oldLightUnit == LightUnit.Lumen && newLightUnit == LightUnit.Lux)
			{
				intensity = ConvertPunctualLightLumenToLux(type, intensity, intensity, editor.m_EnableSpotReflector, editor.m_LuxAtDistance);
			}
			else if (oldLightUnit == LightUnit.Lumen && newLightUnit == LightUnit.Ev100)
			{
				intensity = ConvertPunctualLightLumenToEv(type, intensity, intensity, editor.m_EnableSpotReflector);
			}
			else if (oldLightUnit == LightUnit.Candela && newLightUnit == LightUnit.Lumen)
			{
				intensity = ConvertPunctualLightCandelaToLumen(type, editor.m_SpotShape, intensity, editor.m_EnableSpotReflector, editor.m_SpotAngle, editor.m_AspectRatio);
			}
			else if (oldLightUnit == LightUnit.Candela && newLightUnit == LightUnit.Lux)
			{
				intensity = ConvertCandelaToLux(intensity, editor.m_LuxAtDistance);
			}
			else if (oldLightUnit == LightUnit.Candela && newLightUnit == LightUnit.Ev100)
			{
				intensity = ConvertCandelaToEv(intensity);
			}
			else if (oldLightUnit == LightUnit.Lux && newLightUnit == LightUnit.Lumen)
			{
				intensity = ConvertPunctualLightLuxToLumen(type, editor.m_SpotShape, intensity, editor.m_EnableSpotReflector, editor.m_SpotAngle, editor.m_AspectRatio, editor.m_LuxAtDistance);
			}
			else if (oldLightUnit == LightUnit.Lux && newLightUnit == LightUnit.Candela)
			{
				intensity = ConvertLuxToCandela(intensity, editor.m_LuxAtDistance);
			}
			else if (oldLightUnit == LightUnit.Lux && newLightUnit == LightUnit.Ev100)
			{
				intensity = ConvertLuxToEv(intensity, editor.m_LuxAtDistance);
			}
			else if (oldLightUnit == LightUnit.Ev100 && newLightUnit == LightUnit.Lumen)
			{
				intensity = ConvertPunctualLightEvToLumen(type, editor.m_SpotShape, intensity, editor.m_EnableSpotReflector, editor.m_SpotAngle, editor.m_AspectRatio);
			}
			else if (oldLightUnit == LightUnit.Ev100 && newLightUnit == LightUnit.Candela)
			{
				intensity = ConvertEvToCandela(intensity);
			}
			else if (oldLightUnit == LightUnit.Ev100 && newLightUnit == LightUnit.Lux)
			{
				intensity = ConvertEvToLux(intensity, editor.m_LuxAtDistance);
			}
			break;
		case LightType.Area:
			if (oldLightUnit == LightUnit.Lumen && newLightUnit == LightUnit.Nits)
			{
				intensity = ConvertAreaLightLumenToLuminance(editor.m_AreaShape, intensity, editor.m_ShapeWidth, editor.m_ShapeHeight);
			}
			if (oldLightUnit == LightUnit.Nits && newLightUnit == LightUnit.Lumen)
			{
				intensity = ConvertAreaLightLuminanceToLumen(editor.m_AreaShape, intensity, editor.m_ShapeWidth, editor.m_ShapeHeight);
			}
			if (oldLightUnit == LightUnit.Nits && newLightUnit == LightUnit.Ev100)
			{
				intensity = ConvertLuminanceToEv(intensity);
			}
			if (oldLightUnit == LightUnit.Ev100 && newLightUnit == LightUnit.Nits)
			{
				intensity = ConvertEvToLuminance(intensity);
			}
			if (oldLightUnit == LightUnit.Ev100 && newLightUnit == LightUnit.Lumen)
			{
				intensity = ConvertAreaLightEvToLumen(editor.m_AreaShape, intensity, editor.m_ShapeWidth, editor.m_ShapeHeight);
			}
			if (oldLightUnit == LightUnit.Lumen && newLightUnit == LightUnit.Ev100)
			{
				intensity = ConvertAreaLightLumenToEv(editor.m_AreaShape, intensity, editor.m_ShapeWidth, editor.m_ShapeHeight);
			}
			break;
		}
		return intensity;
	}
```

- `public static ConvertLuminanceToEv(System.Single luminance) : System.Single`  

```csharp
public static float ConvertLuminanceToEv(float luminance)
	{
		return Mathf.Log(luminance, 2f) + s_LuminanceToEvFactor;
	}
```

- `public static ConvertLuxToCandela(System.Single lux, System.Single distance) : System.Single`  

```csharp
public static float ConvertLuxToCandela(float lux, float distance)
	{
		return lux * distance * distance;
	}
```

- `public static ConvertLuxToEv(System.Single lux, System.Single distance) : System.Single`  

```csharp
public static float ConvertLuxToEv(float lux, float distance)
	{
		return ConvertLuminanceToEv(ConvertLuxToCandela(lux, distance));
	}
```

- `public static ConvertPointLightCandelaToLumen(System.Single intensity) : System.Single`  

```csharp
public static float ConvertPointLightCandelaToLumen(float intensity)
	{
		return intensity * (MathF.PI * 4f);
	}
```

- `public static ConvertPointLightLumenToCandela(System.Single intensity) : System.Single`  

```csharp
public static float ConvertPointLightLumenToCandela(float intensity)
	{
		return intensity / (MathF.PI * 4f);
	}
```

- `public static ConvertPunctualLightCandelaToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single candela, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio) : System.Single`  

```csharp
public static float ConvertPunctualLightCandelaToLumen(LightType lightType, SpotLightShape spotLightShape, float candela, bool enableSpotReflector, float spotAngle, float aspectRatio)
	{
		if (lightType == LightType.Spot && enableSpotReflector)
		{
			switch (spotLightShape)
			{
			case SpotLightShape.Cone:
				return ConvertSpotLightCandelaToLumen(candela, spotAngle * (MathF.PI / 180f), exact: true);
			case SpotLightShape.Pyramid:
			{
				CalculateAnglesForPyramid(aspectRatio, spotAngle * (MathF.PI / 180f), out var angleA, out var angleB);
				return ConvertFrustrumLightCandelaToLumen(candela, angleA, angleB);
			}
			default:
				return ConvertPointLightCandelaToLumen(candela);
			}
		}
		return ConvertPointLightCandelaToLumen(candela);
	}
```

- `public static ConvertPunctualLightEvToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single ev, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio) : System.Single`  

```csharp
public static float ConvertPunctualLightEvToLumen(LightType lightType, SpotLightShape spotLightShape, float ev, bool enableSpotReflector, float spotAngle, float aspectRatio)
	{
		float candela = ConvertEvToCandela(ev);
		return ConvertPunctualLightCandelaToLumen(lightType, spotLightShape, candela, enableSpotReflector, spotAngle, aspectRatio);
	}
```

- `public static ConvertPunctualLightLumenToCandela(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector) : System.Single`  

```csharp
public static float ConvertPunctualLightLumenToCandela(LightType lightType, float lumen, float initialIntensity, bool enableSpotReflector)
	{
		if (lightType == LightType.Spot && enableSpotReflector)
		{
			return initialIntensity;
		}
		return ConvertPointLightLumenToCandela(lumen);
	}
```

- `public static ConvertPunctualLightLumenToEv(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector) : System.Single`  

```csharp
public static float ConvertPunctualLightLumenToEv(LightType lightType, float lumen, float initialIntensity, bool enableSpotReflector)
	{
		return ConvertCandelaToEv(ConvertPunctualLightLumenToCandela(lightType, lumen, initialIntensity, enableSpotReflector));
	}
```

- `public static ConvertPunctualLightLumenToLux(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector, System.Single distance) : System.Single`  

```csharp
public static float ConvertPunctualLightLumenToLux(LightType lightType, float lumen, float initialIntensity, bool enableSpotReflector, float distance)
	{
		return ConvertCandelaToLux(ConvertPunctualLightLumenToCandela(lightType, lumen, initialIntensity, enableSpotReflector), distance);
	}
```

- `public static ConvertPunctualLightLuxToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single lux, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio, System.Single distance) : System.Single`  

```csharp
public static float ConvertPunctualLightLuxToLumen(LightType lightType, SpotLightShape spotLightShape, float lux, bool enableSpotReflector, float spotAngle, float aspectRatio, float distance)
	{
		float candela = ConvertLuxToCandela(lux, distance);
		return ConvertPunctualLightCandelaToLumen(lightType, spotLightShape, candela, enableSpotReflector, spotAngle, aspectRatio);
	}
```

- `public static ConvertRectLightLumenToLuminance(System.Single intensity, System.Single width, System.Single height) : System.Single`  

```csharp
public static float ConvertRectLightLumenToLuminance(float intensity, float width, float height)
	{
		return intensity / (width * height * MathF.PI);
	}
```

- `public static ConvertRectLightLuminanceToLumen(System.Single intensity, System.Single width, System.Single height) : System.Single`  

```csharp
public static float ConvertRectLightLuminanceToLumen(float intensity, float width, float height)
	{
		return intensity * (width * height * MathF.PI);
	}
```

- `public static ConvertSpotLightCandelaToLumen(System.Single intensity, System.Single angle, System.Boolean exact) : System.Single`  

```csharp
public static float ConvertSpotLightCandelaToLumen(float intensity, float angle, bool exact)
	{
		if (!exact)
		{
			return intensity * MathF.PI;
		}
		return intensity * (2f * (1f - Mathf.Cos(angle / 2f)) * MathF.PI);
	}
```

- `public static ConvertSpotLightLumenToCandela(System.Single intensity, System.Single angle, System.Boolean exact) : System.Single`  

```csharp
public static float ConvertSpotLightLumenToCandela(float intensity, float angle, bool exact)
	{
		if (!exact)
		{
			return intensity / MathF.PI;
		}
		return intensity / (2f * (1f - Mathf.Cos(angle / 2f)) * MathF.PI);
	}
```


