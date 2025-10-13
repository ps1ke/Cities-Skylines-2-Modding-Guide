# Game.Simulation.TrafficLightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficLightSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_TrafficLightQuery;
    private Game.Simulation.TrafficLightSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public TrafficLightSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void UpdateLaneSignal(Game.Net.TrafficLights trafficLights, Game.Net.LaneSignal& laneSignal);
    public static System.Void UpdateMoveableBridge(Game.Net.TrafficLights trafficLights, Game.Objects.Transform transform, Game.Prefabs.MoveableBridgeData moveableBridgeData, Game.Common.PointOfInterest& pointOfInterest);
    public static System.Void UpdateTrafficLightState(Game.Net.TrafficLights trafficLights, Game.Objects.TrafficLight& trafficLight);
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

- `private Unity.Entities.EntityQuery m_TrafficLightQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrafficLightQuery;
```

- `private Game.Simulation.TrafficLightSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrafficLightSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public TrafficLightSystem()`  

```csharp
[Preserve]
	public TrafficLightSystem()
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
		return 4;
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
		m_TrafficLightQuery = GetEntityQuery(ComponentType.ReadWrite<TrafficLights>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_TrafficLightQuery);
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
		m_TrafficLightQuery.ResetFilter();
		m_TrafficLightQuery.SetSharedComponentFilter(new UpdateFrame(SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16)));
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new UpdateTrafficLightsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_SubLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ConnectedEdgeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TrafficLightsType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrafficLights_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneReservationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneReservation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabMoveableBridgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MoveableBridgeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneSignalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneSignal_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TrafficLightData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_TrafficLight_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PointOfInterestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PointOfInterest_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_TrafficLightQuery, base.Dependency);
		base.Dependency = dependency;
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```

- `public static UpdateLaneSignal(Game.Net.TrafficLights trafficLights, Game.Net.LaneSignal& laneSignal) : System.Void`  

```csharp
public static void UpdateLaneSignal(TrafficLights trafficLights, ref LaneSignal laneSignal)
	{
		int num = 0;
		int num2 = 0;
		if (trafficLights.m_CurrentSignalGroup > 0)
		{
			num |= 1 << trafficLights.m_CurrentSignalGroup - 1;
		}
		if (trafficLights.m_NextSignalGroup > 0)
		{
			num2 |= 1 << trafficLights.m_NextSignalGroup - 1;
		}
		switch (trafficLights.m_State)
		{
		case Game.Net.TrafficLightState.Beginning:
			if ((laneSignal.m_GroupMask & num2) != 0)
			{
				if (laneSignal.m_Signal != LaneSignalType.Go)
				{
					laneSignal.m_Signal = LaneSignalType.Yield;
				}
			}
			else
			{
				laneSignal.m_Signal = LaneSignalType.Stop;
			}
			break;
		case Game.Net.TrafficLightState.Ongoing:
			if ((laneSignal.m_GroupMask & num) != 0)
			{
				laneSignal.m_Signal = LaneSignalType.Go;
			}
			else
			{
				laneSignal.m_Signal = LaneSignalType.Stop;
			}
			break;
		case Game.Net.TrafficLightState.Extending:
			if ((laneSignal.m_Flags & LaneSignalFlags.CanExtend) != 0)
			{
				if ((laneSignal.m_GroupMask & num) != 0)
				{
					laneSignal.m_Signal = LaneSignalType.Go;
				}
				else
				{
					laneSignal.m_Signal = LaneSignalType.Stop;
				}
			}
			else if (laneSignal.m_Signal == LaneSignalType.Go)
			{
				if ((laneSignal.m_GroupMask & num2) == 0)
				{
					laneSignal.m_Signal = LaneSignalType.SafeStop;
				}
			}
			else
			{
				laneSignal.m_Signal = LaneSignalType.Stop;
			}
			break;
		case Game.Net.TrafficLightState.Extended:
			if ((laneSignal.m_Flags & LaneSignalFlags.CanExtend) != 0 && (laneSignal.m_GroupMask & num) != 0)
			{
				laneSignal.m_Signal = LaneSignalType.Go;
			}
			else
			{
				laneSignal.m_Signal = LaneSignalType.Stop;
			}
			break;
		case Game.Net.TrafficLightState.Ending:
			if (laneSignal.m_Signal == LaneSignalType.Go)
			{
				if ((laneSignal.m_GroupMask & num2) == 0)
				{
					laneSignal.m_Signal = LaneSignalType.SafeStop;
				}
			}
			else
			{
				laneSignal.m_Signal = LaneSignalType.Stop;
			}
			break;
		case Game.Net.TrafficLightState.Changing:
			if (laneSignal.m_Signal != LaneSignalType.Go || (laneSignal.m_GroupMask & num2) == 0)
			{
				laneSignal.m_Signal = LaneSignalType.Stop;
			}
			break;
		default:
			laneSignal.m_Signal = LaneSignalType.None;
			break;
		}
	}
```

