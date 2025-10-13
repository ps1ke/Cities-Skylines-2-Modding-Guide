# Game.Simulation.WetnessSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WetnessSystem : Game.GameSystemBase
{
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_SurfaceQuery;
    private Unity.Entities.EntityArchetype m_SubObjectEventArchetype;
    private Game.Simulation.WetnessSystem+TypeHandle __TypeHandle;
    public static const System.Int32 SNOW_REQUIREMENT_LIMIT;

    public WetnessSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_SurfaceQuery`  

```csharp
private Unity.Entities.EntityQuery m_SurfaceQuery;
```

- `private Unity.Entities.EntityArchetype m_SubObjectEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_SubObjectEventArchetype;
```

- `private Game.Simulation.WetnessSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WetnessSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 SNOW_REQUIREMENT_LIMIT`  

```csharp
public static const System.Int32 SNOW_REQUIREMENT_LIMIT;
```


## Constructors

- `public WetnessSystem()`  

```csharp
[Preserve]
	public WetnessSystem()
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
		return 256;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SurfaceQuery = GetEntityQuery(ComponentType.ReadWrite<Surface>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Overridden>(), ComponentType.Exclude<Temp>());
		m_SubObjectEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<SubObjectsUpdated>());
		RequireForUpdate(m_SurfaceQuery);
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
		float4 x = default(float4);
		float4 x2 = default(float4);
		float4 x3 = default(float4);
		float num = m_ClimateSystem.precipitation;
		float num2 = m_ClimateSystem.temperature;
		if (num2 > 0f)
		{
			x.x = math.sqrt(num);
			x.z = math.sqrt(x.x);
			x2.x = num * 0.1f;
			x2.z = num * 0.01f;
			x3.x = (1f - num) * 0.05f;
			x3.y = num2 * 0.01f;
			x3.z = (1f - num) * 0.005f;
			x3.w = num2 * 0.001f;
		}
		else
		{
			x.yw = 1f;
			x2.y = num * 0.05f;
			x2.w = num * 0.005f;
			x3.x = num2 * -0.01f;
			x3.z = num2 * -0.001f;
		}
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new WetnessJob
		{
			m_EntityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ObjectSurfaceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Surface_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjectEventArchetype = m_SubObjectEventArchetype,
			m_RandomSeed = RandomSeed.Next(),
			m_TargetWetness = math.saturate(x),
			m_WetSpeed = math.saturate(x2),
			m_DrySpeed = -math.saturate(x3),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_SurfaceQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.WetnessSystem+WetnessJob`  
- `Game.Simulation.WetnessSystem+TypeHandle`  

