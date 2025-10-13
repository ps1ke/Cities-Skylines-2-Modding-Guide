# Game.Debug.CollapseSFXDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CollapseSFXDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_BuildingEffectGroup;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Colossal.GizmosSystem m_GizmosSystem;

    public CollapseSFXDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingEffectGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingEffectGroup;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```


## Constructors

- `public CollapseSFXDebugSystem()`  

```csharp
[Preserve]
	public CollapseSFXDebugSystem()
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
		m_BuildingEffectGroup = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Objects.Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		RequireForUpdate(m_BuildingEffectGroup);
		base.Enabled = false;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new CollapseSfxCoverageGizmoJob
		{
			m_EntityType = GetEntityTypeHandle(),
			m_PreFabRefType = GetComponentTypeHandle<PrefabRef>(isReadOnly: true),
			m_TransformType = GetComponentTypeHandle<Game.Objects.Transform>(isReadOnly: true),
			m_EffectsBuffs = GetBufferLookup<Effect>(isReadOnly: true),
			m_BuildingConfigurationData = m_ConfigurationQuery.GetSingleton<BuildingConfigurationData>(),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
		}, m_BuildingEffectGroup, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return JobHandle.CombineDependencies(inputDeps, jobHandle);
	}
```


## Nested types

- `Game.Debug.CollapseSFXDebugSystem+CollapseSfxCoverageGizmoJob`  

