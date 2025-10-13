# Game.Tutorials.TutorialHealthProblemActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialHealthProblemActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Unity.Entities.EntityQuery m_TutorialQuery;
    private Unity.Entities.EntityQuery m_HealthProblemQuery;
    private Unity.Entities.EntityQuery m_MedicalClinicQuery;
    private Unity.Entities.EntityQuery m_MedicalClinicUnlockedQuery;
    private Unity.Entities.EntityQuery m_CemeteryQuery;
    private Unity.Entities.EntityQuery m_CemeteryUnlockedQuery;
    private Game.Tutorials.TutorialHealthProblemActivationSystem+TypeHandle __TypeHandle;

    public TutorialHealthProblemActivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```

- `private Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialQuery;
```

- `private Unity.Entities.EntityQuery m_HealthProblemQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthProblemQuery;
```

- `private Unity.Entities.EntityQuery m_MedicalClinicQuery`  

```csharp
private Unity.Entities.EntityQuery m_MedicalClinicQuery;
```

- `private Unity.Entities.EntityQuery m_MedicalClinicUnlockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_MedicalClinicUnlockedQuery;
```

- `private Unity.Entities.EntityQuery m_CemeteryQuery`  

```csharp
private Unity.Entities.EntityQuery m_CemeteryQuery;
```

- `private Unity.Entities.EntityQuery m_CemeteryUnlockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CemeteryUnlockedQuery;
```

- `private Game.Tutorials.TutorialHealthProblemActivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialHealthProblemActivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialHealthProblemActivationSystem()`  

```csharp
[Preserve]
	public TutorialHealthProblemActivationSystem()
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
		m_BarrierSystem = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_TutorialQuery = GetEntityQuery(ComponentType.ReadOnly<HealthProblemActivationData>(), ComponentType.Exclude<TutorialActivated>(), ComponentType.Exclude<TutorialCompleted>());
		m_HealthProblemQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<HealthProblem>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_MedicalClinicQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Buildings.Hospital>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_MedicalClinicUnlockedQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<HospitalData>(), ComponentType.ReadOnly<BuildingData>(), ComponentType.Exclude<Locked>());
		m_CemeteryQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Buildings.DeathcareFacility>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CemeteryUnlockedQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<DeathcareFacilityData>(), ComponentType.ReadOnly<BuildingData>(), ComponentType.Exclude<Locked>());
		RequireForUpdate(m_HealthProblemQuery);
		RequireForUpdate(m_TutorialQuery);
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
		bool flag = m_MedicalClinicQuery.IsEmptyIgnoreFilter && !m_MedicalClinicUnlockedQuery.IsEmpty;
		bool flag2 = m_CemeteryQuery.IsEmptyIgnoreFilter && !m_CemeteryUnlockedQuery.IsEmpty;
		if (flag || flag2)
		{
			JobHandle outJobHandle;
			CheckProblemsJob jobData = new CheckProblemsJob
			{
				m_EntityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ActivationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tutorials_HealthProblemActivationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HealthProblemType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HealthProblemChunks = m_HealthProblemQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
				m_NoHospital = flag,
				m_NoCemetery = flag2,
				m_Writer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_TutorialQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
			jobData.m_HealthProblemChunks.Dispose(base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialHealthProblemActivationSystem+CheckProblemsJob`  
- `Game.Tutorials.TutorialHealthProblemActivationSystem+TypeHandle`  

