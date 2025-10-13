# Game.Serialization.DataMigration.QuantityObjectMissingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class QuantityObjectMissingSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.DataMigration.QuantityObjectMissingSystem+TypeHandle __TypeHandle;

    public QuantityObjectMissingSystem();

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

- `private Game.Serialization.DataMigration.QuantityObjectMissingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.QuantityObjectMissingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public QuantityObjectMissingSystem()`  

```csharp
[Preserve]
	public QuantityObjectMissingSystem()
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
		m_Query = GetEntityQuery(ComponentType.ReadOnly<Object>(), ComponentType.ReadOnly<Static>(), ComponentType.Exclude<Quantity>(), ComponentType.Exclude<Plant>(), ComponentType.Exclude<Building>());
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
		if (!(m_LoadGameSystem.context.version >= Version.resourcePileFixes) && !m_Query.IsEmptyIgnoreFilter)
		{
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new QuantityObjectMissingJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabQuantityObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_QuantityObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_DeserializationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_Query, base.Dependency);
			m_DeserializationBarrier.AddJobHandleForProducer(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Serialization.DataMigration.QuantityObjectMissingSystem+QuantityObjectMissingJob`  
- `Game.Serialization.DataMigration.QuantityObjectMissingSystem+TypeHandle`  

