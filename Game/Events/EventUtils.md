# Game.Events.EventUtils

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class EventUtils
{
    public static const System.UInt32 MIN_IN_DANGER_TIME;
    public static const System.Single FLOOD_DEPTH_TOLERANCE;

    public static System.Single GetSeverity(Unity.Mathematics.float3 position, Game.Events.WeatherPhenomenon weatherPhenomenon, Game.Prefabs.WeatherPhenomenonData weatherPhenomenonData);
    public static System.Boolean IsWorse(Game.Events.DangerFlags flags, Game.Events.DangerFlags other);
}
```


## Fields

- `public static const System.UInt32 MIN_IN_DANGER_TIME`  

```csharp
public static const System.UInt32 MIN_IN_DANGER_TIME;
```

- `public static const System.Single FLOOD_DEPTH_TOLERANCE`  

```csharp
public static const System.Single FLOOD_DEPTH_TOLERANCE;
```


## Methods

- `public static GetSeverity(Unity.Mathematics.float3 position, Game.Events.WeatherPhenomenon weatherPhenomenon, Game.Prefabs.WeatherPhenomenonData weatherPhenomenonData) : System.Single`  

```csharp
public static System.Single GetSeverity(Unity.Mathematics.float3 position, Game.Events.WeatherPhenomenon weatherPhenomenon, Game.Prefabs.WeatherPhenomenonData weatherPhenomenonData);
```

- `public static IsWorse(Game.Events.DangerFlags flags, Game.Events.DangerFlags other) : System.Boolean`  

```csharp
public static System.Boolean IsWorse(Game.Events.DangerFlags flags, Game.Events.DangerFlags other);
```


