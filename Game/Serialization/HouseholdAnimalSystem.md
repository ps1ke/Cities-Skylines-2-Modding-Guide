# Game.Serialization.HouseholdAnimalSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdAnimalSystem : Game.GameSystemBase
{
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.HouseholdAnimalSystem+TypeHandle __TypeHandle;

    public HouseholdAnimalSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.DeserializationBarrier m_DeserializationBarrier`  

```csharp
private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.HouseholdAnimalSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.HouseholdAnimalSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdAnimalSystem()`  

```csharp
[Preserve]
	public HouseholdAnimalSystem()
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
		m_DeserializationBarrier = base.World.GetOrCreateSystemManaged<DeserializationBarrier>();
		m_Query = GetEntityQuery(ComponentType.ReadOnly<HouseholdPet>());
		RequireForUpdate(m_Query);
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
		HouseholdAnimalJob jobData = new HouseholdAnimalJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HouseholdPetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdPet_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdAnimals = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdAnimal_RW_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_DeserializationBarrier.CreateCommandBuffer()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_Query, base.Dependency);
		m_DeserializationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Serialization.HouseholdAnimalSystem+HouseholdAnimalJob`  
- `Game.Serialization.HouseholdAnimalSystem+TypeHandle`  

