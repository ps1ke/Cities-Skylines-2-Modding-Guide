# Game.Debug.AudioGroupingDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AudioGroupingDebugSystem : Game.GameSystemBase
{
    private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem;
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery;
    private Game.Debug.AudioGroupingDebugSystem+TypeHandle __TypeHandle;

    public AudioGroupingDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
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

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery;
```

- `private Game.Debug.AudioGroupingDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.AudioGroupingDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AudioGroupingDebugSystem()`  

```csharp
[Preserve]
	public AudioGroupingDebugSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_TrafficAmbienceSystem = base.World.GetOrCreateSystemManaged<TrafficAmbienceSystem>();
		m_ZoneAmbienceSystem = base.World.GetOrCreateSystemManaged<ZoneAmbienceSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		base.Enabled = false;
		m_AudioGroupingConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<AudioGroupingSettingsData>());
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
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		AudioGroupingGizmoJob jobData = new AudioGroupingGizmoJob
		{
			m_SettingsEntity = m_AudioGroupingConfigurationQuery.GetSingletonEntity(),
			m_Settings = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AudioGroupingSettingsData_RO_BufferLookup, ref base.CheckedStateRef),
			m_TrafficMap = m_TrafficAmbienceSystem.GetMap(readOnly: true, out dependencies),
			m_ZoneMap = m_ZoneAmbienceSystem.GetMap(readOnly: true, out dependencies2),
			m_HeightData = m_TerrainSystem.GetHeightData(),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies3)
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, dependencies3, JobHandle.CombineDependencies(dependencies2, dependencies)));
		m_TrafficAmbienceSystem.AddReader(base.Dependency);
		m_ZoneAmbienceSystem.AddReader(base.Dependency);
		m_GizmosSystem.AddGizmosBatcherWriter(base.Dependency);
	}
```


## Nested types

- `Game.Debug.AudioGroupingDebugSystem+AudioGroupingGizmoJob`  
- `Game.Debug.AudioGroupingDebugSystem+TypeHandle`  

