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
public TimeSystem();
```


## Methods

- `private static CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second) : System.DateTime`  

```csharp
private static System.DateTime CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second);
```

- `public DebugAdvanceTime(System.Int32 minutes) : System.Void`  

```csharp
public System.Void DebugAdvanceTime(System.Int32 minutes);
```

- `public GetCurrentDateTime() : System.DateTime`  

```csharp
public System.DateTime GetCurrentDateTime();
```

- `public GetDateTime(System.Double renderingFrame) : System.DateTime`  

```csharp
public System.DateTime GetDateTime(System.Double renderingFrame);
```

- `public static GetDay(System.UInt32 frame, Game.Common.TimeData data) : System.Int32`  

```csharp
public static System.Int32 GetDay(System.UInt32 frame, Game.Common.TimeData data);
```

- `public GetElapsedYears(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  

```csharp
public System.Single GetElapsedYears(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
```

- `public GetStartingDate(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  

```csharp
public System.Single GetStartingDate(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
```

- `protected GetTicks(System.UInt32 frameIndex, Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Int32`  

```csharp
protected System.Int32 GetTicks(System.UInt32 frameIndex, Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
```

- `protected GetTicks(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Int32`  

```csharp
protected System.Int32 GetTicks(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
```

- `public GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame) : System.Single`  

```csharp
public System.Single GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame);
```

- `protected GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  

```csharp
protected System.Single GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
```

- `public GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame) : System.Single`  

```csharp
public System.Single GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame);
```

- `protected GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  

```csharp
protected System.Single GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
```

- `protected GetTimeWithOffset(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame) : System.Double`  

```csharp
protected System.Double GetTimeWithOffset(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame);
```

- `public GetYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Int32`  

```csharp
public System.Int32 GetYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private UpdateTime() : System.Void`  

```csharp
private System.Void UpdateTime();
```


