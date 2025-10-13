# Game.Simulation.ResourceExporterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceExporterSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ExporterQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Unity.Collections.NativeQueue<Game.Simulation.ResourceExporterSystem+ExportEvent> m_ExportQueue;
    private Game.Simulation.ResourceExporterSystem+TypeHandle __TypeHandle;

    public ResourceExporterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ExporterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExporterQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.ResourceExporterSystem+ExportEvent> m_ExportQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.ResourceExporterSystem+ExportEvent> m_ExportQueue;
```

- `private Game.Simulation.ResourceExporterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResourceExporterSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResourceExporterSystem()`  

```csharp
[Preserve]
	public ResourceExporterSystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_ExporterQuery = GetEntityQuery(ComponentType.ReadOnly<ResourceExporter>(), ComponentType.ReadOnly<TaxPayer>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<Game.Economy.Resources>(), ComponentType.Exclude<ResourceBuyer>(), ComponentType.ReadWrite<TripNeeded>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_ExportQueue = new NativeQueue<ExportEvent>(Allocator.Persistent);
		RequireForUpdate(m_ExporterQuery);
		RequireForUpdate(m_EconomyParameterQuery);
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
		m_ExportQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		ExportJob jobData = new ExportJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ResourceExporterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_ResourceExporter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TripType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PathInformation = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageCompanies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExportQueue = m_ExportQueue.AsParallelWriter(),
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 64).AsParallelWriter(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ExporterQuery, base.Dependency);
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_PathfindSetupSystem.AddQueueWriter(base.Dependency);
		HandleExportsJob jobData2 = new HandleExportsJob
		{
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RW_BufferLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Storages = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TradeCosts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_TradeCost_RW_BufferLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_ExportQueue = m_ExportQueue
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
		m_TaxSystem.AddReader(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.ResourceExporterSystem+ExportJob`  
- `Game.Simulation.ResourceExporterSystem+ExportEvent`  
- `Game.Simulation.ResourceExporterSystem+HandleExportsJob`  
- `Game.Simulation.ResourceExporterSystem+TypeHandle`  

