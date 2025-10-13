# Game.Debug.LightDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class LightDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_LightEffectPrefabQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_SpotOption;
    private Game.Debug.BaseDebugSystem+Option m_PositionOption;

    public LightDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LightEffectPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_LightEffectPrefabQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_SpotOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_SpotOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_PositionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PositionOption;
```


## Constructors

- `public LightDebugSystem()`  

```csharp
[Preserve]
	public LightDebugSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_LightEffectPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<LightEffectData>(), ComponentType.ReadOnly<PrefabData>());
		m_PositionOption = AddOption("Show positions", defaultEnabled: false);
		m_SpotOption = AddOption("Spot Lights Cones", defaultEnabled: false);
		base.Enabled = false;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		HDRPDotsInputs.punctualLightsJobHandle.Complete();
		if (HDRPDotsInputs.s_punctualLightdata.Length != 0)
		{
			JobHandle dependencies;
			LightGizmoJob jobData = new LightGizmoJob
			{
				m_SpotOption = m_SpotOption.enabled,
				m_PositionOption = m_PositionOption.enabled,
				m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
			};
			jobData.m_punctualLights = new NativeArray<HDRPDotsInputs.PunctualLightData>(HDRPDotsInputs.s_punctualLightdata.AsArray(), Allocator.Persistent);
			JobHandle jobHandle = IJobExtensions.Schedule(jobData, dependencies);
			m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Debug.LightDebugSystem+LightGizmoJob`  

