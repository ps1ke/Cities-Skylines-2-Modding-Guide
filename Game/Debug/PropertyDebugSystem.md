# Game.Debug.PropertyDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PropertyDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_PropertyQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_ResidentialAvailableOption;
    private Game.Debug.BaseDebugSystem+Option m_ResidentialCrimeOption;
    private Game.Debug.BaseDebugSystem+Option m_CrimeOption;
    private Game.Debug.PropertyDebugSystem+TypeHandle __TypeHandle;

    public PropertyDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PropertyQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_ResidentialAvailableOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ResidentialAvailableOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ResidentialCrimeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ResidentialCrimeOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CrimeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CrimeOption;
```

- `private Game.Debug.PropertyDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.PropertyDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PropertyDebugSystem()`  

```csharp
[Preserve]
	public PropertyDebugSystem()
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
		m_PropertyQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Building>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<CrimeProducer>(),
				ComponentType.ReadOnly<Renter>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Hidden>()
			}
		});
		m_ResidentialCrimeOption = AddOption("Residential Crime", defaultEnabled: false);
		m_ResidentialAvailableOption = AddOption("Residential Available", defaultEnabled: false);
		m_CrimeOption = AddOption("Crime Accumulation", defaultEnabled: true);
		RequireForUpdate(m_PropertyQuery);
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
		JobHandle dependencies;
		PropertyGizmoJob jobData = new PropertyGizmoJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CrimeProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RenterBufType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CrimeOption = m_CrimeOption.enabled,
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies),
			m_ResidentialAvailableOption = m_ResidentialAvailableOption.enabled,
			m_ResidentialCrimeOption = m_ResidentialCrimeOption.enabled
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_PropertyQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(base.Dependency);
		return base.Dependency;
	}
```


## Nested types

- `Game.Debug.PropertyDebugSystem+PropertyGizmoJob`  
- `Game.Debug.PropertyDebugSystem+TypeHandle`  

