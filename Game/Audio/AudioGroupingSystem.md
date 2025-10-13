# Game.Audio.AudioGroupingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AudioGroupingSystem : Game.GameSystemBase
{
    private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem;
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery;
    private Unity.Entities.EntityQuery m_AudioGroupingMiscSettingQuery;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_AmbienceEntities;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_NearAmbienceEntities;
    private Unity.Collections.NativeArray<Game.Prefabs.AudioGroupingSettingsData> m_Settings;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_OnFireTreeQuery;
    private Unity.Collections.NativeArray<System.Single> m_CurrentValues;
    private Game.Audio.AudioGroupingSystem+TypeHandle __TypeHandle;

    public AudioGroupingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Entities.Entity CreateEffect(Unity.Entities.Entity sfx);
    private System.Void Initialize();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem`  

```csharp
private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem;
```

- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  

```csharp
private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
```

- `private Game.Effects.EffectFlagSystem m_EffectFlagSystem`  

```csharp
private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_AudioGroupingMiscSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_AudioGroupingMiscSettingQuery;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_AmbienceEntities`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_AmbienceEntities;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_NearAmbienceEntities`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_NearAmbienceEntities;
```

- `private Unity.Collections.NativeArray<Game.Prefabs.AudioGroupingSettingsData> m_Settings`  

```csharp
private Unity.Collections.NativeArray<Game.Prefabs.AudioGroupingSettingsData> m_Settings;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_OnFireTreeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OnFireTreeQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_CurrentValues`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_CurrentValues;
```

- `private Game.Audio.AudioGroupingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Audio.AudioGroupingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AudioGroupingSystem()`  

```csharp
[Preserve]
	public AudioGroupingSystem()
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

- `private CreateEffect(Unity.Entities.Entity sfx) : Unity.Entities.Entity`  

```csharp
private Entity CreateEffect(Entity sfx)
	{
		Entity entity = base.EntityManager.CreateEntity();
		base.EntityManager.AddComponentData(entity, default(EffectInstance));
		base.EntityManager.AddComponentData(entity, new PrefabRef
		{
			m_Prefab = sfx
		});
		return entity;
	}
```

- `private Initialize() : System.Void`  

```csharp
private void Initialize()
	{
		NativeArray<Entity> nativeArray = m_AudioGroupingConfigurationQuery.ToEntityArray(Allocator.Temp);
		List<AudioGroupingSettingsData> list = new List<AudioGroupingSettingsData>();
		foreach (Entity item in nativeArray)
		{
			list.AddRange(base.World.EntityManager.GetBuffer<AudioGroupingSettingsData>(item, isReadOnly: true).AsNativeArray());
		}
		if (!m_Settings.IsCreated)
		{
			m_Settings = list.ToNativeArray(Allocator.Persistent);
		}
		nativeArray.Dispose();
		if (!m_AmbienceEntities.IsCreated)
		{
			m_AmbienceEntities = new NativeArray<Entity>(m_Settings.Length, Allocator.Persistent);
		}
		if (!m_NearAmbienceEntities.IsCreated)
		{
			m_NearAmbienceEntities = new NativeArray<Entity>(m_Settings.Length, Allocator.Persistent);
		}
		for (int i = 0; i < m_Settings.Length; i++)
		{
			m_AmbienceEntities[i] = CreateEffect(m_Settings[i].m_GroupSoundFar);
			m_NearAmbienceEntities[i] = ((m_Settings[i].m_GroupSoundNear != Entity.Null) ? CreateEffect(m_Settings[i].m_GroupSoundNear) : Entity.Null);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_TrafficAmbienceSystem = base.World.GetOrCreateSystemManaged<TrafficAmbienceSystem>();
		m_ZoneAmbienceSystem = base.World.GetOrCreateSystemManaged<ZoneAmbienceSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_EffectFlagSystem = base.World.GetOrCreateSystemManaged<EffectFlagSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_CurrentValues = new NativeArray<float>(22, Allocator.Persistent);
		m_AudioGroupingConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<AudioGroupingSettingsData>());
		m_AudioGroupingMiscSettingQuery = GetEntityQuery(ComponentType.ReadOnly<AudioGroupingMiscSetting>());
		m_OnFireTreeQuery = GetEntityQuery(ComponentType.ReadOnly<Tree>(), ComponentType.ReadOnly<OnFire>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_AudioGroupingConfigurationQuery);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		if (m_AmbienceEntities.IsCreated)
		{
			m_AmbienceEntities.Dispose();
		}
		if (m_NearAmbienceEntities.IsCreated)
		{
			m_NearAmbienceEntities.Dispose();
		}
		if (m_Settings.IsCreated)
		{
			m_Settings.Dispose();
		}
		m_CurrentValues.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (GameManager.instance.gameMode == GameMode.Game && !GameManager.instance.isGameLoading)
		{
			if (m_AmbienceEntities.Length == 0 || !base.EntityManager.HasComponent<EffectInstance>(m_AmbienceEntities[0]))
			{
				Initialize();
			}
			Camera main = Camera.main;
			if (!(main == null))
			{
				float3 cameraPosition = main.transform.position;
				AudioGroupingMiscSetting singleton = m_AudioGroupingMiscSettingQuery.GetSingleton<AudioGroupingMiscSetting>();
				JobHandle deps;
				JobHandle dependencies;
				JobHandle dependencies2;
				AudioGroupingJob jobData = new AudioGroupingJob
				{
					m_CameraPosition = cameraPosition,
					m_SourceUpdateData = m_AudioManager.GetSourceUpdateData(out deps),
					m_TrafficAmbienceMap = m_TrafficAmbienceSystem.GetMap(readOnly: true, out dependencies),
					m_AmbienceMap = m_ZoneAmbienceSystem.GetMap(readOnly: true, out dependencies2),
					m_Settings = m_Settings,
					m_EffectFlagData = m_EffectFlagSystem.GetData(),
					m_AmbienceEntities = m_AmbienceEntities,
					m_NearAmbienceEntities = m_NearAmbienceEntities,
					m_OnFireTrees = m_OnFireTreeQuery.ToEntityArray(Allocator.TempJob),
					m_EffectInstances = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Effects_EffectInstance_RW_ComponentLookup, ref base.CheckedStateRef),
					m_EffectDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EffectData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TerrainData = m_TerrainSystem.GetHeightData(),
					m_ForestFireDistance = singleton.m_ForestFireDistance,
					m_Precipitation = m_ClimateSystem.precipitation,
					m_IsRaining = m_ClimateSystem.isRaining,
					m_CurrentValues = m_CurrentValues
				};
				base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(JobHandle.CombineDependencies(dependencies2, deps), dependencies, base.Dependency));
				m_TerrainSystem.AddCPUHeightReader(base.Dependency);
				m_AudioManager.AddSourceUpdateWriter(base.Dependency);
				m_TrafficAmbienceSystem.AddReader(base.Dependency);
			}
		}
	}
```


## Nested types

- `Game.Audio.AudioGroupingSystem+AudioGroupingJob`  
- `Game.Audio.AudioGroupingSystem+TypeHandle`  

