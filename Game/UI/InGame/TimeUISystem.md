# Game.UI.InGame.TimeUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TimeUISystem : Game.UI.UISystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Unity.Entities.EntityQuery m_TimeSettingsQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Colossal.UI.Binding.EventBinding<System.Boolean> m_SimulationPausedBarrierBinding;
    private System.Single m_SpeedBeforePause;
    private System.Boolean m_UnpausedBeforeForcedPause;
    private System.Boolean m_HasFocus;
    private static const System.String kGroup;

    private System.Boolean pausedBarrierActive { private get; }

    public TimeUISystem();

    public System.Int32 GetDay();
    public Game.Rendering.LightingSystem+State GetLightingState();
    public System.Int32 GetSimulationSpeed();
    public System.Int32 GetTicks();
    private Game.UI.InGame.TimeUISystem+TimeSettings GetTimeSettings();
    private Game.Prefabs.TimeSettingsData GetTimeSettingsData();
    private System.Void HandleAppStateChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.AppState state);
    private static System.Single IndexToSpeed(System.Int32 index);
    public System.Boolean IsPaused();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void SetSimulationPaused(System.Boolean paused);
    private System.Void SetSimulationSpeed(System.Int32 speedIndex);
    private static System.Int32 SpeedToIndex(System.Single speed);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Unity.Entities.EntityQuery m_TimeSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Colossal.UI.Binding.EventBinding<System.Boolean> m_SimulationPausedBarrierBinding`  

```csharp
private Colossal.UI.Binding.EventBinding<System.Boolean> m_SimulationPausedBarrierBinding;
```

- `private System.Single m_SpeedBeforePause`  

```csharp
private System.Single m_SpeedBeforePause;
```

- `private System.Boolean m_UnpausedBeforeForcedPause`  

```csharp
private System.Boolean m_UnpausedBeforeForcedPause;
```

- `private System.Boolean m_HasFocus`  

```csharp
private System.Boolean m_HasFocus;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `private System.Boolean pausedBarrierActive { private get }`  

```csharp
private System.Boolean pausedBarrierActive { private get; }
```


## Constructors

- `public TimeUISystem()`  

```csharp
[Preserve]
	public TimeUISystem()
	{
	}
```


## Methods

- `public GetDay() : System.Int32`  

```csharp
public int GetDay()
	{
		return TimeSystem.GetDay(m_SimulationSystem.frameIndex, TimeData.GetSingleton(m_TimeDataQuery));
	}
```

- `public GetLightingState() : Game.Rendering.LightingSystem+State`  

```csharp
public LightingSystem.State GetLightingState()
	{
		LightingSystem.State state = m_LightingSystem.state;
		if (state != LightingSystem.State.Invalid)
		{
			return state;
		}
		float normalizedTime = m_TimeSystem.normalizedTime;
		if (!(normalizedTime < 7f / 24f) && !(normalizedTime > 0.875f))
		{
			return LightingSystem.State.Day;
		}
		return LightingSystem.State.Night;
	}
```

- `public GetSimulationSpeed() : System.Int32`  

```csharp
public int GetSimulationSpeed()
	{
		return SpeedToIndex(IsPaused() ? m_SpeedBeforePause : m_SimulationSystem.selectedSpeed);
	}
```

- `public GetTicks() : System.Int32`  

```csharp
public int GetTicks()
	{
		float num = 182.04445f;
		return Mathf.FloorToInt(Mathf.Floor((float)(m_SimulationSystem.frameIndex - TimeData.GetSingleton(m_TimeDataQuery).m_FirstFrame) / num) * num);
	}
```

- `private GetTimeSettings() : Game.UI.InGame.TimeUISystem+TimeSettings`  

```csharp
private TimeSettings GetTimeSettings()
	{
		TimeSettingsData timeSettingsData = GetTimeSettingsData();
		TimeData singleton = TimeData.GetSingleton(m_TimeDataQuery);
		return new TimeSettings
		{
			ticksPerDay = 262144,
			daysPerYear = timeSettingsData.m_DaysPerYear,
			epochTicks = Mathf.RoundToInt(singleton.TimeOffset * 262144f) + Mathf.RoundToInt(singleton.GetDateOffset(timeSettingsData.m_DaysPerYear) * 262144f * (float)timeSettingsData.m_DaysPerYear),
			epochYear = singleton.m_StartingYear
		};
	}
```

- `private GetTimeSettingsData() : Game.Prefabs.TimeSettingsData`  

