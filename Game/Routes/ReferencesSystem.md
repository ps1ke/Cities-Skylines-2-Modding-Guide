# Game.Routes.ReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_RouteQuery;
    private Game.Routes.ReferencesSystem+TypeHandle __TypeHandle;

    public ReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteQuery;
```

- `private Game.Routes.ReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.ReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ReferencesSystem()`  

```csharp
[Preserve]
	public ReferencesSystem()
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
		m_RouteQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Route>(),
				ComponentType.ReadOnly<RouteWaypoint>(),
				ComponentType.ReadOnly<RouteSegment>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		RequireForUpdate(m_RouteQuery);
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
		NativeList<ArchetypeChunk> routeChunks = m_RouteQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new UpdateRouteReferencesJob
		{
			m_RouteChunks = routeChunks,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_RouteWaypointType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_RouteSegmentType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RW_ComponentLookup, ref base.CheckedStateRef),
			m_SubRoutes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_SubRoute_RW_BufferLookup, ref base.CheckedStateRef)
		}, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
		routeChunks.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Routes.ReferencesSystem+UpdateRouteReferencesJob`  
- `Game.Routes.ReferencesSystem+TypeHandle`  

