# Game.Simulation.RoadSafetySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoadSafetySystem : Game.GameSystemBase
{
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_RoadQuery;
    private Unity.Entities.EntityQuery m_AccidentPrefabQuery;
    private Game.Simulation.RoadSafetySystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATES_PER_DAY;

    public RoadSafetySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_RoadQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoadQuery;
```

- `private Unity.Entities.EntityQuery m_AccidentPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_AccidentPrefabQuery;
```

- `private Game.Simulation.RoadSafetySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.RoadSafetySystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATES_PER_DAY`  

```csharp
private static const System.Int32 UPDATES_PER_DAY;
```


## Constructors

- `public RoadSafetySystem()`  

```csharp
[Preserve]
	public RoadSafetySystem()
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
		return 4096;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_LightingSystem = base.World.GetOrCreateSystemManaged<LightingSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_RoadQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadOnly<Composition>()
			},
			Any = new ComponentType[1] { ComponentType.ReadOnly<Road>() },
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_AccidentPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<EventData>(), ComponentType.ReadOnly<TrafficAccidentData>(), ComponentType.Exclude<Locked>());
		RequireForUpdate(m_RoadQuery);
		RequireForUpdate(m_AccidentPrefabQuery);
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
		float num = m_TimeSystem.normalizedTime * 4f;
		float4 x = new float4(math.max(num - 3f, 1f - num), 1f - math.abs(num - new float3(1f, 2f, 3f)));
		x = math.saturate(x);
		JobHandle outJobHandle;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new RoadSafetyJob
		{
			m_FirePrefabChunks = m_AccidentPrefabQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_NetConditionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NetCondition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoadType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Road_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BorderDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_BorderDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabEventType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_EventData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabTrafficAccidentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TrafficAccidentData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LockedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoadCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_DistrictModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_DistrictModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_RandomSeed = RandomSeed.Next(),
			m_TimeFactors = x,
			m_Brightness = m_LightingSystem.dayLightBrightness,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_RoadQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.RoadSafetySystem+RoadSafetyJob`  
- `Game.Simulation.RoadSafetySystem+TypeHandle`  

