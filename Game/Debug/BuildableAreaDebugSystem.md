# Game.Debug.BuildableAreaDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildableAreaDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_StrictOption;
    private Colossal.Collections.NativeAccumulator<Colossal.Collections.AverageFloat> m_BuildableArea;
    private System.Single m_LastBuildableArea;
    private Game.Debug.BuildableAreaDebugSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1438325908_0;

    public System.Single buildableArea { get; }

    public BuildableAreaDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_StrictOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StrictOption;
```

- `private Colossal.Collections.NativeAccumulator<Colossal.Collections.AverageFloat> m_BuildableArea`  

```csharp
private Colossal.Collections.NativeAccumulator<Colossal.Collections.AverageFloat> m_BuildableArea;
```

- `private System.Single m_LastBuildableArea`  

```csharp
private System.Single m_LastBuildableArea;
```

- `private Game.Debug.BuildableAreaDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.BuildableAreaDebugSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1438325908_0`  

```csharp
private Unity.Entities.EntityQuery __query_1438325908_0;
```


## Properties

- `public System.Single buildableArea { get }`  

```csharp
public System.Single buildableArea { get; }
```


## Constructors

- `public BuildableAreaDebugSystem()`  

```csharp
[Preserve]
	public BuildableAreaDebugSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<AreasConfigurationData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1438325908_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		RequireForUpdate<AreasConfigurationData>();
		m_BuildableArea = new NativeAccumulator<AverageFloat>(Allocator.Persistent);
		m_StrictOption = AddOption("Strict", defaultEnabled: false);
		base.Enabled = false;
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_BuildableArea.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		m_LastBuildableArea = m_BuildableArea.GetResult().average;
		m_BuildableArea.Clear();
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle deps;
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(new BuildableAreaGizmoJob
		{
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies),
			m_NaturalResourceData = m_NaturalResourceSystem.GetData(readOnly: true, out dependencies2),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_BuildableLandMaxSlope = (m_StrictOption.enabled ? new Bounds1(0f, 0.3f) : __query_1438325908_0.GetSingleton<AreasConfigurationData>().m_BuildableLandMaxSlope),
			m_Average = m_BuildableArea.AsParallelWriter()
		}, NaturalResourceSystem.kTextureSize * NaturalResourceSystem.kTextureSize, NaturalResourceSystem.kTextureSize, JobUtils.CombineDependencies(inputDeps, dependencies, dependencies2, deps));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
		m_NaturalResourceSystem.AddReader(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.BuildableAreaDebugSystem+BuildableAreaGizmoJob`  
- `Game.Debug.BuildableAreaDebugSystem+TypeHandle`  

