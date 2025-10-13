# Game.Rendering.ProceduralUploadSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProceduralUploadSystem : Game.GameSystemBase
{
    private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
    private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.RenderPrefabBase m_OverridePrefab;
    private Colossal.Collections.NativeAccumulator<Game.Rendering.ProceduralUploadSystem+UploadData> m_UploadData;
    private Unity.Jobs.JobHandle m_PrepareDeps;
    private Unity.Entities.Entity m_OverrideEntity;
    private Game.Rendering.LightState m_OverrideLightState;
    private System.Int32 m_OverrideSingleLightIndex;
    private System.Int32 m_OverrideMultiLightIndex;
    private System.Single m_OverrideTime;
    private Game.Rendering.ProceduralUploadSystem+TypeHandle __TypeHandle;

    public ProceduralUploadSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 singleLightIndex, System.Int32 multiLightIndex);
    private System.Void UpdateOverride(Game.Rendering.ProceduralUploadSystem+UploadData& emissiveData);
}
```


## Fields

- `private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem`  

```csharp
private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
```

- `private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem`  

```csharp
private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.RenderPrefabBase m_OverridePrefab`  

```csharp
private Game.Prefabs.RenderPrefabBase m_OverridePrefab;
```

- `private Colossal.Collections.NativeAccumulator<Game.Rendering.ProceduralUploadSystem+UploadData> m_UploadData`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Rendering.ProceduralUploadSystem+UploadData> m_UploadData;
```

- `private Unity.Jobs.JobHandle m_PrepareDeps`  

```csharp
private Unity.Jobs.JobHandle m_PrepareDeps;
```

- `private Unity.Entities.Entity m_OverrideEntity`  

```csharp
private Unity.Entities.Entity m_OverrideEntity;
```

- `private Game.Rendering.LightState m_OverrideLightState`  

```csharp
private Game.Rendering.LightState m_OverrideLightState;
```

- `private System.Int32 m_OverrideSingleLightIndex`  

```csharp
private System.Int32 m_OverrideSingleLightIndex;
```

- `private System.Int32 m_OverrideMultiLightIndex`  

```csharp
private System.Int32 m_OverrideMultiLightIndex;
```

- `private System.Single m_OverrideTime`  

```csharp
private System.Single m_OverrideTime;
```

- `private Game.Rendering.ProceduralUploadSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.ProceduralUploadSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ProceduralUploadSystem()`  

```csharp
[Preserve]
	public ProceduralUploadSystem()
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
		m_ProceduralSkeletonSystem = base.World.GetOrCreateSystemManaged<ProceduralSkeletonSystem>();
		m_ProceduralEmissiveSystem = base.World.GetOrCreateSystemManaged<ProceduralEmissiveSystem>();
		m_PreCullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
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
		m_PrepareDeps.Complete();
		UploadData result = m_UploadData.GetResult();
		UploadData emissiveData = m_UploadData.GetResult(1);
		m_UploadData.Dispose();
		if (m_OverrideEntity != Entity.Null)
		{
			UpdateOverride(ref emissiveData);
		}
		int historyByteOffset;
		JobHandle dependencies;
		ProceduralUploadJob jobData = new ProceduralUploadJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Bones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Bone_RO_BufferLookup, ref base.CheckedStateRef),
			m_Lights = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_LightState_RO_BufferLookup, ref base.CheckedStateRef),
			m_ProceduralBones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralBone_RO_BufferLookup, ref base.CheckedStateRef),
			m_ProceduralLights = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralLight_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_Skeletons = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Skeleton_RW_BufferLookup, ref base.CheckedStateRef),
			m_BoneHistories = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_BoneHistory_RW_BufferLookup, ref base.CheckedStateRef),
			m_Emissives = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Emissive_RW_BufferLookup, ref base.CheckedStateRef),
			m_BoneUploader = m_ProceduralSkeletonSystem.BeginUpload(result.m_OpCount, result.m_DataSize, result.m_MaxOpSize, out historyByteOffset),
			m_LightUploader = m_ProceduralEmissiveSystem.BeginUpload(emissiveData.m_OpCount, emissiveData.m_DataSize, emissiveData.m_MaxOpSize),
			m_HistoryByteOffset = historyByteOffset,
			m_MotionBlurEnabled = m_ProceduralSkeletonSystem.isMotionBlurEnabled,
			m_ForceHistoryUpdate = m_ProceduralSkeletonSystem.forceHistoryUpdate,
			m_CullingData = m_PreCullingSystem.GetCullingData(readOnly: true, out dependencies)
		};
		JobHandle jobHandle = jobData.Schedule(jobData.m_CullingData, 16, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_ProceduralSkeletonSystem.AddUploadWriter(jobHandle);
		m_ProceduralEmissiveSystem.AddUploadWriter(jobHandle);
		m_PreCullingSystem.AddCullingDataReader(jobHandle);
		base.Dependency = jobHandle;
	}
```

