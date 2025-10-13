# Game.Simulation.WaterLevelChangeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterLevelChangeSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_WaterLevelChangeQuery;
    private Game.Simulation.WaterLevelChangeSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdateInterval;

    public static System.Int32 TsunamiEndDelay { get; }

    public WaterLevelChangeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.UInt32 GetMinimumDelayAt(Game.Events.WaterLevelChange change, Unity.Mathematics.float3 position);
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

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_WaterLevelChangeQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterLevelChangeQuery;
```

- `private Game.Simulation.WaterLevelChangeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterLevelChangeSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdateInterval`  

```csharp
public static readonly System.Int32 kUpdateInterval;
```


## Properties

- `public static System.Int32 TsunamiEndDelay { get }`  

```csharp
public static System.Int32 TsunamiEndDelay { get; }
```


## Constructors

- `public WaterLevelChangeSystem()`  

```csharp
[Preserve]
	public WaterLevelChangeSystem()
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

- `public static GetMinimumDelayAt(Game.Events.WaterLevelChange change, Unity.Mathematics.float3 position) : System.UInt32`  

```csharp
public static uint GetMinimumDelayAt(WaterLevelChange change, float3 position)
	{
		float2 @float = WaterSystem.kMapSize / 2 * new float2(math.cos(0f - change.m_Direction.x), math.sin(0f - change.m_Direction.y));
		float2 float2 = new float2(change.m_Direction.y, 0f - change.m_Direction.x);
		float2 float3 = math.dot(float2, position.xz - @float) * float2;
		return (uint)Mathf.RoundToInt(math.length(position.xz - @float - float3) / WaterSystem.WaveSpeed);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return kUpdateInterval;
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
		m_WaterLevelChangeQuery = GetEntityQuery(ComponentType.ReadWrite<WaterLevelChange>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_WaterLevelChangeQuery);
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
		WaterLevelChangeJob jobData = new WaterLevelChangeJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterLevelChangeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_WaterLevelChange_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DurationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Duration_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabWaterLevelChangeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterLevelChangeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SimulationFrame = m_SimulationSystem.frameIndex
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_WaterLevelChangeQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.WaterLevelChangeSystem+WaterLevelChangeJob`  
- `Game.Simulation.WaterLevelChangeSystem+TypeHandle`  

