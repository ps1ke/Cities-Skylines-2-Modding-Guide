# Game.Simulation.CityDangerLevelSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityDangerLevelSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_DangerLevelQuery;
    private Game.Simulation.CityDangerLevelSystem+TypeHandle __TypeHandle;

    public CityDangerLevelSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_DangerLevelQuery`  

```csharp
private Unity.Entities.EntityQuery m_DangerLevelQuery;
```

- `private Game.Simulation.CityDangerLevelSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CityDangerLevelSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CityDangerLevelSystem()`  

```csharp
[Preserve]
	public CityDangerLevelSystem()
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
		return 128;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_DangerLevelQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Events.DangerLevel>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate<Game.City.DangerLevel>();
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
		NativeAccumulator<MaxFloat> result = new NativeAccumulator<MaxFloat>(Allocator.TempJob);
		if (!m_DangerLevelQuery.IsEmptyIgnoreFilter)
		{
			DangerLevelJob jobData = new DangerLevelJob
			{
				m_DangerLevelType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_DangerLevel_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Result = result.AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_DangerLevelQuery, base.Dependency);
		}
		UpdateCityJob jobData2 = new UpdateCityJob
		{
			m_DangerLevel = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_DangerLevel_RW_ComponentLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_Result = result
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
		result.Dispose(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.CityDangerLevelSystem+DangerLevelJob`  
- `Game.Simulation.CityDangerLevelSystem+UpdateCityJob`  
- `Game.Simulation.CityDangerLevelSystem+TypeHandle`  

