# Game.Debug.GroundWaterDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class GroundWaterDebugSystem : Game.GameSystemBase
{
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;

    public GroundWaterDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```


## Constructors

- `public GroundWaterDebugSystem()`  

```csharp
[Preserve]
	public GroundWaterDebugSystem()
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
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
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
		GroundWaterGizmoJob jobData = new GroundWaterGizmoJob
		{
			m_GroundWaterMap = m_GroundWaterSystem.GetMap(readOnly: true, out dependencies),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies2)
		};
		base.Dependency = jobData.Schedule(JobHandle.CombineDependencies(base.Dependency, dependencies2, dependencies));
		m_GroundWaterSystem.AddReader(base.Dependency);
		m_TerrainSystem.AddCPUHeightReader(base.Dependency);
		m_GizmosSystem.AddGizmosBatcherWriter(base.Dependency);
	}
```


## Nested types

- `Game.Debug.GroundWaterDebugSystem+GroundWaterGizmoJob`  

