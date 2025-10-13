# Game.Events.EventJournalUtils

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class EventJournalUtils
{
    public static System.Int32 GetPercentileChange(Game.Events.EventJournalCityEffect effect);
    public static System.Int32 GetValue(Unity.Entities.DynamicBuffer<Game.Events.EventJournalData> data, Game.Events.EventDataTrackingType type);
    public static System.Int32 GetValue(Unity.Entities.DynamicBuffer<Game.Events.EventJournalCityEffect> effects, Game.Events.EventCityEffectTrackingType type);
    public static System.Boolean IsValid(Game.Events.EventDataTrackingType type);
    public static System.Boolean IsValid(Game.Events.EventCityEffectTrackingType type);
}
```


## Methods

- `public static GetPercentileChange(Game.Events.EventJournalCityEffect effect) : System.Int32`  

```csharp
public static System.Int32 GetPercentileChange(Game.Events.EventJournalCityEffect effect);
```

- `public static GetValue(Unity.Entities.DynamicBuffer<Game.Events.EventJournalData> data, Game.Events.EventDataTrackingType type) : System.Int32`  

```csharp
public static System.Int32 GetValue(Unity.Entities.DynamicBuffer<Game.Events.EventJournalData> data, Game.Events.EventDataTrackingType type);
```

- `public static GetValue(Unity.Entities.DynamicBuffer<Game.Events.EventJournalCityEffect> effects, Game.Events.EventCityEffectTrackingType type) : System.Int32`  

```csharp
public static System.Int32 GetValue(Unity.Entities.DynamicBuffer<Game.Events.EventJournalCityEffect> effects, Game.Events.EventCityEffectTrackingType type);
```

- `public static IsValid(Game.Events.EventDataTrackingType type) : System.Boolean`  

```csharp
public static System.Boolean IsValid(Game.Events.EventDataTrackingType type);
```

- `public static IsValid(Game.Events.EventCityEffectTrackingType type) : System.Boolean`  

```csharp
public static System.Boolean IsValid(Game.Events.EventCityEffectTrackingType type);
```


