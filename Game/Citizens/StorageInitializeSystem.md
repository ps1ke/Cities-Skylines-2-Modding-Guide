# Game.Citizens.StorageInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StorageInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedStorageGroup;
    private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Citizens.StorageInitializeSystem+TypeHandle __TypeHandle;

    public StorageInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedStorageGroup`  

```csharp
private Unity.Entities.EntityQuery m_CreatedStorageGroup;
```

- `private Game.Common.ModificationBarrier5 m_EndFrameBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Citizens.StorageInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.StorageInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public StorageInitializeSystem()`  

```csharp
[Preserve]
	public StorageInitializeSystem()
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
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_CreatedStorageGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.ReadOnly<Created>());
		RequireForUpdate(m_CreatedStorageGroup);
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
		InitializeStorageJob jobData = new InitializeStorageJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompanyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Brands = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_CompanyBrandElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedStorageGroup, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Citizens.StorageInitializeSystem+InitializeStorageJob`  
- `Game.Citizens.StorageInitializeSystem+TypeHandle`  

