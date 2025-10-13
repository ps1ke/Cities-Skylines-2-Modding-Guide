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
public static int GetPercentileChange(EventJournalCityEffect effect)
	{
		if (effect.m_StartValue != 0)
		{
			return Mathf.RoundToInt((float)(effect.m_Value - effect.m_StartValue) / (float)effect.m_StartValue * 100f);
		}
		return 0;
	}
```

- `public static GetValue(Unity.Entities.DynamicBuffer<Game.Events.EventJournalData> data, Game.Events.EventDataTrackingType type) : System.Int32`  

```csharp
public static int GetValue(DynamicBuffer<EventJournalCityEffect> effects, EventCityEffectTrackingType type)
	{
		if (IsValid(type))
		{
			for (int i = 0; i < effects.Length; i++)
			{
				EventJournalCityEffect effect = effects[i];
				if (effect.m_Type == type)
				{
					return GetPercentileChange(effect);
				}
			}
		}
		return 0;
	}
```

- `public static GetValue(Unity.Entities.DynamicBuffer<Game.Events.EventJournalCityEffect> effects, Game.Events.EventCityEffectTrackingType type) : System.Int32`  

```csharp
public static int GetValue(DynamicBuffer<EventJournalCityEffect> effects, EventCityEffectTrackingType type)
	{
		if (IsValid(type))
		{
			for (int i = 0; i < effects.Length; i++)
			{
				EventJournalCityEffect effect = effects[i];
				if (effect.m_Type == type)
				{
					return GetPercentileChange(effect);
				}
			}
		}
		return 0;
	}
```

- `public static IsValid(Game.Events.EventDataTrackingType type) : System.Boolean`  

```csharp
public static bool IsValid(EventCityEffectTrackingType type)
	{
		if (type >= EventCityEffectTrackingType.Crime)
		{
			return type < EventCityEffectTrackingType.Count;
		}
		return false;
	}
```

- `public static IsValid(Game.Events.EventCityEffectTrackingType type) : System.Boolean`  

```csharp
public static bool IsValid(EventCityEffectTrackingType type)
	{
		if (type >= EventCityEffectTrackingType.Crime)
		{
			return type < EventCityEffectTrackingType.Count;
		}
		return false;
	}
```


