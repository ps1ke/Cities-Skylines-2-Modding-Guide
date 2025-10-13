# Game.Debug.WindDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class WindDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Colossal.GizmosSystem m_GizmosSystem;

    public WindDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  

```csharp
private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```


## Constructors

- `public WindDebugSystem()`  

```csharp
[Preserve]
	public WindDebugSystem()
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
		m_WindSimulationSystem = base.World.GetOrCreateSystemManaged<WindSimulationSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		base.Enabled = false;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		TerrainHeightData data = m_TerrainSystem.GetHeightData();
		float2 terrainRange = new float2(TerrainUtils.ToWorldSpace(ref data, 0f), TerrainUtils.ToWorldSpace(ref data, 65535f));
		JobHandle deps;
		JobHandle dependencies;
		JobHandle jobHandle = new WindGizmoJob
		{
			m_WindMap = m_WindSimulationSystem.GetCells(out deps),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies),
			m_TerrainRange = terrainRange
		}.Schedule(JobHandle.CombineDependencies(inputDeps, dependencies, deps));
		m_WindSimulationSystem.AddReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.WindDebugSystem+WindGizmoJob`  

