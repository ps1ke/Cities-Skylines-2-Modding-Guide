# Game.Simulation.WeatherDamageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WeatherDamageSystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_FacingQuery;
    private Unity.Entities.EntityQuery m_FireConfigQuery;
    private Unity.Entities.EntityQuery m_DisasterConfigQuery;
    private Unity.Entities.EntityArchetype m_DamageEventArchetype;
    private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
    private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
    private Game.Simulation.WeatherDamageSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public WeatherDamageSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_FacingQuery`  

```csharp
private Unity.Entities.EntityQuery m_FacingQuery;
```

- `private Unity.Entities.EntityQuery m_FireConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireConfigQuery;
```

- `private Unity.Entities.EntityQuery m_DisasterConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_DisasterConfigQuery;
```

- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DamageEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
```

- `private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData`  

```csharp
private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
```

- `private Game.Simulation.WeatherDamageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WeatherDamageSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public WeatherDamageSystem()`  

```csharp
[Preserve]
	public WeatherDamageSystem()
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
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_FacingQuery = GetEntityQuery(ComponentType.ReadWrite<FacingWeather>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_FireConfigQuery = GetEntityQuery(ComponentType.ReadOnly<FireConfigurationData>());
		m_DisasterConfigQuery = GetEntityQuery(ComponentType.ReadOnly<DisasterConfigurationData>());
		m_DamageEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Damage>());
		m_DestroyEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Destroy>());
		m_StructuralIntegrityData = new EventHelpers.StructuralIntegrityData(this);
		RequireForUpdate(m_FacingQuery);
		RequireForUpdate(m_FireConfigQuery);
		RequireForUpdate(m_DisasterConfigQuery);
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
		FireConfigurationData singleton = m_FireConfigQuery.GetSingleton<FireConfigurationData>();
		DisasterConfigurationData singleton2 = m_DisasterConfigQuery.GetSingleton<DisasterConfigurationData>();
		m_StructuralIntegrityData.Update(this, singleton);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new WeatherDamageJob
		{
			m_DamageEventArchetype = m_DamageEventArchetype,
			m_DestroyEventArchetype = m_DestroyEventArchetype,
			m_DisasterConfigurationData = singleton2,
			m_StructuralIntegrityData = m_StructuralIntegrityData,
			m_City = m_CitySystem.City,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FacingWeatherType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_FacingWeather_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DamagedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Damaged_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WeatherPhenomenonData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_WeatherPhenomenon_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWeatherPhenomenonData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WeatherPhenomenonData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef)
		}, m_FacingQuery, base.Dependency);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.WeatherDamageSystem+WeatherDamageJob`  
- `Game.Simulation.WeatherDamageSystem+TypeHandle`  

