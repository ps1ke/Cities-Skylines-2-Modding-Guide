# Game.Policies.RouteModifierInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteModifierInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData;
    private Game.Policies.RouteModifierInitializeSystem+TypeHandle __TypeHandle;

    public RouteModifierInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData`  

```csharp
private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData;
```

- `private Game.Policies.RouteModifierInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.RouteModifierInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteModifierInitializeSystem()`  

```csharp
[Preserve]
	public RouteModifierInitializeSystem()
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
		m_RouteModifierRefreshData = new RouteModifierRefreshData(this);
		m_CreatedQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadWrite<Route>(), ComponentType.ReadOnly<Policy>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_CreatedQuery);
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
		m_RouteModifierRefreshData.Update(this);
		InitializeRouteModifiersJob jobData = new InitializeRouteModifiersJob
		{
			m_RouteModifierRefreshData = m_RouteModifierRefreshData,
			m_PolicyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Policies_Policy_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_RouteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Route_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteModifierType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteModifier_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedQuery, base.Dependency);
	}
```


## Nested types

- `Game.Policies.RouteModifierInitializeSystem+InitializeRouteModifiersJob`  
- `Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData`  
- `Game.Policies.RouteModifierInitializeSystem+TypeHandle`  

