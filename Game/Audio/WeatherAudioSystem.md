# Game.Audio.WeatherAudioSystem

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WeatherAudioSystem : Game.GameSystemBase
{
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Unity.Entities.EntityQuery m_WeatherAudioEntityQuery;
    private Unity.Entities.Entity m_SmallWaterAudioEntity;
    private System.Int32 m_WaterAudioEnabledZoom;
    private System.Int32 m_WaterAudioNearDistance;
    private Game.Audio.WeatherAudioSystem+TypeHandle __TypeHandle;

    public WeatherAudioSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    private System.Void Initialize();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Unity.Entities.EntityQuery m_WeatherAudioEntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_WeatherAudioEntityQuery;
```

- `private Unity.Entities.Entity m_SmallWaterAudioEntity`  

```csharp
private Unity.Entities.Entity m_SmallWaterAudioEntity;
```

- `private System.Int32 m_WaterAudioEnabledZoom`  

```csharp
private System.Int32 m_WaterAudioEnabledZoom;
```

- `private System.Int32 m_WaterAudioNearDistance`  

```csharp
private System.Int32 m_WaterAudioNearDistance;
```

- `private Game.Audio.WeatherAudioSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Audio.WeatherAudioSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WeatherAudioSystem()`  

```csharp
[Preserve]
	public WeatherAudioSystem()
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
		return 16;
	}
```

- `private Initialize() : System.Void`  

```csharp
private void Initialize()
	{
		WeatherAudioData componentData = base.EntityManager.GetComponentData<WeatherAudioData>(m_WeatherAudioEntityQuery.GetSingletonEntity());
		Entity entity = base.EntityManager.CreateEntity();
		base.EntityManager.AddComponentData(entity, default(EffectInstance));
		base.EntityManager.AddComponentData(entity, new PrefabRef
		{
			m_Prefab = componentData.m_WaterAmbientAudio
		});
		m_SmallWaterAudioEntity = entity;
		m_WaterAudioEnabledZoom = componentData.m_WaterAudioEnabledZoom;
		m_WaterAudioNearDistance = componentData.m_WaterAudioNearDistance;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_WeatherAudioEntityQuery = GetEntityQuery(ComponentType.ReadOnly<WeatherAudioData>());
		RequireForUpdate(m_WeatherAudioEntityQuery);
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
		m_SmallWaterAudioEntity = Entity.Null;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_WaterSystem.Loaded && m_CameraUpdateSystem.activeViewer != null && m_CameraUpdateSystem.activeCameraController != null)
		{
			if (m_SmallWaterAudioEntity == Entity.Null)
			{
				Initialize();
			}
			IGameCameraController activeCameraController = m_CameraUpdateSystem.activeCameraController;
			float3 position = m_CameraUpdateSystem.activeViewer.position;
			if (base.EntityManager.HasComponent<EffectInstance>(m_SmallWaterAudioEntity) && activeCameraController.zoom < (float)m_WaterAudioEnabledZoom)
			{
				JobHandle deps;
				JobHandle deps2;
				WeatherAudioJob jobData = new WeatherAudioJob
				{
					m_WaterTextureSize = m_WaterSystem.TextureSize,
					m_WaterAudioNearDistance = m_WaterAudioNearDistance,
					m_CameraPosition = position,
					m_WaterAudioEntity = m_SmallWaterAudioEntity,
					m_WeatherAudioData = base.EntityManager.GetComponentData<WeatherAudioData>(m_WeatherAudioEntityQuery.GetSingletonEntity()),
					m_SourceUpdateData = m_AudioManager.GetSourceUpdateData(out deps),
					m_TerrainData = m_TerrainSystem.GetHeightData(),
					m_EffectInstances = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Effects_EffectInstance_RW_ComponentLookup, ref base.CheckedStateRef),
					m_WaterDepths = m_WaterSystem.GetDepths(out deps2)
				};
				base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(deps, deps2, base.Dependency));
				m_TerrainSystem.AddCPUHeightReader(base.Dependency);
				m_AudioManager.AddSourceUpdateWriter(base.Dependency);
			}
		}
	}
```


## Nested types

- `Game.Audio.WeatherAudioSystem+WeatherAudioJob`  
- `Game.Audio.WeatherAudioSystem+TypeHandle`  

