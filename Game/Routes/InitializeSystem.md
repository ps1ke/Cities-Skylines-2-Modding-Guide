# Game.Routes.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.EntityQuery m_RouteQuery;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
    private Game.Routes.InitializeSystem+TypeHandle __TypeHandle;

    public InitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.EntityQuery m_RouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteQuery;
```

- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
```

- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  

```csharp
private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
```

- `private Game.Routes.InitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.InitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeSystem()`  

```csharp
[Preserve]
	public InitializeSystem()
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
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_TransportVehicleSelectData = new TransportVehicleSelectData(this);
		m_CreatedQuery = GetEntityQuery(ComponentType.ReadOnly<Route>(), ComponentType.ReadOnly<RouteNumber>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
		m_RouteQuery = GetEntityQuery(ComponentType.ReadOnly<Route>(), ComponentType.ReadOnly<RouteNumber>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_VehiclePrefabQuery = GetEntityQuery(TransportVehicleSelectData.GetEntityQueryDesc());
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> routeChunks = m_RouteQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		m_TransportVehicleSelectData.PreUpdate(this, m_CityConfigurationSystem, m_VehiclePrefabQuery, Allocator.TempJob, out var jobHandle);
		AssignRouteNumbersJob jobData = new AssignRouteNumbersJob
		{
			m_RouteChunks = routeChunks,
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteNumberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_RouteNumber_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		SelectVehicleJob jobData2 = new SelectVehicleJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_VehicleModelType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_VehicleModel_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabTransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_TransportVehicleSelectData = m_TransportVehicleSelectData
		};
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
		JobHandle jobHandle3 = JobChunkExtensions.ScheduleParallel(jobData2, m_CreatedQuery, JobHandle.CombineDependencies(base.Dependency, jobHandle));
		m_TransportVehicleSelectData.PostUpdate(jobHandle3);
		routeChunks.Dispose(jobHandle2);
		base.Dependency = JobHandle.CombineDependencies(jobHandle2, jobHandle3);
	}
```


## Nested types

- `Game.Routes.InitializeSystem+AssignRouteNumbersJob`  
- `Game.Routes.InitializeSystem+SelectVehicleJob`  
- `Game.Routes.InitializeSystem+TypeHandle`  

