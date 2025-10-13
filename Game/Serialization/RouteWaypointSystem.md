# Game.Serialization.RouteWaypointSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteWaypointSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.RouteWaypointSystem+TypeHandle __TypeHandle;

    public RouteWaypointSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.RouteWaypointSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.RouteWaypointSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteWaypointSystem()`  

```csharp
[Preserve]
	public RouteWaypointSystem()
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
		m_Query = GetEntityQuery(ComponentType.ReadOnly<Waypoint>(), ComponentType.ReadOnly<Owner>());
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
		RouteWaypointJob jobData = new RouteWaypointJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_WaypointType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RW_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_Query, base.Dependency);
	}
```


## Nested types

- `Game.Serialization.RouteWaypointSystem+RouteWaypointJob`  
- `Game.Serialization.RouteWaypointSystem+TypeHandle`  

