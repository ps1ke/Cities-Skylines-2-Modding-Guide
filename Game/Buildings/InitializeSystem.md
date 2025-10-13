# Game.Buildings.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
    private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
    private Unity.Entities.EntityQuery m_CoverageQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents;
    private Game.Buildings.InitializeSystem+TypeHandle __TypeHandle;

    public InitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
```

- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
```

- `private Unity.Entities.EntityQuery m_CoverageQuery`  

```csharp
private Unity.Entities.EntityQuery m_CoverageQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents`  

```csharp
private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents;
```

- `private Game.Buildings.InitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.InitializeSystem+TypeHandle __TypeHandle;
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier2>();
		m_ElectricityRoadConnectionGraphSystem = base.World.GetOrCreateSystemManaged<ElectricityRoadConnectionGraphSystem>();
		m_WaterPipeRoadConnectionGraphSystem = base.World.GetOrCreateSystemManaged<WaterPipeRoadConnectionGraphSystem>();
		m_CoverageQuery = GetEntityQuery(ComponentType.ReadOnly<CoverageServiceType>(), ComponentType.ReadOnly<CoverageElement>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Placeholder>());
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<ServiceUpgrade>(), ComponentType.Exclude<Placeholder>());
		m_DestroyedBuildingComponents = new ComponentTypeSet(ComponentType.ReadOnly<ElectricityConsumer>(), ComponentType.ReadOnly<WaterConsumer>(), ComponentType.ReadOnly<GarbageProducer>(), ComponentType.ReadOnly<MailProducer>());
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
		if (!m_CoverageQuery.IsEmptyIgnoreFilter)
		{
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new InitializeCoverageTypeJob
			{
				m_EntitiesType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabCoverageData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CoverageData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_CoverageQuery, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
			base.Dependency = jobHandle;
		}
		if (!m_BuildingQuery.IsEmptyIgnoreFilter)
		{
			JobHandle deps;
			JobHandle deps2;
			JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new InitializeBuildingsJob
			{
				m_EntitiesType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PoliceStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PoliceStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PostFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PostFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AbandonedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ElectricityConsumerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterConsumerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_GarbageProducerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MailProducerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConsumptionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ConsumptionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DestroyedBuildingComponents = m_DestroyedBuildingComponents,
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_UpdatedElectricityRoadEdges = m_ElectricityRoadConnectionGraphSystem.GetEdgeUpdateQueue(out deps).AsParallelWriter(),
				m_UpdatedWaterPipeRoadEdges = m_WaterPipeRoadConnectionGraphSystem.GetEdgeUpdateQueue(out deps2).AsParallelWriter()
			}, m_BuildingQuery, JobHandle.CombineDependencies(base.Dependency, deps, deps2));
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
			m_ElectricityRoadConnectionGraphSystem.AddQueueWriter(jobHandle2);
			m_WaterPipeRoadConnectionGraphSystem.AddQueueWriter(jobHandle2);
			base.Dependency = jobHandle2;
		}
	}
```


## Nested types

- `Game.Buildings.InitializeSystem+InitializeCoverageTypeJob`  
- `Game.Buildings.InitializeSystem+InitializeBuildingsJob`  
- `Game.Buildings.InitializeSystem+TypeHandle`  

