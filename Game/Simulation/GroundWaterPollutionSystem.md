# Game.Simulation.GroundWaterPollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class GroundWaterPollutionSystem : Game.GameSystemBase
{
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;

    public GroundWaterPollutionSystem();

    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```


## Constructors

- `public GroundWaterPollutionSystem()`  

```csharp
[Preserve]
	public GroundWaterPollutionSystem()
	{
	}
```


## Methods

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 128;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 64;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		PolluteGroundWaterJob jobData = new PolluteGroundWaterJob
		{
			m_GroundWaterMap = m_GroundWaterSystem.GetMap(readOnly: false, out dependencies),
			m_PollutionMap = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies2)
		};
		base.Dependency = jobData.Schedule(JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2));
		m_GroundWaterSystem.AddWriter(base.Dependency);
		m_GroundPollutionSystem.AddReader(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.GroundWaterPollutionSystem+PolluteGroundWaterJob`  