- `public static UpdateMoveableBridge(Game.Net.TrafficLights trafficLights, Game.Objects.Transform transform, Game.Prefabs.MoveableBridgeData moveableBridgeData, Game.Common.PointOfInterest& pointOfInterest) : System.Void`  

```csharp
public static void UpdateMoveableBridge(TrafficLights trafficLights, Transform transform, MoveableBridgeData moveableBridgeData, ref PointOfInterest pointOfInterest)
	{
		int num = -1;
		if (trafficLights.m_State == Game.Net.TrafficLightState.Beginning || trafficLights.m_State == Game.Net.TrafficLightState.Changing)
		{
			if (trafficLights.m_NextSignalGroup > 0)
			{
				num = trafficLights.m_NextSignalGroup - 1;
			}
		}
		else if (trafficLights.m_State != Game.Net.TrafficLightState.Ending && trafficLights.m_CurrentSignalGroup > 0)
		{
			num = trafficLights.m_CurrentSignalGroup - 1;
		}
		pointOfInterest.m_IsValid = false;
		if (num >= 0 && num <= 2)
		{
			pointOfInterest.m_Position = transform.m_Position;
			pointOfInterest.m_Position.y += moveableBridgeData.m_LiftOffsets[num];
			pointOfInterest.m_IsValid = true;
		}
	}
```

- `public static UpdateTrafficLightState(Game.Net.TrafficLights trafficLights, Game.Objects.TrafficLight& trafficLight) : System.Void`  

