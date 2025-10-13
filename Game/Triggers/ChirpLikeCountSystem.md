# Game.Triggers.ChirpLikeCountSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ChirpLikeCountSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Game.Triggers.ChirpLikeCountSystem+TypeHandle __TypeHandle;

    public ChirpLikeCountSystem();

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

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Game.Triggers.ChirpLikeCountSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.ChirpLikeCountSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ChirpLikeCountSystem()`  

```csharp
[Preserve]
	public ChirpLikeCountSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ChirpQuery = GetEntityQuery(ComponentType.ReadWrite<Chirp>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_ChirpQuery);
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
		LikeCountUpdateJob jobData = new LikeCountUpdateJob
		{
			m_ChirpType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Triggers_Chirp_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_SimulationFrame = m_SimulationSystem.frameIndex
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ChirpQuery, base.Dependency);
	}
```


## Nested types

- `Game.Triggers.ChirpLikeCountSystem+LikeCountUpdateJob`  
- `Game.Triggers.ChirpLikeCountSystem+TypeHandle`  

