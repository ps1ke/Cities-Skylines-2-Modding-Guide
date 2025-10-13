# Game.Objects.DamageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DamageSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Game.Objects.DamageSystem+TypeHandle __TypeHandle;

    public DamageSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Game.Objects.DamageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.DamageSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DamageSystem()`  

```csharp
[Preserve]
	public DamageSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier2>();
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<Event>(), ComponentType.ReadOnly<Damage>());
		RequireForUpdate(m_EventQuery);
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
		NativeList<ArchetypeChunk> chunks = m_EventQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new DamageObjectsJob
		{
			m_Chunks = chunks,
			m_DamageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Damage_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RW_ComponentLookup, ref base.CheckedStateRef),
			m_DamagedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Damaged_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		chunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Objects.DamageSystem+DamageObjectsJob`  
- `Game.Objects.DamageSystem+TypeHandle`  

