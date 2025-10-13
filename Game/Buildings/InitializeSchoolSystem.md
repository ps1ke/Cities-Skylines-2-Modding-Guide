# Game.Buildings.InitializeSchoolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSchoolSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedSchoolQuery;
    private Unity.Entities.EntityQuery m_StudentQuery;
    private Game.Buildings.InitializeSchoolSystem+TypeHandle __TypeHandle;

    public InitializeSchoolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedSchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedSchoolQuery;
```

- `private Unity.Entities.EntityQuery m_StudentQuery`  

```csharp
private Unity.Entities.EntityQuery m_StudentQuery;
```

- `private Game.Buildings.InitializeSchoolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.InitializeSchoolSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeSchoolSystem()`  

```csharp
[Preserve]
	public InitializeSchoolSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_CreatedSchoolQuery = GetEntityQuery(ComponentType.ReadOnly<School>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Updated>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_StudentQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Citizens.Student>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_CreatedSchoolQuery);
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
		NativeArray<PrefabRef> nativeArray = m_CreatedSchoolQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
		NativeArray<int> newLevels = new NativeArray<int>(4, Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (base.EntityManager.TryGetComponent<SchoolData>(nativeArray[i].m_Prefab, out var component) && component.m_EducationLevel >= 1 && component.m_EducationLevel <= 4)
			{
				newLevels[component.m_EducationLevel - 1] = 1;
			}
		}
		nativeArray.Dispose();
		InitializeSchoolsJob jobData = new InitializeSchoolsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_StudentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Schools = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_School_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NewLevels = newLevels,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_StudentQuery, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Buildings.InitializeSchoolSystem+InitializeSchoolsJob`  
- `Game.Buildings.InitializeSchoolSystem+TypeHandle`  

