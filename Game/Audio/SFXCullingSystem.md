# Game.Audio.SFXCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SFXCullingSystem : Game.GameSystemBase
{
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Unity.Entities.EntityQuery m_CullingAudioSettingsQuery;
    private Game.Audio.SFXCullingSystem+TypeHandle __TypeHandle;

    public SFXCullingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Unity.Entities.EntityQuery m_CullingAudioSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_CullingAudioSettingsQuery;
```

- `private Game.Audio.SFXCullingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Audio.SFXCullingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SFXCullingSystem()`  

```csharp
[Preserve]
	public SFXCullingSystem()
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
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_EffectControlSystem = base.World.GetOrCreateSystemManaged<EffectControlSystem>();
		m_CullingAudioSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<CullingAudioSettingsData>());
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
		Camera main = Camera.main;
		if (!(main == null))
		{
			int num = 4;
			NativeParallelQueue<CullingGroupItem> nativeParallelQueue = new NativeParallelQueue<CullingGroupItem>(num, Allocator.TempJob);
			JobHandle dependencies;
			NativeList<EnabledEffectData> enabledData = m_EffectControlSystem.GetEnabledData(readOnly: false, out dependencies);
			JobHandle deps;
			SourceUpdateData sourceUpdateData = m_AudioManager.GetSourceUpdateData(out deps);
			SFXCullingJob jobData = new SFXCullingJob
			{
				m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CullingGroupData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CullingGroupData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AudioSpotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AudioSpotData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AudioEffectDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AudioEffectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AudioSourceDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AudioSourceData_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabEffects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_Effect_RO_BufferLookup, ref base.CheckedStateRef),
				m_CameraPosition = main.transform.position,
				m_RandomSeed = RandomSeed.Next(),
				m_DeltaTime = UnityEngine.Time.deltaTime,
				m_EnabledData = enabledData,
				m_CullingGroupItems = nativeParallelQueue.AsWriter(),
				m_SourceUpdateData = sourceUpdateData
			};
			base.Dependency = jobData.Schedule(jobData.m_EnabledData, 16, JobHandle.CombineDependencies(dependencies, deps, base.Dependency));
			JobHandle jobHandle = base.Dependency;
			if (!m_CullingAudioSettingsQuery.IsEmptyIgnoreFilter)
			{
				CullingAudioSettingsData singleton = m_CullingAudioSettingsQuery.GetSingleton<CullingAudioSettingsData>();
				jobHandle = IJobParallelForExtensions.Schedule(new SFXGroupCullingJob
				{
					m_MaxAllowedAmount = singleton.m_PublicTransCullMaxAmount,
					m_MaxDistance = singleton.m_PublicTransCullMaxDistance,
					m_CullingGroupItems = nativeParallelQueue.AsReader(),
					m_EnabledData = enabledData,
					m_SourceUpdateData = sourceUpdateData
				}, num, 1, jobHandle);
			}
			nativeParallelQueue.Dispose(jobHandle);
			m_EffectControlSystem.AddEnabledDataWriter(jobHandle);
			m_AudioManager.AddSourceUpdateWriter(jobHandle);
		}
	}
```


## Nested types

- `Game.Audio.SFXCullingSystem+SFXCullingJob`  
- `Game.Audio.SFXCullingSystem+CullingGroupItem`  
- `Game.Audio.SFXCullingSystem+SFXGroupCullingJob`  
- `Game.Audio.SFXCullingSystem+TypeHandle`  

