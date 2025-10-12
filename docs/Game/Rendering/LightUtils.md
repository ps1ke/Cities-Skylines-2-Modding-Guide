# Game.Rendering.LightUtils

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Properties

- `private static System.Single s_LuminanceToEvFactor { private get }`  
- `private static System.Single s_EvToLuminanceFactor { private get }`  

## Methods

- `public static CalculateAnglesForPyramid(System.Single aspectRatio, System.Single spotAngle, System.Single& angleA, System.Single& angleB) : System.Void`  
- `public static CalculateLineLightLumenToLuminance(System.Single intensity, System.Single lineWidth) : System.Single`  
- `public static CalculateLineLightLuminanceToLumen(System.Single intensity, System.Single lineWidth) : System.Single`  
- `public static ConvertAreaLightEvToLumen(Game.Rendering.AreaLightShape AreaLightShape, System.Single ev, System.Single width, System.Single height) : System.Single`  
- `public static ConvertAreaLightLumenToEv(Game.Rendering.AreaLightShape AreaLightShape, System.Single lumen, System.Single width, System.Single height) : System.Single`  
- `public static ConvertAreaLightLumenToLuminance(Game.Rendering.AreaLightShape areaLightShape, System.Single lumen, System.Single width, System.Single height = 0) : System.Single`  
- `public static ConvertAreaLightLuminanceToLumen(Game.Rendering.AreaLightShape areaLightShape, System.Single luminance, System.Single width, System.Single height = 0) : System.Single`  
- `public static ConvertCandelaToEv(System.Single candela) : System.Single`  
- `public static ConvertCandelaToLux(System.Single candela, System.Single distance) : System.Single`  
- `public static ConvertEvToCandela(System.Single ev) : System.Single`  
- `public static ConvertEvToLuminance(System.Single ev) : System.Single`  
- `public static ConvertEvToLux(System.Single ev, System.Single distance) : System.Single`  
- `public static ConvertFrustrumLightCandelaToLumen(System.Single intensity, System.Single angleA, System.Single angleB) : System.Single`  
- `public static ConvertFrustrumLightLumenToCandela(System.Single intensity, System.Single angleA, System.Single angleB) : System.Single`  
- `public static ConvertLightIntensity(Game.Rendering.LightUnit oldLightUnit, Game.Rendering.LightUnit newLightUnit, Game.Prefabs.Effects.LightEffect editor, System.Single intensity) : System.Single`  
- `public static ConvertLuminanceToEv(System.Single luminance) : System.Single`  
- `public static ConvertLuxToCandela(System.Single lux, System.Single distance) : System.Single`  
- `public static ConvertLuxToEv(System.Single lux, System.Single distance) : System.Single`  
- `public static ConvertPointLightCandelaToLumen(System.Single intensity) : System.Single`  
- `public static ConvertPointLightLumenToCandela(System.Single intensity) : System.Single`  
- `public static ConvertPunctualLightCandelaToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single candela, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio) : System.Single`  
- `public static ConvertPunctualLightEvToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single ev, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio) : System.Single`  
- `public static ConvertPunctualLightLumenToCandela(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector) : System.Single`  
- `public static ConvertPunctualLightLumenToEv(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector) : System.Single`  
- `public static ConvertPunctualLightLumenToLux(Game.Rendering.LightType lightType, System.Single lumen, System.Single initialIntensity, System.Boolean enableSpotReflector, System.Single distance) : System.Single`  
- `public static ConvertPunctualLightLuxToLumen(Game.Rendering.LightType lightType, Game.Rendering.SpotLightShape spotLightShape, System.Single lux, System.Boolean enableSpotReflector, System.Single spotAngle, System.Single aspectRatio, System.Single distance) : System.Single`  
- `public static ConvertRectLightLumenToLuminance(System.Single intensity, System.Single width, System.Single height) : System.Single`  
- `public static ConvertRectLightLuminanceToLumen(System.Single intensity, System.Single width, System.Single height) : System.Single`  
- `public static ConvertSpotLightCandelaToLumen(System.Single intensity, System.Single angle, System.Boolean exact) : System.Single`  
- `public static ConvertSpotLightLumenToCandela(System.Single intensity, System.Single angle, System.Boolean exact) : System.Single`  

