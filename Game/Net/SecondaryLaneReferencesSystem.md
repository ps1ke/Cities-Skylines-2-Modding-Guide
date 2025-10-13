# Game.Net.SecondaryLaneReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SecondaryLaneReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_LanesQuery;
    private Game.Net.SecondaryLaneReferencesSystem+TypeHandle __TypeHandle;

    public SecondaryLaneReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_LanesQuery;
```

- `private Game.Net.SecondaryLaneReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.SecondaryLaneReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SecondaryLaneReferencesSystem()`  

```csharp
[Preserve]
	public SecondaryLaneReferencesSystem()
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
		m_LanesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Lane>(),
				ComponentType.ReadOnly<SecondaryLane>(),
				ComponentType.ReadOnly<Owner>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[0]
		});
		RequireForUpdate(m_LanesQuery);
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
		UpdateLaneReferencesJob jobData = new UpdateLaneReferencesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PedestrianLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkingLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectionLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Lanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RW_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_LanesQuery, base.Dependency);
	}
```


## Nested types

- `Game.Net.SecondaryLaneReferencesSystem+UpdateLaneReferencesJob`  
- `Game.Net.SecondaryLaneReferencesSystem+TypeHandle`  

