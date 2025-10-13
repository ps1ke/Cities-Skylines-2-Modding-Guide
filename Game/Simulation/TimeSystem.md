# Game.Simulation.TimeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ITimeSystem`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TimeSystem : Game.GameSystemBase, Game.Simulation.ITimeSystem, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private System.Int32 <startingYear>k__BackingField;
    private System.Single m_Time;
    private System.Single m_Date;
    private System.Int32 m_Year;
    private System.Int32 m_DaysPerYear;
    private System.UInt32 m_InitialFrame;
    private Unity.Entities.EntityQuery m_TimeSettingGroup;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    public static const System.Int32 kTicksPerDay;

    public System.Int32 startingYear { get; set; }
    public System.Single normalizedTime { get; }
    public System.Single normalizedDate { get; }
    public System.Int32 year { get; }
    public System.Int32 daysPerYear { get; }

    public TimeSystem();

    private static System.DateTime CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second);
    public System.Void DebugAdvanceTime(System.Int32 minutes);
    public System.DateTime GetCurrentDateTime();
    public System.DateTime GetDateTime(System.Double renderingFrame);
    public static System.Int32 GetDay(System.UInt32 frame, Game.Common.TimeData data);
    public System.Single GetElapsedYears(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
    public System.Single GetStartingDate(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
    protected System.Int32 GetTicks(System.UInt32 frameIndex, Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
    protected System.Int32 GetTicks(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
    public System.Single GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame);
    protected System.Single GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
    public System.Single GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame);
    protected System.Single GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
    protected System.Double GetTimeWithOffset(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame);
    public System.Int32 GetYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateTime();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private System.Int32 <startingYear>k__BackingField`  

```csharp
private System.Int32 <startingYear>k__BackingField;
```

- `private System.Single m_Time`  

```csharp
private System.Single m_Time;
```

- `private System.Single m_Date`  

```csharp
private System.Single m_Date;
```

- `private System.Int32 m_Year`  

```csharp
private System.Int32 m_Year;
```

- `private System.Int32 m_DaysPerYear`  

```csharp
private System.Int32 m_DaysPerYear;
```

- `private System.UInt32 m_InitialFrame`  

```csharp
private System.UInt32 m_InitialFrame;
```

- `private Unity.Entities.EntityQuery m_TimeSettingGroup`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingGroup;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `public static const System.Int32 kTicksPerDay`  

```csharp
public static const System.Int32 kTicksPerDay;
```


## Properties

- `public System.Int32 startingYear { get; set }`  

```csharp
public System.Int32 startingYear { get; set; }
```

- `public System.Single normalizedTime { get }`  

```csharp
public System.Single normalizedTime { get; }
```

- `public System.Single normalizedDate { get }`  

```csharp
public System.Single normalizedDate { get; }
```

- `public System.Int32 year { get }`  

```csharp
public System.Int32 year { get; }
```

- `public System.Int32 daysPerYear { get }`  

```csharp
public System.Int32 daysPerYear { get; }
```


## Constructors

- `public TimeSystem()`  

```csharp
[Preserve]
	public TimeSystem()
	{
	}
```


## Methods

- `private static CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second) : System.DateTime`  

```csharp
private static DateTime CreateDateTime(int year, int day, int hour, int minute, float second)
	{
		DateTime result = new DateTime(0L, DateTimeKind.Utc).AddYears(year - 1).AddDays(day - 1).AddHours(hour)
			.AddMinutes(minute)
			.AddSeconds(second);
		if (result.IsDaylightSavingTime())
		{
			result = result.AddHours(1.0);
		}
		return result;
	}
```

- `public DebugAdvanceTime(System.Int32 minutes) : System.Void`  

```csharp
public void DebugAdvanceTime(int minutes)
	{
		TimeData singleton = m_TimeDataQuery.GetSingleton<TimeData>();
		Entity singletonEntity = m_TimeDataQuery.GetSingletonEntity();
		singleton.m_FirstFrame -= (uint)(minutes * 262144) / 1440u;
		base.EntityManager.SetComponentData(singletonEntity, singleton);
	}
```

- `public GetCurrentDateTime() : System.DateTime`  

```csharp
public DateTime GetCurrentDateTime()
	{
		float num = normalizedTime;
		float num2 = normalizedDate;
		int num3 = Mathf.FloorToInt(24f * num);
		int minute = Mathf.FloorToInt(60f * (24f * num - (float)num3));
		int day = 1 + Mathf.FloorToInt((float)daysPerYear * num2) % daysPerYear;
		return CreateDateTime(year, day, num3, minute, Mathf.Repeat(num, 1f));
	}
```

- `public GetDateTime(System.Double renderingFrame) : System.DateTime`  

```csharp
public DateTime GetDateTime(double renderingFrame)
	{
		TimeSettingsData singleton = m_TimeSettingGroup.GetSingleton<TimeSettingsData>();
		TimeData singleton2 = m_TimeDataQuery.GetSingleton<TimeData>();
		float timeOfDay = GetTimeOfDay(singleton, singleton2, renderingFrame);
		float timeOfYear = GetTimeOfYear(singleton, singleton2, renderingFrame);
		int num = Mathf.FloorToInt(24f * timeOfDay);
		int minute = Mathf.FloorToInt(60f * (24f * timeOfDay - (float)num));
		int day = 1 + Mathf.FloorToInt((float)daysPerYear * timeOfYear) % daysPerYear;
		return CreateDateTime(year, day, num, minute, Mathf.Repeat(timeOfDay, 1f));
	}
```

- `public static GetDay(System.UInt32 frame, Game.Common.TimeData data) : System.Int32`  

```csharp
public static int GetDay(uint frame, TimeData data)
	{
		return Mathf.FloorToInt((float)(frame - data.m_FirstFrame) / 262144f + data.TimeOffset);
	}
```

- `public GetElapsedYears(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  

```csharp
public float GetElapsedYears(TimeSettingsData settings, TimeData data)
	{
		int num = 262144 * settings.m_DaysPerYear;
		return (float)(m_SimulationSystem.frameIndex - data.m_FirstFrame) / (float)num;
	}
```

- `public GetStartingDate(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  

```csharp
public float GetStartingDate(TimeSettingsData settings, TimeData data)
	{
		int num = 262144 * settings.m_DaysPerYear;
		return (float)(GetTicks(data.m_FirstFrame, settings, data) % num) / (float)num;
	}
```

- `protected GetTicks(System.UInt32 frameIndex, Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Int32`  

```csharp
protected int GetTicks(TimeSettingsData settings, TimeData data)
	{
		return (int)(m_SimulationSystem.frameIndex - data.m_FirstFrame) + Mathf.RoundToInt(data.TimeOffset * 262144f) + Mathf.RoundToInt(data.GetDateOffset(settings.m_DaysPerYear) * 262144f * (float)settings.m_DaysPerYear);
	}
```

- `protected GetTicks(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Int32`  

```csharp
protected int GetTicks(TimeSettingsData settings, TimeData data)
	{
		return (int)(m_SimulationSystem.frameIndex - data.m_FirstFrame) + Mathf.RoundToInt(data.TimeOffset * 262144f) + Mathf.RoundToInt(data.GetDateOffset(settings.m_DaysPerYear) * 262144f * (float)settings.m_DaysPerYear);
	}
```

- `public GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame) : System.Single`  

```csharp
protected float GetTimeOfDay(TimeSettingsData settings, TimeData data)
	{
		return (float)(GetTicks(settings, data) % 262144) / 262144f;
	}
```

- `protected GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  

```csharp
protected float GetTimeOfDay(TimeSettingsData settings, TimeData data)
	{
		return (float)(GetTicks(settings, data) % 262144) / 262144f;
	}
```

- `public GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame) : System.Single`  

```csharp
protected float GetTimeOfYear(TimeSettingsData settings, TimeData data)
	{
		int num = 262144 * settings.m_DaysPerYear;
		return (float)(GetTicks(settings, data) % num) / (float)num;
	}
```

- `protected GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  

```csharp
protected float GetTimeOfYear(TimeSettingsData settings, TimeData data)
	{
		int num = 262144 * settings.m_DaysPerYear;
		return (float)(GetTicks(settings, data) % num) / (float)num;
	}
```

- `protected GetTimeWithOffset(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame) : System.Double`  

```csharp
protected double GetTimeWithOffset(TimeSettingsData settings, TimeData data, double renderingFrame)
	{
		return renderingFrame + (double)(data.TimeOffset * 262144f) + (double)(data.GetDateOffset(settings.m_DaysPerYear) * 262144f * (float)settings.m_DaysPerYear);
	}
```

- `public GetYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Int32`  

```csharp
public int GetYear(TimeSettingsData settings, TimeData data)
	{
		int num = 262144 * settings.m_DaysPerYear;
		return data.m_StartingYear + Mathf.FloorToInt(GetTicks(settings, data) / num);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TimeSettingGroup = GetEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		RequireForUpdate(m_TimeSettingGroup);
		RequireForUpdate(m_TimeDataQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		UpdateTime();
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (m_TimeDataQuery.IsEmpty)
		{
			Entity entity = base.EntityManager.CreateEntity();
			TimeData componentData = default(TimeData);
			componentData.SetDefaults(context);
			base.EntityManager.AddComponentData(entity, componentData);
		}
		if (context.purpose == Purpose.NewGame)
		{
			TimeData singleton = m_TimeDataQuery.GetSingleton<TimeData>();
			Entity singletonEntity = m_TimeDataQuery.GetSingletonEntity();
			singleton.m_FirstFrame = m_SimulationSystem.frameIndex;
			singleton.m_StartingYear = startingYear;
			base.EntityManager.SetComponentData(singletonEntity, singleton);
		}
		UpdateTime();
	}
```

- `private UpdateTime() : System.Void`  

```csharp
private void UpdateTime()
	{
		TimeSettingsData singleton = m_TimeSettingGroup.GetSingleton<TimeSettingsData>();
		TimeData singleton2 = m_TimeDataQuery.GetSingleton<TimeData>();
		m_Time = GetTimeOfDay(singleton, singleton2);
		m_Date = GetTimeOfYear(singleton, singleton2);
		m_Year = GetYear(singleton, singleton2);
		m_DaysPerYear = singleton.m_DaysPerYear;
	}
```


