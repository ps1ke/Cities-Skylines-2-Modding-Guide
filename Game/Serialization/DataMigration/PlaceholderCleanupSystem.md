# Game.Serialization.DataMigration.PlaceholderCleanupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PlaceholderCleanupSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Unity.Entities.EntityQuery m_Query;
    private Unity.Entities.ComponentTypeSet m_ComponentSet;
    private Game.Serialization.DataMigration.PlaceholderCleanupSystem+TypeHandle __TypeHandle;

    public PlaceholderCleanupSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Serialization.DeserializationBarrier m_DeserializationBarrier`  

```csharp
private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Unity.Entities.ComponentTypeSet m_ComponentSet`  

```csharp
private Unity.Entities.ComponentTypeSet m_ComponentSet;
```

- `private Game.Serialization.DataMigration.PlaceholderCleanupSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.PlaceholderCleanupSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PlaceholderCleanupSystem()`  

```csharp
[Preserve]
	public PlaceholderCleanupSystem()
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
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_DeserializationBarrier = base.World.GetOrCreateSystemManaged<DeserializationBarrier>();
		m_Query = GetEntityQuery(ComponentType.ReadOnly<Placeholder>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Renter>());
		m_ComponentSet = new ComponentTypeSet(new ComponentType[7]
		{
			ComponentType.ReadWrite<Renter>(),
			ComponentType.ReadWrite<PropertyToBeOnMarket>(),
			ComponentType.ReadWrite<PropertyOnMarket>(),
			ComponentType.ReadWrite<ElectricityConsumer>(),
			ComponentType.ReadWrite<WaterConsumer>(),
			ComponentType.ReadWrite<GarbageProducer>(),
			ComponentType.ReadWrite<TelecomConsumer>()
		});
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
		if (!(m_LoadGameSystem.context.version >= Version.placeholderCleanup) && !m_Query.IsEmptyIgnoreFilter)
		{
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new PlaceholderCleanupJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_IconElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Notifications_IconElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_ComponentSet = m_ComponentSet,
				m_CommandBuffer = m_DeserializationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_Query, base.Dependency);
			m_DeserializationBarrier.AddJobHandleForProducer(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Serialization.DataMigration.PlaceholderCleanupSystem+PlaceholderCleanupJob`  
- `Game.Serialization.DataMigration.PlaceholderCleanupSystem+TypeHandle`  

