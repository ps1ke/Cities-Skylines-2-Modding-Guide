# Game.Serialization.LifepathEntrySystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LifepathEntrySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Game.Serialization.LifepathEntrySystem+TypeHandle __TypeHandle;

    public LifepathEntrySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Game.Serialization.DeserializationBarrier m_DeserializationBarrier`  

```csharp
private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
```

- `private Game.Serialization.LifepathEntrySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.LifepathEntrySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LifepathEntrySystem()`  

```csharp
[Preserve]
	public LifepathEntrySystem()
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
		m_ChirpQuery = GetEntityQuery(ComponentType.ReadOnly<Chirp>(), ComponentType.ReadOnly<LifePathEvent>());
		m_DeserializationBarrier = base.World.GetOrCreateSystemManaged<DeserializationBarrier>();
		RequireForUpdate(m_ChirpQuery);
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
		FixLifepathChirpReferencesJob jobData = new FixLifepathChirpReferencesJob
		{
			m_EntityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ChirpType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Triggers_Chirp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EntryDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Triggers_LifePathEntry_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_DeserializationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ChirpQuery, base.Dependency);
		m_DeserializationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Serialization.LifepathEntrySystem+FixLifepathChirpReferencesJob`  
- `Game.Serialization.LifepathEntrySystem+TypeHandle`  

