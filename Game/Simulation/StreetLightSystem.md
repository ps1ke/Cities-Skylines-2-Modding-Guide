# Game.Simulation.StreetLightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StreetLightSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_StreetLightQuery;
    private Game.Simulation.StreetLightSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public StreetLightSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Net.Road road);
    public static System.Void UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Buildings.Building building);
    public static System.Void UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Vehicles.Watercraft watercraft);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_StreetLightQuery`  

```csharp
private Unity.Entities.EntityQuery m_StreetLightQuery;
```

- `private Game.Simulation.StreetLightSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.StreetLightSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public StreetLightSystem()`  

```csharp
[Preserve]
	public StreetLightSystem()
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
		return 16;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_LightingSystem = base.World.GetOrCreateSystemManaged<LightingSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_StreetLightQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<UpdateFrame>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Road>(),
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Watercraft>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		RequireForUpdate(m_StreetLightQuery);
		Assert.AreEqual(16, 16);
		Assert.AreEqual(16, 16);
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
		m_StreetLightQuery.ResetFilter();
		m_StreetLightQuery.SetSharedComponentFilter(new UpdateFrame(SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16)));
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateStreetLightsJob
		{
			m_EntityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PseudoRandomSeedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ElectricityNodeConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ElectricityConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoadType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Road_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WatercraftType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Watercraft_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedFlowEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_ElectricityFlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityNodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StreetLightData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_StreetLight_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Brightness = Mathf.RoundToInt(m_LightingSystem.dayLightBrightness * 1000f),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_StreetLightQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```

- `public static UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Net.Road road) : System.Void`  

```csharp
public static void UpdateStreetLightState(ref StreetLight streetLight, Watercraft watercraft)
	{
		if ((watercraft.m_Flags & WatercraftFlags.LightsOff) != 0)
		{
			streetLight.m_State |= StreetLightState.TurnedOff;
		}
		else
		{
			streetLight.m_State &= ~StreetLightState.TurnedOff;
		}
	}
```

- `public static UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Buildings.Building building) : System.Void`  

```csharp
public static void UpdateStreetLightState(ref StreetLight streetLight, Watercraft watercraft)
	{
		if ((watercraft.m_Flags & WatercraftFlags.LightsOff) != 0)
		{
			streetLight.m_State |= StreetLightState.TurnedOff;
		}
		else
		{
			streetLight.m_State &= ~StreetLightState.TurnedOff;
		}
	}
```

- `public static UpdateStreetLightState(Game.Objects.StreetLight& streetLight, Game.Vehicles.Watercraft watercraft) : System.Void`  

```csharp
public static void UpdateStreetLightState(ref StreetLight streetLight, Watercraft watercraft)
	{
		if ((watercraft.m_Flags & WatercraftFlags.LightsOff) != 0)
		{
			streetLight.m_State |= StreetLightState.TurnedOff;
		}
		else
		{
			streetLight.m_State &= ~StreetLightState.TurnedOff;
		}
	}
```


## Nested types

- `Game.Simulation.StreetLightSystem+UpdateStreetLightsJob`  
- `Game.Simulation.StreetLightSystem+TypeHandle`  

