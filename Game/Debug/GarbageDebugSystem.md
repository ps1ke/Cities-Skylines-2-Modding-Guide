# Game.Debug.GarbageDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_BuildingGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_AccumulatedOption;
    private Game.Debug.BaseDebugSystem+Option m_ProduceOption;
    private Game.Debug.GarbageDebugSystem+TypeHandle __TypeHandle;

    public GarbageDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_AccumulatedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AccumulatedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ProduceOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ProduceOption;
```

- `private Game.Debug.GarbageDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.GarbageDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GarbageDebugSystem()`  

```csharp
[Preserve]
	public GarbageDebugSystem()
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
		m_BuildingGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Objects.Transform>(),
				ComponentType.ReadOnly<GarbageProducer>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Hidden>()
			}
		});
		base.Enabled = false;
		m_AccumulatedOption = AddOption("Accumulated Garbage", defaultEnabled: true);
		m_ProduceOption = AddOption("Produce Garbage", defaultEnabled: true);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_BuildingGroup.IsEmptyIgnoreFilter)
		{
			JobHandle dependencies;
			GarbageGizmoJob jobData = new GarbageGizmoJob
			{
				m_GarbageProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ConsumptionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ConsumptionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AccumulatedOption = m_AccumulatedOption.enabled,
				m_ProduceOption = m_ProduceOption.enabled,
				m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies),
				m_GarbageParameterData = GetEntityQuery(ComponentType.ReadOnly<GarbageParameterData>()).GetSingleton<GarbageParameterData>()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_BuildingGroup, JobHandle.CombineDependencies(base.Dependency, dependencies));
			m_GizmosSystem.AddGizmosBatcherWriter(base.Dependency);
		}
	}
```


## Nested types

- `Game.Debug.GarbageDebugSystem+GarbageGizmoJob`  
- `Game.Debug.GarbageDebugSystem+TypeHandle`  

