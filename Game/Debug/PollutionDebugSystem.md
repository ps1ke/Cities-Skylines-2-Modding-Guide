# Game.Debug.PollutionDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class PollutionDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_GroundOption;
    private Game.Debug.BaseDebugSystem+Option m_AirOption;
    private Game.Debug.BaseDebugSystem+Option m_NoiseOption;

    public PollutionDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_GroundOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GroundOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_AirOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AirOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_NoiseOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_NoiseOption;
```


## Constructors

- `public PollutionDebugSystem()`  

```csharp
[Preserve]
	public PollutionDebugSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_GroundOption = AddOption("Ground pollution", defaultEnabled: true);
		m_AirOption = AddOption("Air pollution", defaultEnabled: true);
		m_NoiseOption = AddOption("Noise pollution", defaultEnabled: true);
		base.Enabled = false;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle dependencies4;
		JobHandle jobHandle = new PollutionGizmoJob
		{
			m_PollutionMap = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies),
			m_AirPollutionMap = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies2),
			m_NoisePollutionMap = m_NoisePollutionSystem.GetMap(readOnly: true, out dependencies3),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies4),
			m_AirOption = m_AirOption.enabled,
			m_GroundOption = m_GroundOption.enabled,
			m_NoiseOption = m_NoiseOption.enabled,
			m_BaseHeight = m_ClimateSystem.temperatureBaseHeight
		}.Schedule(JobHandle.CombineDependencies(dependencies2, dependencies3, JobHandle.CombineDependencies(inputDeps, dependencies4, dependencies)));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		m_GroundPollutionSystem.AddReader(jobHandle);
		m_AirPollutionSystem.AddReader(jobHandle);
		m_NoisePollutionSystem.AddReader(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.PollutionDebugSystem+PollutionGizmoJob`  

