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
public static System.Void CalculateAnglesForPyramid(System.Single aspectRatio, System.Single spotAngle, System.Single& angleA, System.Single& angleB);
```

- `public static CalculateLineLightLumenToLuminance(System.Single intensity, System.Single lineWidth) : System.Single`  

```csharp
public static System.Single CalculateLineLightLumenToLuminance(System.Single intensity, System.Single lineWidth);
```

- `public static CalculateLineLightLuminanceToLumen(System.Single intensity, System.Single lineWidth) : System.Single`  

```csharp
public static System.Single CalculateLineLightLuminanceToLumen(System.Single intensity, System.Single lineWidth);
```

- `public static ConvertAreaLightEvToLumen(Game.Rendering.AreaLightShape AreaLightShape, System.Single ev, System.Single width, System.Single height) : System.Single`  

```csharp
public static System.Single ConvertAreaLightEvToLumen(Game.Rendering.AreaLightShape AreaLightShape, System.Single ev, System.Single width, System.Single height);
```

- `public static ConvertAreaLightLumenToEv(Game.Rendering.AreaLightShape AreaLightShape, System.Single lumen, System.Single width, System.Single height) : System.Single`  

```csharp
public static System.Single ConvertAreaLightLumenToEv(Game.Rendering.AreaLightShape AreaLightShape, System.Single lumen, System.Single width, System.Single height);
```

- `public static ConvertAreaLightLumenToLuminance(Game.Rendering.AreaLightShape areaLightShape, System.Single lumen, System.Single width, System.Single height = 0) : System.Single`  

```csharp
public static System.Single ConvertAreaLightLumenToLuminance(Game.Rendering.AreaLightShape areaLightShape, System.Single lumen, System.Single width, System.Single height);
```

- `public static ConvertAreaLightLuminanceToLumen(Game.Rendering.AreaLightShape areaLightShape, System.Single luminance, System.Single width, System.Single height = 0) : System.Single`  

```csharp
public static System.Single ConvertAreaLightLuminanceToLumen(Game.Rendering.AreaLightShape areaLightShape, System.Single luminance, System.Single width, System.Single height);
```

- `public static ConvertCandelaToEv(System.Single candela) : System.Single`  

```csharp
public static System.Single ConvertCandelaToEv(System.Single candela);
```

- `public static ConvertCandelaToLux(System.Single candela, System.Single distance) : System.Single`  

```csharp
public static System.Single ConvertCandelaToLux(System.Single candela, System.Single distance);
```

- `public static ConvertEvToCandela(System.Single ev) : System.Single`  

```csharp
public static System.Single ConvertEvToCandela(System.Single ev);
```

- `public static ConvertEvToLuminance(System.Single ev) : System.Single`  

```csharp
public static System.Single ConvertEvToLuminance(System.Single ev);
```

- `public static ConvertEvToLux(System.Single ev, System.Single distance) : System.Single`  

```csharp
public static System.Single ConvertEvToLux(System.Single ev, System.Single distance);
```

- `public static ConvertFrustrumLightCandelaToLumen(System.Single intensity, System.Single angleA, System.Single angleB) : System.Single`  

```csharp
public static System.Single ConvertFrustrumLightCandelaToLumen(System.Single intensity, System.Single angleA, System.Single angleB);
```

- `public static ConvertFrustrumLightLumenToCandela(System.Single intensity, System.Single angleA, System.Single angleB) : System.Single`  

```csharp
public static System.Single ConvertFrustrumLightLumenToCandela(System.Single intensity, System.Single angleA, System.Single angleB);
```

- `public static ConvertLightIntensity(Game.Rendering.LightUnit oldLightUnit, Game.Rendering.LightUnit newLightUnit, Game.Prefabs.Effects.LightEffect editor, System.Single intensity) : System.Single`  

```csharp
public static System.Single ConvertLightIntensity(Game.Rendering.LightUnit oldLightUnit, Game.Rendering.LightUnit newLightUnit, Game.Prefabs.Effects.LightEffect editor, System.Single intensity);
```

- `public static ConvertLuminanceToEv(System.Single luminance) : System.Single`  

```csharp
public static System.Single ConvertLuminanceToEv(System.Single luminance);
```

- `public static ConvertLuxToCandela(System.Single lux, System.Single distance) : System.Single`  

```csharp
public static System.Single ConvertLuxToCandela(System.Single lux, System.Single distance);
```

- `public static ConvertLuxToEv(System.Single lux, System.Single distance) : System.Single`  

```csharp
public static System.Single ConvertLuxToEv(System.Single lux, System.Single distance);
```

- `public static ConvertPointLightCandelaToLumen(System.Single intensity) : System.Single`  

```csharp
public static System.Single ConvertPointLightCandelaToLumen(System.Single intensity);
```

- `public static ConvertPointLightLumenToCandela(System.Single intensity) : System.Single`  

```csharp
public static System.Single ConvertPointLightLumenToCandela(System.Single intensity);
```

- `public static ConvertPunctualLightCandelaToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single candela, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio) : System.Single`  

```csharp
public static System.Single ConvertPunctualLightCandelaToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single candela, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio);
```

- `public static ConvertPunctualLightEvToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single ev, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio) : System.Single`  

```csharp
public static System.Single ConvertPunctualLightEvToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single ev, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio);
```

- `public static ConvertPunctualLightLumenToCandela(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector) : System.Single`  

```csharp
public static System.Single ConvertPunctualLightLumenToCandela(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector);
```

- `public static ConvertPunctualLightLumenToEv(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector) : System.Single`  

```csharp
public static System.Single ConvertPunctualLightLumenToEv(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector);
```

- `public static ConvertPunctualLightLumenToLux(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector, System.Single distance) : System.Single`  

```csharp
public static System.Single ConvertPunctualLightLumenToLux(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector, System.Single distance);
```

- `public static ConvertPunctualLightLuxToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single lux, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio, System.Single distance) : System.Single`  

```csharp
public static System.Single ConvertPunctualLightLuxToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single lux, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio, System.Single distance);
```

- `public static ConvertRectLightLumenToLuminance(System.Single intensity, System.Single width, System.Single height) : System.Single`  

```csharp
public static System.Single ConvertRectLightLumenToLuminance(System.Single intensity, System.Single width, System.Single height);
```

- `public static ConvertRectLightLuminanceToLumen(System.Single intensity, System.Single width, System.Single height) : System.Single`  

```csharp
public static System.Single ConvertRectLightLuminanceToLumen(System.Single intensity, System.Single width, System.Single height);
```

- `public static ConvertSpotLightCandelaToLumen(System.Single intensity, System.Single angle, System.Boolean exact) : System.Single`  

```csharp
public static System.Single ConvertSpotLightCandelaToLumen(System.Single intensity, System.Single angle, System.Boolean exact);
```

- `public static ConvertSpotLightLumenToCandela(System.Single intensity, System.Single angle, System.Boolean exact) : System.Single`  

```csharp
public static System.Single ConvertSpotLightLumenToCandela(System.Single intensity, System.Single angle, System.Boolean exact);
```


