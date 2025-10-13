# Game.Simulation.RemovedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RemovedSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_DeletedBuildings;
    private Unity.Entities.EntityQuery m_DeletedWorkplaces;
    private Unity.Entities.EntityQuery m_DeletedCompanies;
    private Unity.Entities.EntityQuery m_NeedUpdateRenterQuery;
    private Unity.Entities.EntityQuery m_BuildingParameterQuery;
    private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Simulation.RemovedSystem+TypeHandle __TypeHandle;

    public RemovedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_DeletedBuildings`  

```csharp
private Unity.Entities.EntityQuery m_DeletedBuildings;
```

- `private Unity.Entities.EntityQuery m_DeletedWorkplaces`  

```csharp
private Unity.Entities.EntityQuery m_DeletedWorkplaces;
```

- `private Unity.Entities.EntityQuery m_DeletedCompanies`  

```csharp
private Unity.Entities.EntityQuery m_DeletedCompanies;
```

- `private Unity.Entities.EntityQuery m_NeedUpdateRenterQuery`  

```csharp
private Unity.Entities.EntityQuery m_NeedUpdateRenterQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Simulation.RemovedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.RemovedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RemovedSystem()`  

```csharp
[Preserve]
	public RemovedSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_DeletedBuildings = GetEntityQuery(ComponentType.ReadOnly<Renter>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
		m_DeletedWorkplaces = GetEntityQuery(ComponentType.ReadOnly<Employee>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
		m_DeletedCompanies = GetEntityQuery(ComponentType.ReadOnly<CompanyNotifications>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
		m_NeedUpdateRenterQuery = GetEntityQuery(ComponentType.ReadOnly<Event>(), ComponentType.ReadOnly<RentersUpdated>());
		m_BuildingParameterQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		m_CompanyNotificationParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CompanyNotificationParameterData>());
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
		JobHandle jobHandle = default(JobHandle);
		if (!m_DeletedBuildings.IsEmptyIgnoreFilter)
		{
			jobHandle = JobChunkExtensions.ScheduleParallel(new RemovedPropertyJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_RenterBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_TouristHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LodgingProviders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_LodgingProvider_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_DeletedBuildings, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		}
		JobHandle jobHandle2 = default(JobHandle);
		if (!m_DeletedWorkplaces.IsEmptyIgnoreFilter)
		{
			jobHandle2 = JobChunkExtensions.ScheduleParallel(new RemovedWorkplaceJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_EmployeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_Employee_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_Purposes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_DeletedWorkplaces, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		}
		JobHandle jobHandle3 = default(JobHandle);
		if (!m_DeletedCompanies.IsEmptyIgnoreFilter && !m_CompanyNotificationParameterQuery.IsEmptyIgnoreFilter)
		{
			jobHandle3 = JobChunkExtensions.ScheduleParallel(new RemovedCompanyJob
			{
				m_NotificationsType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_CompanyNotifications_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CompanyNotificationParameters = m_CompanyNotificationParameterQuery.GetSingleton<CompanyNotificationParameterData>(),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
			}, m_DeletedCompanies, base.Dependency);
			m_IconCommandSystem.AddCommandBufferWriter(jobHandle3);
		}
		JobHandle jobHandle4 = default(JobHandle);
		if (!m_NeedUpdateRenterQuery.IsEmptyIgnoreFilter)
		{
			jobHandle4 = JobChunkExtensions.Schedule(new RentersUpdateJob
			{
				m_RentersUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_RentersUpdated_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RW_BufferLookup, ref base.CheckedStateRef),
				m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Deleteds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Abandoneds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Parks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MovingAways = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_MovingAway_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RW_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingConfigurationData = m_BuildingParameterQuery.GetSingleton<BuildingConfigurationData>(),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
			}, m_NeedUpdateRenterQuery, JobHandle.CombineDependencies(base.Dependency, jobHandle));
			m_IconCommandSystem.AddCommandBufferWriter(jobHandle4);
		}
		base.Dependency = JobHandle.CombineDependencies(jobHandle, jobHandle2, JobHandle.CombineDependencies(jobHandle3, jobHandle4));
	}
```


## Nested types

- `Game.Simulation.RemovedSystem+RemovedPropertyJob`  
- `Game.Simulation.RemovedSystem+RemovedWorkplaceJob`  
- `Game.Simulation.RemovedSystem+RemovedCompanyJob`  
- `Game.Simulation.RemovedSystem+RentersUpdateJob`  
- `Game.Simulation.RemovedSystem+TypeHandle`  

