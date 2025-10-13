# Game.Simulation.PropertyRenterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PropertyRenterSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Unity.Entities.EntityQuery m_BuildingGroup;
    private Unity.Entities.EntityQuery m_GarbageFacilityGroup;
    private Unity.Entities.EntityQuery m_MovingAwayHouseholdGroup;
    private Unity.Entities.EntityArchetype m_RentEventArchetype;
    private Game.Simulation.PropertyRenterSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_595560377_0;
    public static readonly System.Int32 kUpdatesPerDay;

    public PropertyRenterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Int32 GetUpkeep(System.Int32 level, System.Single baseUpkeep, System.Int32 lotSize, Game.Zones.AreaType areaType, Game.Prefabs.EconomyParameterData& economyParameterData, System.Boolean isStorage);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingGroup;
```

- `private Unity.Entities.EntityQuery m_GarbageFacilityGroup`  

```csharp
private Unity.Entities.EntityQuery m_GarbageFacilityGroup;
```

- `private Unity.Entities.EntityQuery m_MovingAwayHouseholdGroup`  

```csharp
private Unity.Entities.EntityQuery m_MovingAwayHouseholdGroup;
```

- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RentEventArchetype;
```

- `private Game.Simulation.PropertyRenterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PropertyRenterSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_595560377_0`  

```csharp
private Unity.Entities.EntityQuery __query_595560377_0;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public PropertyRenterSystem()`  

```csharp
[Preserve]
	public PropertyRenterSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<ServiceFeeParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_595560377_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `public static GetUpkeep(System.Int32 level, System.Single baseUpkeep, System.Int32 lotSize, Game.Zones.AreaType areaType, Game.Prefabs.EconomyParameterData& economyParameterData, System.Boolean isStorage = False) : System.Int32`  

```csharp
public static int GetUpkeep(int level, float baseUpkeep, int lotSize, AreaType areaType, ref EconomyParameterData economyParameterData, bool isStorage = false)
	{
		float num;
		switch (areaType)
		{
		case AreaType.Residential:
			return Mathf.RoundToInt(math.pow(level, economyParameterData.m_ResidentialUpkeepLevelExponent) * baseUpkeep * (float)lotSize);
		default:
			num = 1f;
			break;
		case AreaType.Industrial:
			num = economyParameterData.m_IndustrialUpkeepLevelExponent;
			break;
		case AreaType.Commercial:
			num = economyParameterData.m_CommercialUpkeepLevelExponent;
			break;
		}
		float y = num;
		return Mathf.RoundToInt(math.pow(level, y) * baseUpkeep * (float)lotSize * (isStorage ? 0.5f : 1f));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ServiceFeeSystem = base.World.GetOrCreateSystemManaged<ServiceFeeSystem>();
		m_BuildingGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Renter>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			Any = new ComponentType[1] { ComponentType.ReadWrite<BuildingCondition>() },
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_GarbageFacilityGroup = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.GarbageFacility>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_MovingAwayHouseholdGroup = GetEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<MovingAway>(), ComponentType.ReadOnly<PropertyRenter>());
		m_RentEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<RentersUpdated>());
		RequireForUpdate(m_BuildingGroup);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		bool providedGarbageService = false;
		NativeArray<Entity> nativeArray = m_GarbageFacilityGroup.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (base.EntityManager.TryGetComponent<Building>(nativeArray[i], out var component) && !BuildingUtils.CheckOption(component, BuildingOption.Inactive))
			{
				providedGarbageService = true;
				break;
			}
		}
		nativeArray.Dispose();
		JobHandle jobHandle = JobChunkExtensions.Schedule(new RenterMovingAwayJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_MovingAwayHouseholdGroup, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		jobHandle = JobChunkExtensions.ScheduleParallel(new PayRentJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = GetSharedComponentTypeHandle<UpdateFrame>(),
			m_SpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RW_BufferLookup, ref base.CheckedStateRef),
			m_BuildingProperties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertiesOnMarket = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyOnMarket_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Abandoned = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Destroyed = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Storages = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RentEventArchetype = m_RentEventArchetype,
			m_RandomSeed = RandomSeed.Next(),
			m_FeeParameters = __query_595560377_0.GetSingleton<ServiceFeeParameterData>(),
			m_UpdateFrameIndex = updateFrame,
			m_ProvidedGarbageService = providedGarbageService,
			m_FeeQueue = m_ServiceFeeSystem.GetFeeQueue(out var deps).AsParallelWriter(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_BuildingGroup, JobHandle.CombineDependencies(jobHandle, deps));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		m_ServiceFeeSystem.AddQueueWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


## Nested types

- `Game.Simulation.PropertyRenterSystem+PayRentJob`  
- `Game.Simulation.PropertyRenterSystem+RenterMovingAwayJob`  
- `Game.Simulation.PropertyRenterSystem+TypeHandle`  

