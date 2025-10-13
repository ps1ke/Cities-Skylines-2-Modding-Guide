# Colossal.Atmosphere.TopocentricCoordinates

**Assembly:** `Game`  
**Namespace:** `Colossal.Atmosphere`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TopocentricCoordinates
{
    public System.Double azimuth;
    public System.Double altitude;
    private static readonly System.String[] kCardinals;

    public static Unity.Mathematics.float3 ConvertToLocalCoordinates(System.Single theta, System.Single phi);
    private static System.String DegreesToCardinal(System.Double degrees);
    private static System.String FormatAltitude(System.Double altitude);
    private static System.String FormatAzimuth(System.Double azimuth);
    public System.Void Quantize(System.Double resolutionRadians);
    private System.Single Remap(System.Single value, System.Single from1, System.Single to1, System.Single from2, System.Single to2);
    public Unity.Mathematics.float3 ToLocalCoordinates(System.Single& planetTime);
    public virtual System.String ToString();
}
```


## Fields

- `public System.Double azimuth`  

```csharp
public System.Double azimuth;
```

- `public System.Double altitude`  

```csharp
public System.Double altitude;
```

- `private static readonly System.String[] kCardinals`  

```csharp
private static readonly System.String[] kCardinals;
```


## Methods

- `public static ConvertToLocalCoordinates(System.Single theta, System.Single phi) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 ConvertToLocalCoordinates(System.Single theta, System.Single phi);
```

- `private static DegreesToCardinal(System.Double degrees) : System.String`  

```csharp
private static System.String DegreesToCardinal(System.Double degrees);
```

- `private static FormatAltitude(System.Double altitude) : System.String`  

```csharp
private static System.String FormatAltitude(System.Double altitude);
```

- `private static FormatAzimuth(System.Double azimuth) : System.String`  

```csharp
private static System.String FormatAzimuth(System.Double azimuth);
```

- `public Quantize(System.Double resolutionRadians) : System.Void`  

```csharp
public System.Void Quantize(System.Double resolutionRadians);
```

- `private Remap(System.Single value, System.Single from1, System.Single to1, System.Single from2, System.Single to2) : System.Single`  

```csharp
private System.Single Remap(System.Single value, System.Single from1, System.Single to1, System.Single from2, System.Single to2);
```

- `public ToLocalCoordinates(System.Single& planetTime) : Unity.Mathematics.float3`  

```csharp
public Unity.Mathematics.float3 ToLocalCoordinates(System.Single& planetTime);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


