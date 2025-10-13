# Game.Simulation.NetPollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetPollutionSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_PollutionQuery;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    private Game.Simulation.NetPollutionSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public NetPollutionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_PollutionQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionQuery;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `private Game.Simulation.NetPollutionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.NetPollutionSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public NetPollutionSystem()`  

```csharp
[Preserve]
	public NetPollutionSystem()
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
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_PollutionQuery = GetEntityQuery(ComponentType.ReadWrite<Game.Net.Pollution>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_PollutionParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PollutionParameterData>());
		RequireForUpdate(m_PollutionQuery);
		RequireForUpdate(m_PollutionParameterQuery);
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		m_PollutionQuery.ResetFilter();
		m_PollutionQuery.SetSharedComponentFilter(new UpdateFrame(updateFrame));
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = JobChunkExtensions.Schedule(new UpdateNetPollutionJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpgradedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ElevationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectedEdgeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PollutionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Pollution_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetPollutionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetPollutionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AirPollutionMap = m_AirPollutionSystem.GetMap(readOnly: false, out dependencies),
			m_NoisePollutionMap = m_NoisePollutionSystem.GetMap(readOnly: false, out dependencies2),
			m_AirPollutionTextureSize = AirPollutionSystem.kTextureSize,
			m_NoisePollutionTextureSize = NoisePollutionSystem.kTextureSize,
			m_MapSize = CellMapSystem<AirPollution>.kMapSize,
			m_PollutionParameters = m_PollutionParameterQuery.GetSingleton<PollutionParameterData>()
		}, m_PollutionQuery, JobHandle.CombineDependencies(dependencies, dependencies2, base.Dependency));
		m_AirPollutionSystem.AddWriter(jobHandle);
		m_NoisePollutionSystem.AddWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.NetPollutionSystem+UpdateNetPollutionJob`  
- `Game.Simulation.NetPollutionSystem+TypeHandle`  

