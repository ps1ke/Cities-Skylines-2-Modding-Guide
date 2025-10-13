# Game.Simulation.ObsoleteChirpSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObsoleteChirpSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Unity.Entities.EntityQuery m_LimitSettingQuery;
    private Game.Simulation.ObsoleteChirpSystem+TypeHandle __TypeHandle;

    public ObsoleteChirpSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Unity.Entities.EntityQuery m_LimitSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_LimitSettingQuery;
```

- `private Game.Simulation.ObsoleteChirpSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ObsoleteChirpSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObsoleteChirpSystem()`  

```csharp
[Preserve]
	public ObsoleteChirpSystem()
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
		return 65536;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ChirpQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Triggers.Chirp>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Game.Triggers.LifePathEvent>(), ComponentType.Exclude<Temp>());
		m_LimitSettingQuery = GetEntityQuery(ComponentType.ReadOnly<LimitSettingData>());
		RequireForUpdate(m_ChirpQuery);
		RequireForUpdate(m_LimitSettingQuery);
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
		if (m_ChirpQuery.CalculateEntityCount() > m_LimitSettingQuery.GetSingleton<LimitSettingData>().m_MaxChirpsLimit)
		{
			ObsoleteChirpJob jobData = new ObsoleteChirpJob
			{
				m_Entities = m_ChirpQuery.ToEntityArray(Allocator.TempJob),
				m_Chirps = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Triggers_Chirp_RW_ComponentLookup, ref base.CheckedStateRef),
				m_LimitSettingData = m_LimitSettingQuery.GetSingleton<LimitSettingData>(),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
			};
			base.Dependency = IJobExtensions.Schedule(jobData, base.Dependency);
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.ObsoleteChirpSystem+ObsoleteChirpJob`  
- `Game.Simulation.ObsoleteChirpSystem+ChirpComparer`  
- `Game.Simulation.ObsoleteChirpSystem+TypeHandle`  

