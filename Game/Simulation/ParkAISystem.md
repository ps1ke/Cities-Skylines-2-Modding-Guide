# Game.Simulation.ParkAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkAISystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_ParkQuery;
    private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
    private Game.Simulation.ParkAISystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public ParkAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetMaintenancePriority(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData);
    public static Game.Buildings.ModifiedServiceCoverage GetModifiedServiceCoverage(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData, Game.Prefabs.CoverageData prefabCoverageData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_ParkQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkQuery;
```

- `private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
```

- `private Game.Simulation.ParkAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ParkAISystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public ParkAISystem()`  

```csharp
[Preserve]
	public ParkAISystem()
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

- `public static GetMaintenancePriority(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData) : System.Int32`  

```csharp
public static int GetMaintenancePriority(Game.Buildings.Park park, ParkData prefabParkData)
	{
		return prefabParkData.m_MaintenancePool - park.m_Maintenance - prefabParkData.m_MaintenancePool / 10;
	}
```

- `public static GetModifiedServiceCoverage(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData, Game.Prefabs.CoverageData prefabCoverageData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : Game.Buildings.ModifiedServiceCoverage`  

```csharp
public static ModifiedServiceCoverage GetModifiedServiceCoverage(Game.Buildings.Park park, ParkData prefabParkData, CoverageData prefabCoverageData, DynamicBuffer<CityModifier> cityModifiers)
	{
		float num = (float)park.m_Maintenance / (float)math.max(1, prefabParkData.m_MaintenancePool);
		ModifiedServiceCoverage result = new ModifiedServiceCoverage(prefabCoverageData);
		int num2 = Mathf.FloorToInt(num / 0.3f);
		result.m_Magnitude *= 0.95f + 0.05f * (float)math.min(1, num2) + 0.1f * (float)math.max(0, num2 - 1);
		result.m_Range *= 0.95f + 0.05f * (float)num2;
		if (cityModifiers.IsCreated)
		{
			CityUtils.ApplyModifier(ref result.m_Magnitude, cityModifiers, CityModifierType.ParkEntertainment);
		}
		return result;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / kUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ParkQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.Park>(), ComponentType.ReadWrite<ModifiedServiceCoverage>(), ComponentType.ReadOnly<Renter>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>());
		m_MaintenanceRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<MaintenanceRequest>(), ComponentType.ReadWrite<RequestGroup>());
		RequireForUpdate(m_ParkQuery);
		Assert.IsTrue((long)(262144 / kUpdatesPerDay) >= 512L);
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
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new ParkTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Park_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MaintenanceConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_MaintenanceConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ModifiedServiceCoverageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ModifiedServiceCoverage_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CoverageDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CoverageData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MaintenanceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_MaintenanceRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_MaintenanceRequestArchetype = m_MaintenanceRequestArchetype,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_ParkQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.ParkAISystem+ParkTickJob`  
- `Game.Simulation.ParkAISystem+TypeHandle`  

