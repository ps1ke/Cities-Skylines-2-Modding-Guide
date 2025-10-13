# Game.Debug.AvailabilityDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AvailabilityDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_AvailabilityGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private System.Collections.Generic.Dictionary<Game.Net.AvailableResource, Game.Debug.BaseDebugSystem+Option> m_AvailabilityOptions;
    private Game.Debug.AvailabilityDebugSystem+TypeHandle __TypeHandle;

    public AvailabilityDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AvailabilityGroup`  

```csharp
private Unity.Entities.EntityQuery m_AvailabilityGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private System.Collections.Generic.Dictionary<Game.Net.AvailableResource, Game.Debug.BaseDebugSystem+Option> m_AvailabilityOptions`  

```csharp
private System.Collections.Generic.Dictionary<Game.Net.AvailableResource, Game.Debug.BaseDebugSystem+Option> m_AvailabilityOptions;
```

- `private Game.Debug.AvailabilityDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.AvailabilityDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AvailabilityDebugSystem()`  

```csharp
[Preserve]
	public AvailabilityDebugSystem()
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
		m_AvailabilityGroup = GetEntityQuery(ComponentType.ReadOnly<ResourceAvailability>(), ComponentType.ReadOnly<EdgeGeometry>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_AvailabilityOptions = new Dictionary<AvailableResource, Option>();
		string[] names = Enum.GetNames(typeof(AvailableResource));
		Array values = Enum.GetValues(typeof(AvailableResource));
		for (int i = 0; i < names.Length; i++)
		{
			AvailableResource availableResource = (AvailableResource)values.GetValue(i);
			if (availableResource != AvailableResource.Count)
			{
				m_AvailabilityOptions.Add(availableResource, AddOption(names[i], i == 0));
			}
		}
		RequireForUpdate(m_AvailabilityGroup);
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
		foreach (KeyValuePair<AvailableResource, Option> item in m_AvailabilityOptions)
		{
			if (item.Value.enabled)
			{
				JobHandle dependencies;
				JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new AvailabilityGizmoJob
				{
					m_Resource = item.Key,
					m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_AvailabilityType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
				}, m_AvailabilityGroup, JobHandle.CombineDependencies(inputDeps, dependencies));
				m_GizmosSystem.AddGizmosBatcherWriter(jobHandle2);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
		}
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.AvailabilityDebugSystem+AvailabilityGizmoJob`  
- `Game.Debug.AvailabilityDebugSystem+TypeHandle`  

