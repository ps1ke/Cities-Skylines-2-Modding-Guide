# Game.Debug.LaneDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_StandaloneOption;
    private Game.Debug.BaseDebugSystem+Option m_SlaveOption;
    private Game.Debug.BaseDebugSystem+Option m_MasterOption;
    private Game.Debug.BaseDebugSystem+Option m_ConnectionOption;
    private Game.Debug.BaseDebugSystem+Option m_OverlapOption;
    private Game.Debug.BaseDebugSystem+Option m_ReservedOption;
    private Game.Debug.BaseDebugSystem+Option m_BlockageOption;
    private Game.Debug.BaseDebugSystem+Option m_ConditionOption;
    private Game.Debug.BaseDebugSystem+Option m_SignalsOption;
    private Game.Debug.BaseDebugSystem+Option m_PriorityOption;
    private Game.Debug.LaneDebugSystem+TypeHandle __TypeHandle;

    public LaneDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_StandaloneOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StandaloneOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_SlaveOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SlaveOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MasterOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MasterOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ConnectionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ConnectionOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_OverlapOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_OverlapOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ReservedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ReservedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_BlockageOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_BlockageOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ConditionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ConditionOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_SignalsOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SignalsOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_PriorityOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PriorityOption;
```

- `private Game.Debug.LaneDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.LaneDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneDebugSystem()`  

```csharp
[Preserve]
	public LaneDebugSystem()
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
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_LaneQuery = GetEntityQuery(ComponentType.ReadOnly<Lane>(), ComponentType.ReadOnly<Curve>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Hidden>());
		RequireForUpdate(m_LaneQuery);
		m_StandaloneOption = AddOption("Standalone Lanes", defaultEnabled: true);
		m_SlaveOption = AddOption("Slave Lanes", defaultEnabled: true);
		m_MasterOption = AddOption("Master Lanes", defaultEnabled: false);
		m_ConnectionOption = AddOption("Connection Lanes", defaultEnabled: false);
		m_OverlapOption = AddOption("Draw Overlaps", defaultEnabled: false);
		m_ReservedOption = AddOption("Draw Reserved", defaultEnabled: true);
		m_BlockageOption = AddOption("Draw Blocked", defaultEnabled: true);
		m_ConditionOption = AddOption("Draw Condition", defaultEnabled: false);
		m_SignalsOption = AddOption("Draw Signals", defaultEnabled: false);
		m_PriorityOption = AddOption("Draw Priorities", defaultEnabled: false);
		base.Enabled = false;
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
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new LaneGizmoJob
		{
			m_StandaloneOption = m_StandaloneOption.enabled,
			m_SlaveOption = m_SlaveOption.enabled,
			m_MasterOption = m_MasterOption.enabled,
			m_ConnectionOption = m_ConnectionOption.enabled,
			m_OverlapOption = m_OverlapOption.enabled,
			m_ReservedOption = m_ReservedOption.enabled,
			m_BlockageOption = m_BlockageOption.enabled,
			m_ConditionOption = m_ConditionOption.enabled,
			m_SignalsOption = m_SignalsOption.enabled,
			m_PriorityOption = m_PriorityOption.enabled,
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkingLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PedestrianLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectionLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MasterLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SlaveLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneReservationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LaneReservation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneConditionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LaneCondition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneSignalType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LaneSignal_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_LaneOverlapType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LaneOverlap_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
		}, m_LaneQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Debug.LaneDebugSystem+LaneGizmoJob`  
- `Game.Debug.LaneDebugSystem+TypeHandle`  

