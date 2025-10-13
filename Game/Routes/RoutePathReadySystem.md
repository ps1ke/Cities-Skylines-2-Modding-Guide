# Game.Routes.RoutePathReadySystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoutePathReadySystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_PathReadyQuery;
    private Unity.Entities.EntityQuery m_RouteQuery;
    private Unity.Entities.EntityQuery m_RouteConfigQuery;
    private System.Boolean m_Loaded;
    private Game.Routes.RoutePathReadySystem+TypeHandle __TypeHandle;

    public RoutePathReadySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_PathReadyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PathReadyQuery;
```

- `private Unity.Entities.EntityQuery m_RouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteQuery;
```

- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteConfigQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Routes.RoutePathReadySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.RoutePathReadySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RoutePathReadySystem()`  

```csharp
[Preserve]
	public RoutePathReadySystem()
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

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_PathReadyQuery = GetEntityQuery(ComponentType.ReadOnly<Event>(), ComponentType.ReadOnly<PathUpdated>());
		m_RouteQuery = GetEntityQuery(ComponentType.ReadOnly<Route>());
		m_RouteConfigQuery = GetEntityQuery(ComponentType.ReadOnly<RouteConfigurationData>());
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EntityQuery query = (GetLoaded() ? m_RouteQuery : m_PathReadyQuery);
		if (!query.IsEmptyIgnoreFilter)
		{
			JobHandle jobHandle = JobChunkExtensions.Schedule(new RoutePathReadyJob
			{
				m_PathUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_RouteWaypointType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_RouteSegmentType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SegmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathInformationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteSegments = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferLookup, ref base.CheckedStateRef),
				m_PathTargetsData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_PathTargets_RW_ComponentLookup, ref base.CheckedStateRef),
				m_RouteConfigurationData = m_RouteConfigQuery.GetSingleton<RouteConfigurationData>(),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
			}, query, base.Dependency);
			m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Routes.RoutePathReadySystem+RoutePathReadyJob`  
- `Game.Routes.RoutePathReadySystem+TypeHandle`  

