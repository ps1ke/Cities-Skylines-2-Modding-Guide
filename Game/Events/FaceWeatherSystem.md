# Game.Events.FaceWeatherSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FaceWeatherSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_FaceWeatherQuery;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Game.Events.FaceWeatherSystem+TypeHandle __TypeHandle;

    public FaceWeatherSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_FaceWeatherQuery`  

```csharp
private Unity.Entities.EntityQuery m_FaceWeatherQuery;
```

- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_JournalDataArchetype;
```

- `private Game.Events.FaceWeatherSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.FaceWeatherSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FaceWeatherSystem()`  

```csharp
[Preserve]
	public FaceWeatherSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_FaceWeatherQuery = GetEntityQuery(ComponentType.ReadOnly<FaceWeather>(), ComponentType.ReadOnly<Game.Common.Event>());
		m_JournalDataArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<AddEventJournalData>(), ComponentType.ReadWrite<Game.Common.Event>());
		RequireForUpdate(m_FaceWeatherQuery);
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_FaceWeatherQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new FaceWeatherJob
		{
			m_Chunks = chunks,
			m_FaceWeatherType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_FaceWeather_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FacingWeatherData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_FacingWeather_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TargetElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Events_TargetElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_JournalDataArchetype = m_JournalDataArchetype,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		chunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Events.FaceWeatherSystem+FaceWeatherJob`  
- `Game.Events.FaceWeatherSystem+TypeHandle`  

