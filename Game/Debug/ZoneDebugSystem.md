# Game.Debug.ZoneDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_BlockGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Prefabs.ZoneSystem m_ZoneSystem;
    private Game.Debug.BaseDebugSystem+Option m_PivotOption;
    private Game.Debug.BaseDebugSystem+Option m_GridOption;
    private Game.Debug.BaseDebugSystem+Option m_LotOption;
    private Game.Debug.ZoneDebugSystem+TypeHandle __TypeHandle;

    public ZoneDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BlockGroup`  

```csharp
private Unity.Entities.EntityQuery m_BlockGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Prefabs.ZoneSystem m_ZoneSystem`  

```csharp
private Game.Prefabs.ZoneSystem m_ZoneSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_PivotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PivotOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_GridOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GridOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LotOption;
```

- `private Game.Debug.ZoneDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.ZoneDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ZoneDebugSystem()`  

```csharp
[Preserve]
	public ZoneDebugSystem()
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
		m_ZoneSystem = base.World.GetOrCreateSystemManaged<ZoneSystem>();
		m_BlockGroup = GetEntityQuery(ComponentType.ReadOnly<Block>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Hidden>());
		m_PivotOption = AddOption("Draw Pivots", defaultEnabled: false);
		m_GridOption = AddOption("Draw Grids", defaultEnabled: true);
		m_LotOption = AddOption("Vacant Lots", defaultEnabled: true);
		RequireForUpdate(m_BlockGroup);
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
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new BlockGizmoJob
		{
			m_PivotOption = m_PivotOption.enabled,
			m_GridOption = m_GridOption.enabled,
			m_LotOption = m_LotOption.enabled,
			m_ZonePrefabs = m_ZoneSystem.GetPrefabs(),
			m_BlockType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_Block_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_VacantLotType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Zones_VacantLot_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ErrorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Error_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
		}, m_BlockGroup, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_ZoneSystem.AddPrefabsReader(jobHandle);
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.ZoneDebugSystem+BlockGizmoJob`  
- `Game.Debug.ZoneDebugSystem+TypeHandle`  

