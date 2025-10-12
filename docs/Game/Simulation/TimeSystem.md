# Game.Simulation.TimeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ITimeSystem`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private System.Int32 <startingYear>k__BackingField`  
- `private System.Single m_Time`  
- `private System.Single m_Date`  
- `private System.Int32 m_Year`  
- `private System.Int32 m_DaysPerYear`  
- `private System.UInt32 m_InitialFrame`  
- `private Unity.Entities.EntityQuery m_TimeSettingGroup`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `public static const System.Int32 kTicksPerDay`  

## Properties

- `public System.Int32 startingYear { get; set }`  
- `public System.Single normalizedTime { get }`  
- `public System.Single normalizedDate { get }`  
- `public System.Int32 year { get }`  
- `public System.Int32 daysPerYear { get }`  

## Constructors

- `public TimeSystem()`  

## Methods

- `private static CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second) : System.DateTime`  
- `public DebugAdvanceTime(System.Int32 minutes) : System.Void`  
- `public GetCurrentDateTime() : System.DateTime`  
- `public GetDateTime(System.Double renderingFrame) : System.DateTime`  
- `public static GetDay(System.UInt32 frame, Game.Common.TimeData data) : System.Int32`  
- `public GetElapsedYears(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  
- `public GetStartingDate(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  
- `protected GetTicks(System.UInt32 frameIndex, Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Int32`  
- `protected GetTicks(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Int32`  
- `public GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame) : System.Single`  
- `protected GetTimeOfDay(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  
- `public GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame) : System.Single`  
- `protected GetTimeOfYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Single`  
- `protected GetTimeWithOffset(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data, System.Double renderingFrame) : System.Double`  
- `public GetYear(Game.Prefabs.TimeSettingsData settings, Game.Common.TimeData data) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private UpdateTime() : System.Void`  