- `public SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 singleLightIndex, System.Int32 multiLightIndex) : System.Void`  

```csharp
public void SetOverride(Entity entity, RenderPrefabBase prefab, int singleLightIndex, int multiLightIndex)
	{
		if (entity != m_OverrideEntity || singleLightIndex != m_OverrideSingleLightIndex || multiLightIndex != m_OverrideMultiLightIndex)
		{
			m_OverrideLightState.m_Intensity = -1f;
			m_OverrideTime = 0f;
		}
		m_OverrideEntity = entity;
		m_OverridePrefab = prefab;
		m_OverrideSingleLightIndex = singleLightIndex;
		m_OverrideMultiLightIndex = multiLightIndex;
	}
```

- `private UpdateOverride(Game.Rendering.ProceduralUploadSystem+UploadData& emissiveData) : System.Void`  

```csharp
private unsafe void UpdateOverride(ref UploadData emissiveData)
	{
		if (!base.EntityManager.TryGetBuffer(m_OverrideEntity, isReadOnly: false, out DynamicBuffer<Emissive> buffer) || !base.EntityManager.TryGetBuffer(m_OverrideEntity, isReadOnly: false, out DynamicBuffer<LightState> buffer2) || !base.EntityManager.TryGetComponent<PrefabRef>(m_OverrideEntity, out var component) || !base.EntityManager.TryGetBuffer(component.m_Prefab, isReadOnly: true, out DynamicBuffer<SubMesh> buffer3) || !m_OverridePrefab.TryGet<EmissiveProperties>(out var component2) || !m_PrefabSystem.TryGetEntity(m_OverridePrefab, out var entity))
		{
			return;
		}
		int num = -1;
		if (m_OverrideMultiLightIndex >= 0)
		{
			num = m_OverrideMultiLightIndex;
		}
		else
		{
			if (m_OverrideSingleLightIndex < 0)
			{
				return;
			}
			num = m_OverrideSingleLightIndex;
			if (component2.hasMultiLights)
			{
				num += component2.m_MultiLights.Count;
			}
		}
		float deltaTime = UnityEngine.Time.deltaTime;
		for (int i = 0; i < buffer.Length; i++)
		{
			ref Emissive reference = ref buffer.ElementAt(i);
			if (reference.m_BufferAllocation.Empty)
			{
				continue;
			}
			SubMesh subMesh = buffer3[i];
			if (!(subMesh.m_SubMesh != entity) && base.EntityManager.TryGetBuffer(subMesh.m_SubMesh, isReadOnly: true, out DynamicBuffer<ProceduralLight> buffer4) && num < buffer4.Length)
			{
				if (!reference.m_Updated)
				{
					uint num2 = reference.m_BufferAllocation.Length * (uint)sizeof(float4);
					emissiveData.Accumulate(new UploadData
					{
						m_OpCount = 1,
						m_DataSize = num2,
						m_MaxOpSize = num2
					});
				}
				ProceduralLight proceduralLight = buffer4[num];
				ref LightState reference2 = ref buffer2.ElementAt(reference.m_LightOffset + num);
				if (m_OverrideLightState.m_Intensity < 0f)
				{
					m_OverrideLightState = reference2;
				}
				float2 target = new float2(1f, 0f);
				if (proceduralLight.m_AnimationIndex >= 0 && base.EntityManager.TryGetBuffer(subMesh.m_SubMesh, isReadOnly: true, out DynamicBuffer<LightAnimation> buffer5))
				{
					LightAnimation lightAnimation = buffer5[proceduralLight.m_AnimationIndex];
					m_OverrideTime += deltaTime * 60f;
					m_OverrideTime %= lightAnimation.m_DurationFrames;
					target.x *= lightAnimation.m_AnimationCurve.Evaluate(m_OverrideTime / (float)lightAnimation.m_DurationFrames);
				}
				ObjectInterpolateSystem.AnimateLight(proceduralLight, ref reference, ref m_OverrideLightState, deltaTime, target, instantReset: false);
				reference2 = m_OverrideLightState;
				reference.m_Updated = true;
			}
		}
	}
```


## Nested types

- `Game.Rendering.ProceduralUploadSystem+Prepare`  
- `Game.Rendering.ProceduralUploadSystem+UploadData`  
- `Game.Rendering.ProceduralUploadSystem+ProceduralPrepareJob`  
- `Game.Rendering.ProceduralUploadSystem+ProceduralUploadJob`  
- `Game.Rendering.ProceduralUploadSystem+TypeHandle`  

