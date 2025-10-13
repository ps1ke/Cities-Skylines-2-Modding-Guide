# Game.Debug.TerrainAttractivenessDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TerrainAttractivenessDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Colossal.GizmosSystem m_GizmosSystem;

    public TerrainAttractivenessDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```


## Constructors

- `public TerrainAttractivenessDebugSystem()`  

```csharp
[Preserve]
	public TerrainAttractivenessDebugSystem()
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
		m_TerrainAttractivenessSystem = base.World.GetOrCreateSystemManaged<TerrainAttractivenessSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_ParameterQuery = GetEntityQuery(ComponentType.ReadOnly<AttractivenessParameterData>());
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
		JobHandle jobHandle = IJobExtensions.Schedule(new TerrainAttractivenessGizmoJob
		{
			m_Map = m_TerrainAttractivenessSystem.GetData(readOnly: true, out dependencies),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies2),
			m_HeightData = m_TerrainSystem.GetHeightData(),
			m_Parameters = m_ParameterQuery.GetSingleton<AttractivenessParameterData>()
		}, JobHandle.CombineDependencies(inputDeps, dependencies2, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		m_TerrainAttractivenessSystem.AddReader(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.TerrainAttractivenessDebugSystem+TerrainAttractivenessGizmoJob`  

