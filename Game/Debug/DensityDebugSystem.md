# Game.Debug.DensityDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DensityDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.DensityDebugSystem+TypeHandle __TypeHandle;

    public DensityDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.DensityDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.DensityDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DensityDebugSystem()`  

```csharp
[Preserve]
	public DensityDebugSystem()
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
		m_EdgeGroup = GetEntityQuery(ComponentType.ReadOnly<Density>(), ComponentType.ReadOnly<EdgeGeometry>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		base.Enabled = false;
		RequireForUpdate(m_EdgeGroup);
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
		inputDeps = JobChunkExtensions.ScheduleParallel(new DensityGizmoJob
		{
			m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DensityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Density_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out var dependencies)
		}, m_EdgeGroup, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(inputDeps);
		return inputDeps;
	}
```


## Nested types

- `Game.Debug.DensityDebugSystem+DensityGizmoJob`  
- `Game.Debug.DensityDebugSystem+TypeHandle`  

