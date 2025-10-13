# Game.Tools.ApplyObjectsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyObjectsSystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Unity.Entities.ComponentTypeSet m_TempAnimationTypes;
    private Game.Tools.ApplyObjectsSystem+TypeHandle __TypeHandle;

    public ApplyObjectsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem`  

```csharp
private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityArchetype m_PathTargetEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_TempAnimationTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TempAnimationTypes;
```

- `private Game.Tools.ApplyObjectsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ApplyObjectsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ApplyObjectsSystem()`  

```csharp
[Preserve]
	public ApplyObjectsSystem()
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
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_InstanceCountSystem = base.World.GetOrCreateSystemManaged<InstanceCountSystem>();
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Object>());
		m_PathTargetEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<PathTargetMoved>());
		m_AppliedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<Updated>());
		m_TempAnimationTypes = new ComponentTypeSet(ComponentType.ReadWrite<Temp>(), ComponentType.ReadWrite<Animation>(), ComponentType.ReadWrite<BackSide>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		RequireForUpdate(m_TempQuery);
		RequireForUpdate(m_EconomyParameterQuery);
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
		PatchTempReferencesJob jobData = new PatchTempReferencesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AttachedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_VehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatureType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Creature_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RW_BufferLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RW_BufferLookup, ref base.CheckedStateRef),
			m_OwnedCreatures = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Creatures_OwnedCreature_RW_BufferLookup, ref base.CheckedStateRef)
		};
		NativeQueue<TriggerAction> nativeQueue = (m_TriggerSystem.Enabled ? m_TriggerSystem.CreateActionBuffer() : new NativeQueue<TriggerAction>(Allocator.TempJob));
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new HandleTempEntitiesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AttachedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WatercraftCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AircraftCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HumanCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AnimalCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RescueTargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_RescueTarget_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransportStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportStop_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RecentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Recent_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DamagedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StaticData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Static_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StoppedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Stopped_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SwayingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_Swaying_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_MeshColors = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshColor_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_EconomyParameterData = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_PathTargetEventArchetype = m_PathTargetEventArchetype,
			m_AppliedTypes = m_AppliedTypes,
			m_TempAnimationTypes = m_TempAnimationTypes,
			m_InstanceCounts = m_InstanceCountSystem.GetInstanceCounts(readOnly: true, out dependencies),
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_TriggerBuffer = nativeQueue.AsParallelWriter()
		}, dependsOn: JobHandle.CombineDependencies(JobChunkExtensions.Schedule(jobData, m_TempQuery, base.Dependency), dependencies), query: m_TempQuery);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
		if (m_TriggerSystem.Enabled)
		{
			m_TriggerSystem.AddActionBufferWriter(jobHandle);
		}
		else
		{
			nativeQueue.Dispose(jobHandle);
		}
		m_InstanceCountSystem.AddCountReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Tools.ApplyObjectsSystem+PatchTempReferencesJob`  
- `Game.Tools.ApplyObjectsSystem+HandleTempEntitiesJob`  
- `Game.Tools.ApplyObjectsSystem+TypeHandle`  

