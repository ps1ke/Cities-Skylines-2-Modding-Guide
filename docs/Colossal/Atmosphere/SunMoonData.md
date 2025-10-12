# Colossal.Atmosphere.SunMoonData

**Assembly:** `Game`  
**Namespace:** `Colossal.Atmosphere`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private static readonly System.Double e`  
- `public static readonly System.Double h0`  
- `public static readonly System.Double h1`  
- `public static readonly System.Double d0`  
- `public static readonly System.Double d1`  
- `public static readonly System.Double d2`  
- `public static readonly System.Double g0`  
- `private static const System.Double J0`  
- `private static const System.Double kDayMs`  
- `private static const System.Double J2000`  

## Methods

- `private GetAltitude(System.Double H, System.Double phi, System.Double dec) : System.Double`  
- `private GetApproximateSolarTransit(System.Double Ht, System.Double lw, System.Double n) : System.Double`  
- `private GetAstroRefraction(System.Double h) : System.Double`  
- `private GetAzimuth(System.Double H, System.Double phi, System.Double dec) : System.Double`  
- `private GetDeclination(System.Double l, System.Double b) : System.Double`  
- `private GetEclipticLongitude(System.Double M) : System.Double`  
- `private GetHourAngle(System.Double h, System.Double phi, System.Double d) : System.Double`  
- `private GetJulianCycle(System.Double d, System.Double lw) : System.Double`  
- `private GetMoonCoords(System.Double d) : Colossal.Atmosphere.MoonCoords`  
- `public GetMoonIllumination(Colossal.Atmosphere.JulianDateTime date) : Colossal.Atmosphere.MoonIllumination`  
- `public GetMoonPosition(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.MoonCoordinate`  
- `private GetRightAscension(System.Double l, System.Double b) : System.Double`  
- `private GetSiderealTime(System.Double d, System.Double lw) : System.Double`  
- `private GetSolarMeanAnomaly(System.Double d) : System.Double`  
- `private GetSolarTransit(System.Double ds, System.Double M, System.Double L) : System.Double`  
- `private GetSunCoords(System.Double d) : Colossal.Atmosphere.EquatorialCoordinate`  
- `public GetSunPosition(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.TopocentricCoordinates`  
- `public GetSunTimes(Colossal.Atmosphere.JulianDateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.SunMoonData+SunTimes`  
- `private GetTimeForSunAltitude(System.Double h, System.Double lw, System.Double phi, System.Double dec, System.Double n, System.Double M, System.Double L) : System.Double`  

## Nested types

- `Colossal.Atmosphere.SunMoonData+SunTimes`  

