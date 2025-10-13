# Game.Net.FlipTrafficHandednessSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FlipTrafficHandednessSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_RoadEdgeQuery;
    private Game.Net.FlipTrafficHandednessSystem+TypeHandle __TypeHandle;

    public FlipTrafficHandednessSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RoadEdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoadEdgeQuery;
```

- `private Game.Net.FlipTrafficHandednessSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.FlipTrafficHandednessSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FlipTrafficHandednessSystem()`  

```csharp
[Preserve]
	public FlipTrafficHandednessSystem()
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
		m_RoadEdgeQuery = GetEntityQuery(ComponentType.ReadOnly<Road>(), ComponentType.ReadOnly<Edge>());
		RequireForUpdate(m_RoadEdgeQuery);
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
		FlipOnewayRoadsJob jobData = new FlipOnewayRoadsJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ElevationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Elevation_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpgradedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Upgraded_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildOrderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_BuildOrder_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectedNodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ConnectedNode_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ServiceCoverageType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ServiceCoverage_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ResourceAvailabilityType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ResourceAvailability_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_RoadEdgeQuery, base.Dependency);
	}
```


## Nested types

- `Game.Net.FlipTrafficHandednessSystem+FlipOnewayRoadsJob`  
- `Game.Net.FlipTrafficHandednessSystem+TypeHandle`  

