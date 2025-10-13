# Game.Debug.SoilWaterDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class SoilWaterDebugSystem : Game.GameSystemBase
{
    private Game.Simulation.SoilWaterSystem m_SoilWaterSystem;
    private Colossal.GizmosSystem m_GizmosSystem;

    public SoilWaterDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SoilWaterSystem m_SoilWaterSystem`  

```csharp
private Game.Simulation.SoilWaterSystem m_SoilWaterSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```


## Constructors

- `public SoilWaterDebugSystem()`  

```csharp
[Preserve]
	public SoilWaterDebugSystem()
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
		m_SoilWaterSystem = base.World.GetOrCreateSystemManaged<SoilWaterSystem>();
		base.Enabled = false;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependencies;
		JobHandle dependencies2;
		SoilWaterGizmoJob jobData = new SoilWaterGizmoJob
		{
			m_SoilWaterMap = m_SoilWaterSystem.GetMap(readOnly: true, out dependencies),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies2)
		};
		base.Dependency = jobData.Schedule(JobHandle.CombineDependencies(base.Dependency, dependencies2, dependencies));
		m_SoilWaterSystem.AddReader(base.Dependency);
		m_GizmosSystem.AddGizmosBatcherWriter(base.Dependency);
	}
```


## Nested types

- `Game.Debug.SoilWaterDebugSystem+SoilWaterGizmoJob`  