```csharp
private TimeSettingsData GetTimeSettingsData()
	{
		if (m_TimeSettingsQuery.IsEmptyIgnoreFilter)
		{
			return new TimeSettingsData
			{
				m_DaysPerYear = 12
			};
		}
		return m_TimeSettingsQuery.GetSingleton<TimeSettingsData>();
	}
```

- `private HandleAppStateChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.AppState state) : System.Void`  

```csharp
private void HandleAppStateChanged(IPlatformServiceIntegration psi, AppState state)
	{
		switch (state)
		{
		case AppState.Default:
			m_HasFocus = true;
			break;
		case AppState.Constrained:
			m_HasFocus = false;
			break;
		}
	}
```

- `private static IndexToSpeed(System.Int32 index) : System.Single`  

```csharp
private static float IndexToSpeed(int index)
	{
		return Mathf.Pow(2f, Mathf.Clamp(index, 0, 2));
	}
```

- `public IsPaused() : System.Boolean`  

```csharp
public bool IsPaused()
	{
		return m_SimulationSystem.selectedSpeed == 0f;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_LightingSystem = base.World.GetOrCreateSystemManaged<LightingSystem>();
		m_TimeSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		AddUpdateBinding(new GetterValueBinding<TimeSettings>("time", "timeSettings", GetTimeSettings, new ValueWriter<TimeSettings>()));
		AddUpdateBinding(new GetterValueBinding<int>("time", "ticks", GetTicks));
		AddUpdateBinding(new GetterValueBinding<int>("time", "day", GetDay));
		AddUpdateBinding(new GetterValueBinding<LightingSystem.State>("time", "lightingState", GetLightingState, new DelegateWriter<LightingSystem.State>(delegate(IJsonWriter writer, LightingSystem.State value)
		{
			writer.Write((int)value);
		})));
		AddUpdateBinding(new GetterValueBinding<bool>("time", "simulationPaused", IsPaused));
		AddUpdateBinding(new GetterValueBinding<int>("time", "simulationSpeed", GetSimulationSpeed));
		AddBinding(m_SimulationPausedBarrierBinding = new EventBinding<bool>("time", "simulationPausedBarrier"));
		AddBinding(new TriggerBinding<bool>("time", "setSimulationPaused", SetSimulationPaused));
		AddBinding(new TriggerBinding<int>("time", "setSimulationSpeed", SetSimulationSpeed));
		PlatformManager.instance.onAppStateChanged += HandleAppStateChanged;
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_SpeedBeforePause = 1f;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		if (m_SimulationSystem.selectedSpeed > 0f)
		{
			m_SpeedBeforePause = m_SimulationSystem.selectedSpeed;
		}
		if (!m_HasFocus || m_SimulationPausedBarrierBinding.observerCount > 0)
		{
			if (!IsPaused())
			{
				m_UnpausedBeforeForcedPause = true;
			}
			m_SimulationSystem.selectedSpeed = 0f;
		}
		else
		{
			if (m_UnpausedBeforeForcedPause)
			{
				m_SimulationSystem.selectedSpeed = m_SpeedBeforePause;
			}
			m_UnpausedBeforeForcedPause = false;
		}
	}
```

- `private SetSimulationPaused(System.Boolean paused) : System.Void`  

```csharp
private void SetSimulationPaused(bool paused)
	{
		if (!pausedBarrierActive)
		{
			m_SimulationSystem.selectedSpeed = (paused ? 0f : m_SpeedBeforePause);
		}
		else
		{
			m_UnpausedBeforeForcedPause = !paused;
		}
	}
```

- `private SetSimulationSpeed(System.Int32 speedIndex) : System.Void`  

```csharp
private void SetSimulationSpeed(int speedIndex)
	{
		if (!pausedBarrierActive)
		{
			m_SimulationSystem.selectedSpeed = IndexToSpeed(speedIndex);
			return;
		}
		m_SpeedBeforePause = IndexToSpeed(speedIndex);
		m_UnpausedBeforeForcedPause = true;
	}
```

- `private static SpeedToIndex(System.Single speed) : System.Int32`  

```csharp
private static int SpeedToIndex(float speed)
	{
		if (!(speed > 0f))
		{
			return 0;
		}
		return Mathf.Clamp((int)Mathf.Log(speed, 2f), 0, 2);
	}
```


## Nested types

- `Game.UI.InGame.TimeUISystem+TimeSettings`  
- `Game.UI.InGame.TimeUISystem+<>c`  

