# Game.Simulation.SimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ISimulationSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SimulationSystem : Game.GameSystemBase, Game.Simulation.ISimulationSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private System.UInt32 <frameIndex>k__BackingField;
    private System.Single <frameTime>k__BackingField;
    private System.Single <smoothSpeed>k__BackingField;
    private System.Single <frameDuration>k__BackingField;
    private Game.Simulation.SimulationSystem+PerformancePreference <performancePreference>k__BackingField;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Pathfind.PathfindResultSystem m_PathfindResultSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private System.Single m_Timer;
    private System.Single m_LastSpeed;
    private System.Single m_SelectedSpeed;
    private System.Int32 m_LoadingCount;
    private System.Int32 m_StepCount;
    private System.Boolean m_IsLoading;
    private Unity.Jobs.JobHandle m_WatchDeps;
    private System.Diagnostics.Stopwatch m_Stopwatch;
    public static const System.Single PENDING_FRAMES_SPEED_FACTOR;
    private static const System.Int32 LOADING_COUNT;
    public static const System.String kLoadingTask;

    public System.UInt32 frameIndex { get; private set; }
    public System.Single frameTime { get; private set; }
    public System.Single selectedSpeed { get; set; }
    public System.Single smoothSpeed { get; private set; }
    public System.Single loadingProgress { get; private set; }
    public System.Single frameDuration { get; private set; }
    public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set; }

    public SimulationSystem();

    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateLoadingProgress();
}
```


## Fields

- `private System.UInt32 <frameIndex>k__BackingField`  

```csharp
private System.UInt32 <frameIndex>k__BackingField;
```

- `private System.Single <frameTime>k__BackingField`  

```csharp
private System.Single <frameTime>k__BackingField;
```

- `private System.Single <smoothSpeed>k__BackingField`  

```csharp
private System.Single <smoothSpeed>k__BackingField;
```

- `private System.Single <frameDuration>k__BackingField`  

```csharp
private System.Single <frameDuration>k__BackingField;
```

- `private Game.Simulation.SimulationSystem+PerformancePreference <performancePreference>k__BackingField`  

```csharp
private Game.Simulation.SimulationSystem+PerformancePreference <performancePreference>k__BackingField;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Pathfind.PathfindResultSystem m_PathfindResultSystem`  

```csharp
private Game.Pathfind.PathfindResultSystem m_PathfindResultSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private System.Single m_Timer`  

```csharp
private System.Single m_Timer;
```

- `private System.Single m_LastSpeed`  

```csharp
private System.Single m_LastSpeed;
```

- `private System.Single m_SelectedSpeed`  

```csharp
private System.Single m_SelectedSpeed;
```

- `private System.Int32 m_LoadingCount`  

```csharp
private System.Int32 m_LoadingCount;
```

- `private System.Int32 m_StepCount`  

```csharp
private System.Int32 m_StepCount;
```

- `private System.Boolean m_IsLoading`  

```csharp
private System.Boolean m_IsLoading;
```

- `private Unity.Jobs.JobHandle m_WatchDeps`  

```csharp
private Unity.Jobs.JobHandle m_WatchDeps;
```

- `private System.Diagnostics.Stopwatch m_Stopwatch`  

```csharp
private System.Diagnostics.Stopwatch m_Stopwatch;
```

- `public static const System.Single PENDING_FRAMES_SPEED_FACTOR`  

```csharp
public static const System.Single PENDING_FRAMES_SPEED_FACTOR;
```

- `private static const System.Int32 LOADING_COUNT`  

```csharp
private static const System.Int32 LOADING_COUNT;
```

- `public static const System.String kLoadingTask`  

```csharp
public static const System.String kLoadingTask;
```


## Properties

- `public System.UInt32 frameIndex { get; private set }`  

```csharp
public System.UInt32 frameIndex { get; private set; }
```

- `public System.Single frameTime { get; private set }`  

```csharp
public System.Single frameTime { get; private set; }
```

- `public System.Single selectedSpeed { get; set }`  

```csharp
public System.Single selectedSpeed { get; set; }
```

- `public System.Single smoothSpeed { get; private set }`  

```csharp
public System.Single smoothSpeed { get; private set; }
```

- `public System.Single loadingProgress { get; private set }`  

```csharp
public System.Single loadingProgress { get; private set; }
```

- `public System.Single frameDuration { get; private set }`  

```csharp
public System.Single frameDuration { get; private set; }
```

- `public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set }`  

```csharp
public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set; }
```


## Constructors

- `public SimulationSystem()`  

```csharp
[Preserve]
	public SimulationSystem()
	{
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		selectedSpeed = 1f;
		performancePreference = SharedSettings.instance?.general.performancePreference ?? PerformancePreference.Balanced;
		m_Stopwatch = new Stopwatch();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_PathfindResultSystem = base.World.GetOrCreateSystemManaged<PathfindResultSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_WatchDeps.Complete();
		base.OnDestroy();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		selectedSpeed = 0f;
		loadingProgress = 0f;
		m_LoadingCount = ((purpose == Purpose.NewGame) ? 1024 : 0);
		m_IsLoading = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_StepCount != 0)
		{
			m_WatchDeps.Complete();
			frameDuration = (float)m_Stopwatch.ElapsedTicks / (float)(Stopwatch.Frequency * m_StepCount);
			m_Stopwatch.Reset();
			m_StepCount = 0;
		}
		else
		{
			frameDuration = 0f;
		}
		if (m_IsLoading)
		{
			if (loadingProgress != 1f)
			{
				UpdateLoadingProgress();
				return;
			}
			if (!GameManager.instance.isGameLoading)
			{
				m_IsLoading = false;
				GameplaySettings gameplaySettings = SharedSettings.instance?.gameplay;
				selectedSpeed = ((gameplaySettings != null && gameplaySettings.pausedAfterLoading) ? 0f : 1f);
			}
		}
		else if (GameManager.instance.isGameLoading)
		{
			selectedSpeed = 0f;
		}
		int num;
		if (selectedSpeed == 0f)
		{
			num = 0;
			smoothSpeed = 0f;
		}
		else
		{
			float deltaTime = UnityEngine.Time.deltaTime;
			float num2 = deltaTime * selectedSpeed;
			float num3 = 1f;
			if (m_PathfindResultSystem.pendingSimulationFrame < uint.MaxValue)
			{
				int num4 = (int)math.max(0u, m_PathfindResultSystem.pendingSimulationFrame - frameIndex - 1);
				num3 = math.min(1f, (float)num4 * (1f / 48f));
				num2 *= num3;
			}
			m_Timer += num2;
			num = (int)math.floor(m_Timer * 60f);
			num2 *= 60f;
			if (m_PathfindResultSystem.pendingSimulationFrame < uint.MaxValue)
			{
				int num5 = (int)math.max(0u, m_PathfindResultSystem.pendingSimulationFrame - frameIndex - 1);
				num = math.min(num, num5);
				num2 = math.min(num2, num5);
			}
			if (performancePreference != PerformancePreference.SimulationSpeed)
			{
				float currentElapsedTime = m_EndFrameBarrier.currentElapsedTime;
				float f = (m_EndFrameBarrier.lastElapsedTime - currentElapsedTime) / math.max(0.001f, frameDuration);
				int num6 = math.max(1, (performancePreference == PerformancePreference.FrameRate) ? Mathf.FloorToInt(f) : Mathf.CeilToInt(f));
				num = math.min(num, num6);
				num2 = math.min(num2, num6);
			}
			m_Timer = math.clamp(m_Timer - (float)num / 60f, 0f, 1f / 60f);
			int num7 = math.max(1, math.min(8, Mathf.RoundToInt(selectedSpeed * num3 * 2f)));
			num = math.clamp(num, 0, num7);
			num2 = math.clamp(num2, 0f, num7);
			float num8 = num2 / math.max(1E-06f, 60f * deltaTime);
			float y = math.lerp(num8, smoothSpeed, math.pow(0.5f, deltaTime));
			float y2 = smoothSpeed + selectedSpeed - m_LastSpeed;
			if (num8 > smoothSpeed)
			{
				smoothSpeed = math.max(math.min(num8, y2), y);
			}
			else
			{
				smoothSpeed = math.min(math.max(num8, y2), y);
			}
		}
		frameTime = m_Timer * 60f;
		m_LastSpeed = selectedSpeed;
		m_UpdateSystem.Update(SystemUpdatePhase.PreSimulation);
		if (num != 0)
		{
			m_StepCount = num;
			m_Stopwatch.Start();
			for (int i = 0; i < num; i++)
			{
				frameIndex++;
				if (m_ToolSystem.actionMode.IsEditor())
				{
					m_UpdateSystem.Update(SystemUpdatePhase.EditorSimulation, frameIndex, i);
				}
				if (m_ToolSystem.actionMode.IsGame())
				{
					m_UpdateSystem.Update(SystemUpdatePhase.GameSimulation, frameIndex, i);
				}
			}
			SimulationEndTimeJob jobData = new SimulationEndTimeJob
			{
				m_Stopwatch = GCHandle.Alloc(m_Stopwatch)
			};
			m_WatchDeps = jobData.Schedule(m_EndFrameBarrier.producerHandle);
		}
		m_UpdateSystem.Update(SystemUpdatePhase.PostSimulation);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		frameIndex = 0u;
		frameTime = 0f;
		m_Timer = 0f;
	}
```

- `private UpdateLoadingProgress() : System.Void`  

```csharp
private void UpdateLoadingProgress()
	{
		if (m_LoadingCount > 0)
		{
			m_UpdateSystem.Update(SystemUpdatePhase.PreSimulation);
			int num = 8;
			for (int i = 0; i < num; i++)
			{
				frameIndex++;
				m_UpdateSystem.Update(SystemUpdatePhase.LoadSimulation, frameIndex, i);
			}
			m_UpdateSystem.Update(SystemUpdatePhase.PostSimulation);
			m_LoadingCount -= num;
		}
		if (m_LoadingCount > 0)
		{
			loadingProgress = math.clamp(1f - (float)m_LoadingCount / 1024f, 0f, 0.99999f);
		}
		else
		{
			loadingProgress = 1f;
		}
	}
```


## Nested types

- `Game.Simulation.SimulationSystem+PerformancePreference`  
- `Game.Simulation.SimulationSystem+SimulationEndTimeJob`  