```csharp
public static void UpdateTrafficLightState(TrafficLights trafficLights, ref TrafficLight trafficLight)
	{
		int num = 0;
		int num2 = 0;
		if (trafficLights.m_CurrentSignalGroup > 0)
		{
			num |= 1 << trafficLights.m_CurrentSignalGroup - 1;
		}
		if (trafficLights.m_NextSignalGroup > 0)
		{
			num2 |= 1 << trafficLights.m_NextSignalGroup - 1;
		}
		Game.Objects.TrafficLightState trafficLightState = trafficLight.m_State & (Game.Objects.TrafficLightState.Red | Game.Objects.TrafficLightState.Yellow | Game.Objects.TrafficLightState.Green | Game.Objects.TrafficLightState.Flashing);
		Game.Objects.TrafficLightState trafficLightState2 = (Game.Objects.TrafficLightState)(((int)trafficLight.m_State >> 4) & 0xF);
		Game.Objects.TrafficLightState trafficLightState3 = (((trafficLights.m_Flags & TrafficLightFlags.LevelCrossing) != 0) ? (Game.Objects.TrafficLightState.Yellow | Game.Objects.TrafficLightState.Flashing) : Game.Objects.TrafficLightState.Yellow);
		Game.Objects.TrafficLightState trafficLightState4 = (((trafficLights.m_Flags & TrafficLightFlags.LevelCrossing) == 0) ? Game.Objects.TrafficLightState.Red : (Game.Objects.TrafficLightState.Red | Game.Objects.TrafficLightState.Flashing));
		switch (trafficLights.m_State)
		{
		case Game.Net.TrafficLightState.Beginning:
			if ((trafficLight.m_GroupMask0 & num2) != 0)
			{
				if (trafficLightState != Game.Objects.TrafficLightState.Green)
				{
					trafficLightState = trafficLightState4 | trafficLightState3;
				}
			}
			else
			{
				trafficLightState = trafficLightState4;
			}
			trafficLightState2 = (((trafficLight.m_GroupMask1 & num2) == 0) ? Game.Objects.TrafficLightState.Red : Game.Objects.TrafficLightState.Green);
			break;
		case Game.Net.TrafficLightState.Ongoing:
			trafficLightState = (((trafficLight.m_GroupMask0 & num) == 0) ? trafficLightState4 : Game.Objects.TrafficLightState.Green);
			trafficLightState2 = (((trafficLight.m_GroupMask1 & num) == 0) ? Game.Objects.TrafficLightState.Red : Game.Objects.TrafficLightState.Green);
			break;
		case Game.Net.TrafficLightState.Extending:
			trafficLightState = (((trafficLight.m_GroupMask0 & num) == 0) ? trafficLightState4 : Game.Objects.TrafficLightState.Green);
			if (trafficLightState2 == Game.Objects.TrafficLightState.Green)
			{
				if ((trafficLight.m_GroupMask1 & num2) == 0)
				{
					trafficLightState2 = Game.Objects.TrafficLightState.Green | Game.Objects.TrafficLightState.Flashing;
				}
			}
			else
			{
				trafficLightState2 = Game.Objects.TrafficLightState.Red;
			}
			break;
		case Game.Net.TrafficLightState.Extended:
			trafficLightState = (((trafficLight.m_GroupMask0 & num) == 0) ? trafficLightState4 : Game.Objects.TrafficLightState.Green);
			if (trafficLightState2 != Game.Objects.TrafficLightState.Green || (trafficLight.m_GroupMask1 & num2) == 0)
			{
				trafficLightState2 = Game.Objects.TrafficLightState.Red;
			}
			break;
		case Game.Net.TrafficLightState.Ending:
			if (trafficLightState == Game.Objects.TrafficLightState.Green)
			{
				if ((trafficLight.m_GroupMask0 & num2) == 0)
				{
					trafficLightState = trafficLightState3;
				}
			}
			else
			{
				trafficLightState = trafficLightState4;
			}
			if (trafficLightState2 == Game.Objects.TrafficLightState.Green)
			{
				if ((trafficLight.m_GroupMask1 & num2) == 0)
				{
					trafficLightState2 = Game.Objects.TrafficLightState.Green | Game.Objects.TrafficLightState.Flashing;
				}
			}
			else
			{
				trafficLightState2 = Game.Objects.TrafficLightState.Red;
			}
			break;
		case Game.Net.TrafficLightState.Changing:
			if (trafficLightState != Game.Objects.TrafficLightState.Green || (trafficLight.m_GroupMask0 & num2) == 0)
			{
				trafficLightState = trafficLightState4;
			}
			if (trafficLightState2 != Game.Objects.TrafficLightState.Green || (trafficLight.m_GroupMask1 & num2) == 0)
			{
				trafficLightState2 = Game.Objects.TrafficLightState.Red;
			}
			break;
		default:
			trafficLightState = Game.Objects.TrafficLightState.None;
			trafficLightState2 = Game.Objects.TrafficLightState.None;
			break;
		}
		trafficLight.m_State = (Game.Objects.TrafficLightState)((uint)trafficLightState | ((uint)trafficLightState2 << 4));
	}
```


## Nested types

- `Game.Simulation.TrafficLightSystem+UpdateTrafficLightsJob`  
- `Game.Simulation.TrafficLightSystem+TypeHandle`  

