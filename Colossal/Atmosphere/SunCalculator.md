# Colossal.Atmosphere.SunCalculator

**Assembly:** `Game`  
**Namespace:** `Colossal.Atmosphere`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class SunCalculator
{
    private static readonly System.Double J2000;
    private static readonly System.Double h0;
    private static readonly System.Double d0;
    private static readonly System.Double h1;
    private static readonly System.Double h2;
    private static readonly System.Double h3;
    private static readonly System.Double P;
    private static readonly System.Double e;
    private static readonly System.Double th0;
    private static readonly System.Double th1;
    private static readonly System.Double M0;
    private static readonly System.Double M1;
    private static readonly System.Double C1;
    private static readonly System.Double C2;
    private static readonly System.Double C3;
    private static readonly System.Double J0;
    private static readonly System.Double J1;
    private static readonly System.Double J2;

    public SunCalculator();

    private static System.Double GetAltitude(System.Double th, System.Double a, System.Double phi, System.Double d);
    private static System.Double GetApproxSolarTransit(System.Double Ht, System.Double lw, System.Double n);
    private static System.Double GetAzimuth(System.Double th, System.Double a, System.Double phi, System.Double d);
    public static Colossal.Atmosphere.SunCalculator+DayInfo GetDayInfo(System.DateTime date, System.Single latitude, System.Single longitude);
    private static System.Double GetEclipticLongitude(System.Double M, System.Double C);
    private static System.Double GetEquationOfCenter(System.Double M);
    private static System.Double GetHourAngle(System.Double h, System.Double phi, System.Double d);
    private static System.Double GetJulianCycle(System.Double J, System.Double lw);
    private static System.Double GetRightAscension(System.Double Lsun);
    private static System.Double GetSiderealTime(System.Double J, System.Double lw);
    private static System.Double GetSolarMeanAnomaly(System.Double Js);
    private static System.Double GetSolarTransit(System.Double Js, System.Double M, System.Double Lsun);
    private static System.Double GetSunDeclination(System.Double Lsun);
    private static Colossal.Atmosphere.TopocentricCoordinates GetSunPosition(System.Double J, System.Double lw, System.Double phi);
    public static Colossal.Atmosphere.TopocentricCoordinates GetSunPosition(System.DateTime date, System.Single latitude, System.Single longitude);
    private static System.Double GetSunriseJulianDate(System.Double Jtransit, System.Double Jset);
    private static System.Double GetSunsetJulianDate(System.Double w0, System.Double M, System.Double Lsun, System.Double lw, System.Double n);
}
```


## Fields

- `private static readonly System.Double J2000`  

```csharp
private static readonly System.Double J2000;
```

- `private static readonly System.Double h0`  

```csharp
private static readonly System.Double h0;
```

- `private static readonly System.Double d0`  

```csharp
private static readonly System.Double d0;
```

- `private static readonly System.Double h1`  

```csharp
private static readonly System.Double h1;
```

- `private static readonly System.Double h2`  

```csharp
private static readonly System.Double h2;
```

- `private static readonly System.Double h3`  

```csharp
private static readonly System.Double h3;
```

- `private static readonly System.Double P`  

```csharp
private static readonly System.Double P;
```

- `private static readonly System.Double e`  

```csharp
private static readonly System.Double e;
```

- `private static readonly System.Double th0`  

```csharp
private static readonly System.Double th0;
```

- `private static readonly System.Double th1`  

```csharp
private static readonly System.Double th1;
```

- `private static readonly System.Double M0`  

```csharp
private static readonly System.Double M0;
```

- `private static readonly System.Double M1`  

```csharp
private static readonly System.Double M1;
```

- `private static readonly System.Double C1`  

```csharp
private static readonly System.Double C1;
```

- `private static readonly System.Double C2`  

```csharp
private static readonly System.Double C2;
```

- `private static readonly System.Double C3`  

```csharp
private static readonly System.Double C3;
```

- `private static readonly System.Double J0`  

```csharp
private static readonly System.Double J0;
```

- `private static readonly System.Double J1`  

```csharp
private static readonly System.Double J1;
```

- `private static readonly System.Double J2`  

```csharp
private static readonly System.Double J2;
```


## Constructors

- `public SunCalculator()`  

```csharp
public SunCalculator();
```


## Methods

- `private static GetAltitude(System.Double th, System.Double a, System.Double phi, System.Double d) : System.Double`  

```csharp
private static System.Double GetAltitude(System.Double th, System.Double a, System.Double phi, System.Double d);
```

- `private static GetApproxSolarTransit(System.Double Ht, System.Double lw, System.Double n) : System.Double`  

```csharp
private static System.Double GetApproxSolarTransit(System.Double Ht, System.Double lw, System.Double n);
```

- `private static GetAzimuth(System.Double th, System.Double a, System.Double phi, System.Double d) : System.Double`  

```csharp
private static System.Double GetAzimuth(System.Double th, System.Double a, System.Double phi, System.Double d);
```

- `public static GetDayInfo(System.DateTime date, System.Single latitude, System.Single longitude) : Colossal.Atmosphere.SunCalculator+DayInfo`  

```csharp
public static Colossal.Atmosphere.SunCalculator+DayInfo GetDayInfo(System.DateTime date, System.Single latitude, System.Single longitude);
```

- `private static GetEclipticLongitude(System.Double M, System.Double C) : System.Double`  

```csharp
private static System.Double GetEclipticLongitude(System.Double M, System.Double C);
```

- `private static GetEquationOfCenter(System.Double M) : System.Double`  

```csharp
private static System.Double GetEquationOfCenter(System.Double M);
```

- `private static GetHourAngle(System.Double h, System.Double phi, System.Double d) : System.Double`  

```csharp
private static System.Double GetHourAngle(System.Double h, System.Double phi, System.Double d);
```

- `private static GetJulianCycle(System.Double J, System.Double lw) : System.Double`  

```csharp
private static System.Double GetJulianCycle(System.Double J, System.Double lw);
```

- `private static GetRightAscension(System.Double Lsun) : System.Double`  

```csharp
private static System.Double GetRightAscension(System.Double Lsun);
```

- `private static GetSiderealTime(System.Double J, System.Double lw) : System.Double`  

```csharp
private static System.Double GetSiderealTime(System.Double J, System.Double lw);
```

- `private static GetSolarMeanAnomaly(System.Double Js) : System.Double`  

```csharp
private static System.Double GetSolarMeanAnomaly(System.Double Js);
```

- `private static GetSolarTransit(System.Double Js, System.Double M, System.Double Lsun) : System.Double`  

```csharp
private static System.Double GetSolarTransit(System.Double Js, System.Double M, System.Double Lsun);
```

- `private static GetSunDeclination(System.Double Lsun) : System.Double`  

```csharp
private static System.Double GetSunDeclination(System.Double Lsun);
```

- `private static GetSunPosition(System.Double J, System.Double lw, System.Double phi) : Colossal.Atmosphere.TopocentricCoordinates`  

```csharp
private static Colossal.Atmosphere.TopocentricCoordinates GetSunPosition(System.Double J, System.Double lw, System.Double phi);
```

- `public static GetSunPosition(System.DateTime date, System.Single latitude, System.Single longitude) : Colossal.Atmosphere.TopocentricCoordinates`  

```csharp
public static Colossal.Atmosphere.TopocentricCoordinates GetSunPosition(System.DateTime date, System.Single latitude, System.Single longitude);
```

- `private static GetSunriseJulianDate(System.Double Jtransit, System.Double Jset) : System.Double`  

```csharp
private static System.Double GetSunriseJulianDate(System.Double Jtransit, System.Double Jset);
```

- `private static GetSunsetJulianDate(System.Double w0, System.Double M, System.Double Lsun, System.Double lw, System.Double n) : System.Double`  

```csharp
private static System.Double GetSunsetJulianDate(System.Double w0, System.Double M, System.Double Lsun, System.Double lw, System.Double n);
```


## Nested types

- `Colossal.Atmosphere.SunCalculator+Twiligth`  
- `Colossal.Atmosphere.SunCalculator+TimeFrame`  
- `Colossal.Atmosphere.SunCalculator+DayInfo`  

