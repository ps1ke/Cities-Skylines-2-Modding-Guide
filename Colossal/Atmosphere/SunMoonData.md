# Colossal.Atmosphere.SunMoonData

**Assembly:** `Game`  
**Namespace:** `Colossal.Atmosphere`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SunMoonData
{
    private static readonly System.Double e;
    public static readonly System.Double h0;
    public static readonly System.Double h1;
    public static readonly System.Double d0;
    public static readonly System.Double d1;
    public static readonly System.Double d2;
    public static readonly System.Double g0;
    private static const System.Double J0;
    private static const System.Double kDayMs;
    private static const System.Double J2000;

    private System.Double GetAltitude(System.Double H, System.Double phi, System.Double dec);
    private System.Double GetApproximateSolarTransit(System.Double Ht, System.Double lw, System.Double n);
    private System.Double GetAstroRefraction(System.Double h);
    private System.Double GetAzimuth(System.Double H, System.Double phi, System.Double dec);
    private System.Double GetDeclination(System.Double l, System.Double b);
    private System.Double GetEclipticLongitude(System.Double M);
    private System.Double GetHourAngle(System.Double h, System.Double phi, System.Double d);
    private System.Double GetJulianCycle(System.Double d, System.Double lw);
    private Colossal.Atmosphere.MoonCoords GetMoonCoords(System.Double d);
    public Colossal.Atmosphere.MoonIllumination GetMoonIllumination(Colossal.Atmosphere.JulianDateTime date);
    public Colossal.Atmosphere.MoonCoordinate GetMoonPosition(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude);
    private System.Double GetRightAscension(System.Double l, System.Double b);
    private System.Double GetSiderealTime(System.Double d, System.Double lw);
    private System.Double GetSolarMeanAnomaly(System.Double d);
    private System.Double GetSolarTransit(System.Double ds, System.Double M, System.Double L);
    private Colossal.Atmosphere.EquatorialCoordinate GetSunCoords(System.Double d);
    public Colossal.Atmosphere.TopocentricCoordinates GetSunPosition(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude);
    public Colossal.Atmosphere.SunMoonData+SunTimes GetSunTimes(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude);
    private System.Double GetTimeForSunAltitude(System.Double h, System.Double lw, System.Double phi, System.Double dec, System.Double n, System.Double M, System.Double L);
}
```


## Fields

- `private static readonly System.Double e`  

```csharp
private static readonly System.Double e;
```

- `public static readonly System.Double h0`  

```csharp
public static readonly System.Double h0;
```

- `public static readonly System.Double h1`  

```csharp
public static readonly System.Double h1;
```

- `public static readonly System.Double d0`  

```csharp
public static readonly System.Double d0;
```

- `public static readonly System.Double d1`  

```csharp
public static readonly System.Double d1;
```

- `public static readonly System.Double d2`  

```csharp
public static readonly System.Double d2;
```

- `public static readonly System.Double g0`  

```csharp
public static readonly System.Double g0;
```

- `private static const System.Double J0`  

```csharp
private static const System.Double J0;
```

- `private static const System.Double kDayMs`  

```csharp
private static const System.Double kDayMs;
```

- `private static const System.Double J2000`  

```csharp
private static const System.Double J2000;
```


## Methods

- `private GetAltitude(System.Double H, System.Double phi, System.Double dec) : System.Double`  

```csharp
private System.Double GetAltitude(System.Double H, System.Double phi, System.Double dec);
```

- `private GetApproximateSolarTransit(System.Double Ht, System.Double lw, System.Double n) : System.Double`  

```csharp
private System.Double GetApproximateSolarTransit(System.Double Ht, System.Double lw, System.Double n);
```

- `private GetAstroRefraction(System.Double h) : System.Double`  

```csharp
private System.Double GetAstroRefraction(System.Double h);
```

- `private GetAzimuth(System.Double H, System.Double phi, System.Double dec) : System.Double`  

```csharp
private System.Double GetAzimuth(System.Double H, System.Double phi, System.Double dec);
```

- `private GetDeclination(System.Double l, System.Double b) : System.Double`  

```csharp
private System.Double GetDeclination(System.Double l, System.Double b);
```

- `private GetEclipticLongitude(System.Double M) : System.Double`  

```csharp
private System.Double GetEclipticLongitude(System.Double M);
```

- `private GetHourAngle(System.Double h, System.Double phi, System.Double d) : System.Double`  

```csharp
private System.Double GetHourAngle(System.Double h, System.Double phi, System.Double d);
```

- `private GetJulianCycle(System.Double d, System.Double lw) : System.Double`  

```csharp
private System.Double GetJulianCycle(System.Double d, System.Double lw);
```

- `private GetMoonCoords(System.Double d) : Colossal.Atmosphere.MoonCoords`  

```csharp
private Colossal.Atmosphere.MoonCoords GetMoonCoords(System.Double d);
```

- `public GetMoonIllumination(Colossal.Atmosphere.JulianDateTime date) : Colossal.Atmosphere.MoonIllumination`  

```csharp
public Colossal.Atmosphere.MoonIllumination GetMoonIllumination(Colossal.Atmosphere.JulianDateTime date);
```

- `public GetMoonPosition(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.MoonCoordinate`  

```csharp
public Colossal.Atmosphere.MoonCoordinate GetMoonPosition(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude);
```

- `private GetRightAscension(System.Double l, System.Double b) : System.Double`  

```csharp
private System.Double GetRightAscension(System.Double l, System.Double b);
```

- `private GetSiderealTime(System.Double d, System.Double lw) : System.Double`  

```csharp
private System.Double GetSiderealTime(System.Double d, System.Double lw);
```

- `private GetSolarMeanAnomaly(System.Double d) : System.Double`  

```csharp
private System.Double GetSolarMeanAnomaly(System.Double d);
```

- `private GetSolarTransit(System.Double ds, System.Double M, System.Double L) : System.Double`  

```csharp
private System.Double GetSolarTransit(System.Double ds, System.Double M, System.Double L);
```

- `private GetSunCoords(System.Double d) : Colossal.Atmosphere.EquatorialCoordinate`  

```csharp
private Colossal.Atmosphere.EquatorialCoordinate GetSunCoords(System.Double d);
```

- `public GetSunPosition(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.TopocentricCoordinates`  

```csharp
public Colossal.Atmosphere.TopocentricCoordinates GetSunPosition(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude);
```

- `public GetSunTimes(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.SunMoonData+SunTimes`  

```csharp
public Colossal.Atmosphere.SunMoonData+SunTimes GetSunTimes(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude);
```

- `private GetTimeForSunAltitude(System.Double h, System.Double lw, System.Double phi, System.Double dec, System.Double n, System.Double M, System.Double L) : System.Double`  

```csharp
private System.Double GetTimeForSunAltitude(System.Double h, System.Double lw, System.Double phi, System.Double dec, System.Double n, System.Double M, System.Double L);
```


## Nested types

- `Colossal.Atmosphere.SunMoonData+SunTimes`  

