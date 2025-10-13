# Game.Triggers.EarlyGameOutsideConnectionTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EarlyGameOutsideConnectionTriggerSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ResourceAvailabilitySystem m_ResourceAvailabilitySystem;
    private System.Boolean m_Started;
    private System.Double m_StartTime;
    private System.Boolean m_Triggered;
    private Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle __TypeHandle;
    private static readonly System.Single kDelaySeconds;
    private static const System.UInt32 UPDATE_INTERVAL;

    public EarlyGameOutsideConnectionTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ResourceAvailabilitySystem m_ResourceAvailabilitySystem`  

```csharp
private Game.Simulation.ResourceAvailabilitySystem m_ResourceAvailabilitySystem;
```

- `private System.Boolean m_Started`  

```csharp
private System.Boolean m_Started;
```

- `private System.Double m_StartTime`  

```csharp
private System.Double m_StartTime;
```

- `private System.Boolean m_Triggered`  

```csharp
private System.Boolean m_Triggered;
```

- `private Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single kDelaySeconds`  

```csharp
private static readonly System.Single kDelaySeconds;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public EarlyGameOutsideConnectionTriggerSystem()`  

```csharp
[Preserve]
	public EarlyGameOutsideConnectionTriggerSystem()
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
		return 64;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<BuildingCondition>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ResourceAvailabilitySystem = base.World.GetOrCreateSystemManaged<ResourceAvailabilitySystem>();
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (serializationContext.purpose == Purpose.NewGame)
		{
			m_Started = false;
			m_StartTime = 0.0;
			m_Triggered = false;
		}
		else
		{
			m_Triggered = true;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_BuildingQuery.IsEmptyIgnoreFilter && !m_Triggered)
		{
			if (!m_Started)
			{
				m_StartTime = m_SimulationSystem.frameIndex;
				m_Started = true;
			}
			if (m_ResourceAvailabilitySystem.appliedResource == AvailableResource.OutsideConnection && (double)m_SimulationSystem.frameIndex - m_StartTime > (double)(kDelaySeconds * 60f))
			{
				TriggerJob jobData = new TriggerJob
				{
					m_Buildings = m_BuildingQuery.ToComponentDataArray<Building>(Allocator.TempJob),
					m_AvailabilityDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferLookup, ref base.CheckedStateRef),
					m_ActionBuffer = m_TriggerSystem.CreateActionBuffer()
				};
				base.Dependency = IJobExtensions.Schedule(jobData, base.Dependency);
				m_TriggerSystem.AddActionBufferWriter(base.Dependency);
				m_Triggered = true;
			}
		}
		if (m_BuildingQuery.IsEmptyIgnoreFilter && m_Started && !m_Triggered)
		{
			m_Started = false;
		}
	}
```


## Nested types

- `Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TriggerJob`  
- `Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle`  

