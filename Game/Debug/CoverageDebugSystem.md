# Game.Debug.CoverageDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CoverageDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_CoverageGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private System.Collections.Generic.Dictionary<Game.Net.CoverageService, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions;
    private Game.Debug.CoverageDebugSystem+TypeHandle __TypeHandle;

    public CoverageDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CoverageGroup`  

```csharp
private Unity.Entities.EntityQuery m_CoverageGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private System.Collections.Generic.Dictionary<Game.Net.CoverageService, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions`  

```csharp
private System.Collections.Generic.Dictionary<Game.Net.CoverageService, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions;
```

- `private Game.Debug.CoverageDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.CoverageDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CoverageDebugSystem()`  

```csharp
[Preserve]
	public CoverageDebugSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_CoverageGroup = GetEntityQuery(ComponentType.ReadOnly<ServiceCoverage>(), ComponentType.ReadOnly<EdgeGeometry>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_CoverageOptions = new Dictionary<CoverageService, Option>();
		string[] names = Enum.GetNames(typeof(CoverageService));
		Array values = Enum.GetValues(typeof(CoverageService));
		for (int i = 0; i < names.Length; i++)
		{
			CoverageService coverageService = (CoverageService)values.GetValue(i);
			if (coverageService != CoverageService.Count)
			{
				m_CoverageOptions.Add(coverageService, AddOption(names[i], i == 0));
			}
		}
		RequireForUpdate(m_CoverageGroup);
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

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		JobHandle jobHandle = inputDeps;
		foreach (KeyValuePair<CoverageService, Option> item in m_CoverageOptions)
		{
			if (item.Value.enabled)
			{
				JobHandle dependencies;
				JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new CoverageGizmoJob
				{
					m_Service = item.Key,
					m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CoverageType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
				}, m_CoverageGroup, JobHandle.CombineDependencies(inputDeps, dependencies));
				m_GizmosSystem.AddGizmosBatcherWriter(jobHandle2);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
		}
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.CoverageDebugSystem+CoverageGizmoJob`  
- `Game.Debug.CoverageDebugSystem+TypeHandle`  

