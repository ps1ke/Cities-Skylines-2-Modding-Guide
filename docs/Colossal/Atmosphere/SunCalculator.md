# Colossal.Atmosphere.SunCalculator

**Assembly:** `Game`  
**Namespace:** `Colossal.Atmosphere`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.Double J2000`  
- `private static readonly System.Double h0`  
- `private static readonly System.Double d0`  
- `private static readonly System.Double h1`  
- `private static readonly System.Double h2`  
- `private static readonly System.Double h3`  
- `private static readonly System.Double P`  
- `private static readonly System.Double e`  
- `private static readonly System.Double th0`  
- `private static readonly System.Double th1`  
- `private static readonly System.Double M0`  
- `private static readonly System.Double M1`  
- `private static readonly System.Double C1`  
- `private static readonly System.Double C2`  
- `private static readonly System.Double C3`  
- `private static readonly System.Double J0`  
- `private static readonly System.Double J1`  
- `private static readonly System.Double J2`  

## Constructors

- `public SunCalculator()`  

## Methods

- `private static GetAltitude(System.Double th, System.Double a, System.Double phi, System.Double d) : System.Double`  
- `private static GetApproxSolarTransit(System.Double Ht, System.Double lw, System.Double n) : System.Double`  
- `private static GetAzimuth(System.Double th, System.Double a, System.Double phi, System.Double d) : System.Double`  
- `public static GetDayInfo(System.DateTime date, System.Single latitude, System.Single longitude) : Colossal.Atmosphere.SunCalculator+DayInfo`  
- `private static GetEclipticLongitude(System.Double M, System.Double C) : System.Double`  
- `private static GetEquationOfCenter(System.Double M) : System.Double`  
- `private static GetHourAngle(System.Double h, System.Double phi, System.Double d) : System.Double`  
- `private static GetJulianCycle(System.Double J, System.Double lw) : System.Double`  
- `private static GetRightAscension(System.Double Lsun) : System.Double`  
- `private static GetSiderealTime(System.Double J, System.Double lw) : System.Double`  
- `private static GetSolarMeanAnomaly(System.Double Js) : System.Double`  
- `private static GetSolarTransit(System.Double Js, System.Double M, System.Double Lsun) : System.Double`  
- `private static GetSunDeclination(System.Double Lsun) : System.Double`  
- `private static GetSunPosition(System.Double J, System.Double lw, System.Double phi) : Colossal.Atmosphere.TopocentricCoordinates`  
- `public static GetSunPosition(System.DateTime date, System.Single latitude, System.Single longitude) : Colossal.Atmosphere.TopocentricCoordinates`  
- `private static GetSunriseJulianDate(System.Double Jtransit, System.Double Jset) : System.Double`  
- `private static GetSunsetJulianDate(System.Double w0, System.Double M, System.Double Lsun, System.Double lw, System.Double n) : System.Double`  

## Nested types

- `Colossal.Atmosphere.SunCalculator+Twiligth`  
- `Colossal.Atmosphere.SunCalculator+TimeFrame`  
- `Colossal.Atmosphere.SunCalculator+DayInfo`  

