# Game.Routes.BoardingVehicleSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BoardingVehicleSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_WaypointQuery;
    private Unity.Entities.EntityQuery m_BoardingQuery;
    private System.Boolean m_Loaded;
    private Game.Routes.BoardingVehicleSystem+TypeHandle __TypeHandle;

    public BoardingVehicleSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_WaypointQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaypointQuery;
```

- `private Unity.Entities.EntityQuery m_BoardingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BoardingQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Routes.BoardingVehicleSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.BoardingVehicleSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BoardingVehicleSystem()`  

```csharp
[Preserve]
	public BoardingVehicleSystem()
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
		m_WaypointQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Waypoint>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_BoardingQuery = GetEntityQuery(ComponentType.ReadWrite<BoardingVehicle>());
		RequireForUpdate(m_BoardingQuery);
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
		if (GetLoaded() || !m_WaypointQuery.IsEmptyIgnoreFilter)
		{
			JobHandle dependency = JobChunkExtensions.ScheduleParallel(new BoardingVehicleJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_BoardingVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_BoardingVehicle_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef)
			}, m_BoardingQuery, base.Dependency);
			base.Dependency = dependency;
		}
	}
```


## Nested types

- `Game.Routes.BoardingVehicleSystem+BoardingVehicleJob`  
- `Game.Routes.BoardingVehicleSystem+TypeHandle`  

