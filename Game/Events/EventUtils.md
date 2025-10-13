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
public static float GetSeverity(float3 position, WeatherPhenomenon weatherPhenomenon, WeatherPhenomenonData weatherPhenomenonData)
	{
		float num = math.distance(position.xz, weatherPhenomenon.m_HotspotPosition.xz) / weatherPhenomenon.m_HotspotRadius;
		float num2 = weatherPhenomenon.m_Intensity * weatherPhenomenonData.m_DamageSeverity * (1f - num);
		return math.select(num2, 0f, num2 < 0.001f);
	}
```

- `public static IsWorse(Game.Events.DangerFlags flags, Game.Events.DangerFlags other) : System.Boolean`  

```csharp
public static bool IsWorse(DangerFlags flags, DangerFlags other)
	{
		DangerFlags dangerFlags = flags ^ other;
		if ((dangerFlags & DangerFlags.Evacuate) != 0)
		{
			return (flags & DangerFlags.Evacuate) != 0;
		}
		if ((dangerFlags & DangerFlags.StayIndoors) != 0)
		{
			return (flags & DangerFlags.StayIndoors) != 0;
		}
		return false;
	}
```


