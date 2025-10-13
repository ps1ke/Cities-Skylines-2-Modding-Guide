# Game.Simulation.IndustrialSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IndustrialSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_StorageCompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_ExtractorQuery;
    private Unity.Entities.EntityQuery m_ExtractorCompanyQuery;
    private Unity.Entities.EntityQuery m_ExistingIndustrialQuery;
    private Unity.Entities.EntityQuery m_ExistingExtractorQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.IndustrialSpawnSystem+TypeHandle __TypeHandle;

    public IndustrialSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_StorageCompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_StorageCompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorCompanyQuery;
```

- `private Unity.Entities.EntityQuery m_ExistingIndustrialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExistingIndustrialQuery;
```

- `private Unity.Entities.EntityQuery m_ExistingExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExistingExtractorQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.IndustrialSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.IndustrialSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public IndustrialSpawnSystem()`  

```csharp
[Preserve]
	public IndustrialSpawnSystem()
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
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_IndustrialDemandSystem = base.World.GetOrCreateSystemManaged<IndustrialDemandSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_IndustrialCompanyPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ArchetypeData>(), ComponentType.ReadOnly<IndustrialCompanyData>(), ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.Exclude<StorageCompanyData>());
		m_StorageCompanyPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ArchetypeData>(), ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.ReadOnly<StorageCompanyData>());
		m_ExtractorQuery = GetEntityQuery(ComponentType.ReadOnly<ExtractorProperty>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>());
		m_ExtractorCompanyQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.ExtractorCompany>(), ComponentType.Exclude<Deleted>());
		m_ExistingIndustrialQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialCompany>(), ComponentType.Exclude<Game.Companies.ExtractorCompany>(), ComponentType.Exclude<Game.Companies.StorageCompany>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<PropertyRenter>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ExistingExtractorQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.ExtractorCompany>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<PropertyRenter>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_IndustrialCompanyPrefabQuery);
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
		if (m_SimulationSystem.frameIndex / 16 % 8 == 2 && m_IndustrialDemandSystem.industrialCompanyDemand + m_IndustrialDemandSystem.storageCompanyDemand + m_IndustrialDemandSystem.officeCompanyDemand > 0)
		{
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			JobHandle outJobHandle3;
			JobHandle outJobHandle4;
			JobHandle deps;
			JobHandle deps2;
			CheckSpawnJob jobData = new CheckSpawnJob
			{
				m_ArchetypeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ArchetypeData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ProcessType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_IndustrialChunks = m_IndustrialCompanyPrefabQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_StorageChunks = m_StorageCompanyPrefabQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
				m_ExistingExtractorPrefabs = m_ExistingExtractorQuery.ToComponentDataListAsync<PrefabRef>(base.World.UpdateAllocator.ToAllocator, out outJobHandle3),
				m_ExistingIndustrialPrefabs = m_ExistingIndustrialQuery.ToComponentDataListAsync<PrefabRef>(base.World.UpdateAllocator.ToAllocator, out outJobHandle4),
				m_ProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Populations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceDemands = m_IndustrialDemandSystem.GetResourceDemands(out deps),
				m_WarehouseDemands = m_IndustrialDemandSystem.GetStorageCompanyDemands(out deps2),
				m_City = m_CitySystem.City,
				m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
				m_SimulationFrame = m_SimulationSystem.frameIndex,
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, outJobHandle, outJobHandle2, outJobHandle3, outJobHandle4, deps, deps2));
			m_ResourceSystem.AddPrefabsReader(base.Dependency);
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.IndustrialSpawnSystem+CheckSpawnJob`  
- `Game.Simulation.IndustrialSpawnSystem+TypeHandle`  

