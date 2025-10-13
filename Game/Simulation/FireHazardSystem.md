# Game.Simulation.FireHazardSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FireHazardSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_FlammableQuery;
    private Unity.Entities.EntityQuery m_FirePrefabQuery;
    private Unity.Entities.EntityQuery m_FireConfigQuery;
    private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
    private System.Single <noRainDays>k__BackingField;
    private Game.Simulation.FireHazardSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATES_PER_DAY;

    public System.Single noRainDays { get; private set; }

    public FireHazardSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_FlammableQuery`  

```csharp
private Unity.Entities.EntityQuery m_FlammableQuery;
```

- `private Unity.Entities.EntityQuery m_FirePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_FirePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_FireConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireConfigQuery;
```

- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  

```csharp
private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
```

- `private System.Single <noRainDays>k__BackingField`  

```csharp
private System.Single <noRainDays>k__BackingField;
```

- `private Game.Simulation.FireHazardSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FireHazardSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATES_PER_DAY`  

```csharp
private static const System.Int32 UPDATES_PER_DAY;
```


## Properties

- `public System.Single noRainDays { get; private set }`  

```csharp
public System.Single noRainDays { get; private set; }
```


## Constructors

- `public FireHazardSystem()`  

```csharp
[Preserve]
	public FireHazardSystem()
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

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
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
		m_LocalEffectSystem = base.World.GetOrCreateSystemManaged<LocalEffectSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_FlammableQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Tree>()
			},
			None = new ComponentType[7]
			{
				ComponentType.ReadOnly<Game.Buildings.FireStation>(),
				ComponentType.ReadOnly<Placeholder>(),
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadOnly<OnFire>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Overridden>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_FirePrefabQuery = GetEntityQuery(ComponentType.ReadOnly<EventData>(), ComponentType.ReadOnly<FireData>(), ComponentType.Exclude<Locked>());
		m_FireConfigQuery = GetEntityQuery(ComponentType.ReadOnly<FireConfigurationData>());
		m_FireHazardData = new EventHelpers.FireHazardData(this);
		RequireForUpdate(m_FlammableQuery);
		RequireForUpdate(m_FirePrefabQuery);
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
		if (m_ClimateSystem.isRaining)
		{
			noRainDays = 0f;
		}
		else
		{
			noRainDays += 1f / 64f;
		}
		JobHandle dependencies;
		LocalEffectSystem.ReadData readData = m_LocalEffectSystem.GetReadData(out dependencies);
		FireConfigurationPrefab prefab = m_PrefabSystem.GetPrefab<FireConfigurationPrefab>(m_FireConfigQuery.GetSingletonEntity());
		m_FireHazardData.Update(this, readData, prefab, m_ClimateSystem.temperature, noRainDays);
		JobHandle outJobHandle;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new FireHazardJob
		{
			m_FirePrefabChunks = m_FirePrefabQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TreeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DamagedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnderConstructionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabEventType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_EventData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabFireType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_FireData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LockedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FireHazardData = m_FireHazardData,
			m_RandomSeed = RandomSeed.Next(),
			m_NaturalDisasters = m_CityConfigurationSystem.naturalDisasters,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_FlammableQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle, dependencies));
		m_LocalEffectSystem.AddLocalEffectReader(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		noRainDays = 0f;
	}
```


## Nested types

- `Game.Simulation.FireHazardSystem+FireHazardJob`  
- `Game.Simulation.FireHazardSystem+TypeHandle`  

