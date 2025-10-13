# Game.Simulation.ServiceCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceCompanySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
    private Unity.Entities.EntityQuery m_BuildingParameterQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.ServiceCompanySystem+TypeHandle __TypeHandle;

    public ServiceCompanySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingParameterQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.ServiceCompanySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ServiceCompanySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceCompanySystem()`  

```csharp
[Preserve]
	public ServiceCompanySystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (EconomyUtils.kCompanyUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_CompanyGroup = GetEntityQuery(ComponentType.ReadOnly<CompanyData>(), ComponentType.ReadWrite<ServiceAvailable>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<WorkProvider>(), ComponentType.ReadOnly<Employee>(), ComponentType.ReadOnly<UpdateFrame>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_CompanyNotificationParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CompanyNotificationParameterData>());
		m_BuildingParameterQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		RequireForUpdate(m_CompanyGroup);
		RequireForUpdate(m_CompanyNotificationParameterQuery);
		RequireForUpdate(m_EconomyParameterQuery);
		RequireForUpdate(m_BuildingParameterQuery);
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, EconomyUtils.kCompanyUpdatesPerDay, 16);
		UpdateServiceJob jobData = new UpdateServiceJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PropertyRenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LodgingProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_LodgingProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceAvailableType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_ServiceAvailable_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompanyNotificationsType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_CompanyNotifications_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EmployeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_Employee_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingEfficiencies = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RW_ComponentLookup, ref base.CheckedStateRef),
			m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DistrictModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_DistrictModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_Districts = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxPayers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_TaxPayer_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TaxRates = m_TaxSystem.GetTaxRates(),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_CompanyNotificationParameters = m_CompanyNotificationParameterQuery.GetSingleton<CompanyNotificationParameterData>(),
			m_BuildingConfigurationData = m_BuildingParameterQuery.GetSingleton<BuildingConfigurationData>(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_RandomSeed = RandomSeed.Next(),
			m_UpdateFrameIndex = updateFrame
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CompanyGroup, base.Dependency);
		m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
		m_TaxSystem.AddReader(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.ServiceCompanySystem+UpdateServiceJob`  
- `Game.Simulation.ServiceCompanySystem+TypeHandle`  

