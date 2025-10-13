# Game.Simulation.CommercialSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CommercialSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CommercialCompanyPrefabGroup;
    private Unity.Entities.EntityQuery m_PropertyLessCompanyGroup;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Collections.NativeArray<System.UInt32> m_LastSpawnedCommercialFrame;
    private Game.Simulation.CommercialSpawnSystem+TypeHandle __TypeHandle;

    public CommercialSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CommercialCompanyPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_CommercialCompanyPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_PropertyLessCompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_PropertyLessCompanyGroup;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Collections.NativeArray<System.UInt32> m_LastSpawnedCommercialFrame`  

```csharp
private Unity.Collections.NativeArray<System.UInt32> m_LastSpawnedCommercialFrame;
```

- `private Game.Simulation.CommercialSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CommercialSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CommercialSpawnSystem()`  

```csharp
[Preserve]
	public CommercialSpawnSystem()
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
		m_CommercialDemandSystem = base.World.GetOrCreateSystemManaged<CommercialDemandSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CommercialCompanyPrefabGroup = GetEntityQuery(ComponentType.ReadOnly<ArchetypeData>(), ComponentType.ReadOnly<CommercialCompanyData>(), ComponentType.ReadOnly<IndustrialProcessData>());
		m_DemandParameterQuery = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		m_PropertyLessCompanyGroup = GetEntityQuery(ComponentType.ReadOnly<CommercialCompany>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<PropertyRenter>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_LastSpawnedCommercialFrame = new NativeArray<uint>(EconomyUtils.ResourceCount, Allocator.Persistent);
		RequireForUpdate(m_CommercialCompanyPrefabGroup);
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
		base.OnDestroy();
		m_LastSpawnedCommercialFrame.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_SimulationSystem.frameIndex / 16 % 8 == 1 && m_CommercialDemandSystem.companyDemand > 0)
		{
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			JobHandle deps;
			SpawnCompanyJob jobData = new SpawnCompanyJob
			{
				m_CompanyPrefabs = m_CommercialCompanyPrefabGroup.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_PropertyLessCompanies = m_PropertyLessCompanyGroup.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
				m_Archetypes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ArchetypeData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Processes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceDemands = m_CommercialDemandSystem.GetResourceDemands(out deps),
				m_Random = RandomSeed.Next().GetRandom((int)m_SimulationSystem.frameIndex),
				m_FrameIndex = m_SimulationSystem.frameIndex,
				m_LastSpawnedCommercialFrame = m_LastSpawnedCommercialFrame,
				m_DemandParameterData = m_DemandParameterQuery.GetSingleton<DemandParameterData>(),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, outJobHandle, outJobHandle2, deps));
			m_CommercialDemandSystem.AddReader(base.Dependency);
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.CommercialSpawnSystem+SpawnCompanyJob`  
- `Game.Simulation.CommercialSpawnSystem+TypeHandle`  

