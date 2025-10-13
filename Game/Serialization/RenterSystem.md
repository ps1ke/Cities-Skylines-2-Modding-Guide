# Game.Serialization.RenterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RenterSystem : Game.GameSystemBase
{
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.RenterSystem+TypeHandle __TypeHandle;

    public RenterSystem();

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

- `private Game.Serialization.RenterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.RenterSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RenterSystem()`  

```csharp
[Preserve]
	public RenterSystem()
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
		m_Query = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<PropertyRenter>(),
				ComponentType.ReadOnly<TouristHousehold>(),
				ComponentType.ReadOnly<HomelessHousehold>()
			}
		});
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
		RenterJob jobData = new RenterJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PropertyRenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TouristHouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HomelessHouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_CityServiceUpkeep_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RW_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_DeserializationBarrier.CreateCommandBuffer()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_Query, base.Dependency);
		m_DeserializationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Serialization.RenterSystem+RenterJob`  
- `Game.Serialization.RenterSystem+TypeHandle`  

