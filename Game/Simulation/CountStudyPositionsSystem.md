# Game.Simulation.CountStudyPositionsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CountStudyPositionsSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_SchoolQuery;
    private Unity.Collections.NativeArray<System.Int32> m_StudyPositionByEducation;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Game.Simulation.CountStudyPositionsSystem+TypeHandle __TypeHandle;

    public CountStudyPositionsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetStudyPositionsByEducation(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_SchoolQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_StudyPositionByEducation`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_StudyPositionByEducation;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Game.Simulation.CountStudyPositionsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CountStudyPositionsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CountStudyPositionsSystem()`  

```csharp
[Preserve]
	public CountStudyPositionsSystem()
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

- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public void AddReader(JobHandle reader)
	{
		m_ReadDependencies = JobHandle.CombineDependencies(m_ReadDependencies, reader);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStudyPositionsByEducation(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetStudyPositionsByEducation(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_StudyPositionByEducation;
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
		m_SchoolQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Buildings.School>(), ComponentType.ReadOnly<Student>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>());
		m_StudyPositionByEducation = new NativeArray<int>(5, Allocator.Persistent);
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
		m_StudyPositionByEducation.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle outJobHandle;
		CountStudyPositionsJob jobData = new CountStudyPositionsJob
		{
			m_SchoolChunks = m_SchoolQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_StudentType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Student_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_OutsideConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SchoolDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SchoolData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StudyPositionByEducation = m_StudyPositionByEducation
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, m_ReadDependencies, outJobHandle));
		m_WriteDependencies = base.Dependency;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		for (int i = 0; i < 5; i++)
		{
			m_StudyPositionByEducation[i] = 0;
		}
	}
```


## Nested types

- `Game.Simulation.CountStudyPositionsSystem+CountStudyPositionsJob`  
- `Game.Simulation.CountStudyPositionsSystem+TypeHandle`  

