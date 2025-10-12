# Colossal.Atmosphere.TopocentricCoordinates

**Assembly:** `Game`  
**Namespace:** `Colossal.Atmosphere`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public System.Double azimuth`  
- `public System.Double altitude`  
- `private static readonly System.String[] kCardinals`  

## Methods

- `public static ConvertToLocalCoordinates(System.Single theta, System.Single phi) : Unity.Mathematics.float3`  
- `private static DegreesToCardinal(System.Double degrees) : System.String`  
- `private static FormatAltitude(System.Double altitude) : System.String`  
- `private static FormatAzimuth(System.Double azimuth) : System.String`  
- `public Quantize(System.Double resolutionRadians) : System.Void`  
- `private Remap(System.Single value, System.Single from1, System.Single to1, System.Single from2, System.Single to2) : System.Single`  
- `public ToLocalCoordinates(System.Single& planetTime) : Unity.Mathematics.float3`  
- `public virtual ToString() : System.String`  

