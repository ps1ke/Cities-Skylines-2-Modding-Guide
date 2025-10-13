# Game.Effects.VFXSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VFXSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private System.Collections.Generic.Queue<Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>> m_SourceUpdateQueue;
    private Unity.Jobs.JobHandle m_SourceUpdateWriter;
    private Unity.Entities.EntityQuery m_VFXPrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private System.Boolean m_Initialized;
    private Game.Effects.VFXSystem+EffectInfo[] m_Effects;
    private Unity.Jobs.JobHandle m_TextureUpdate;
    private Game.Rendering.WindTextureSystem m_WindTextureSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;

    public VFXSystem();

    public System.Void AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Void ClearQueue();
    public Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo> GetSourceUpdateData();
    private System.Boolean Initialize();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private System.Collections.Generic.Queue<Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>> m_SourceUpdateQueue`  

```csharp
private System.Collections.Generic.Queue<Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>> m_SourceUpdateQueue;
```

- `private Unity.Jobs.JobHandle m_SourceUpdateWriter`  

```csharp
private Unity.Jobs.JobHandle m_SourceUpdateWriter;
```

- `private Unity.Entities.EntityQuery m_VFXPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VFXPrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private System.Boolean m_Initialized`  

```csharp
private System.Boolean m_Initialized;
```

- `private Game.Effects.VFXSystem+EffectInfo[] m_Effects`  

```csharp
private Game.Effects.VFXSystem+EffectInfo[] m_Effects;
```

- `private Unity.Jobs.JobHandle m_TextureUpdate`  

```csharp
private Unity.Jobs.JobHandle m_TextureUpdate;
```

- `private Game.Rendering.WindTextureSystem m_WindTextureSystem`  

```csharp
private Game.Rendering.WindTextureSystem m_WindTextureSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```


## Constructors

- `public VFXSystem()`  

```csharp
[Preserve]
	public VFXSystem()
	{
	}
```


## Methods

- `public AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddSourceUpdateWriter(JobHandle jobHandle)
	{
		m_SourceUpdateWriter = JobHandle.CombineDependencies(m_SourceUpdateWriter, jobHandle);
	}
```

- `private ClearQueue() : System.Void`  

```csharp
private void ClearQueue()
	{
		m_SourceUpdateWriter.Complete();
		NativeQueue<VFXUpdateInfo> result;
		while (m_SourceUpdateQueue.TryDequeue(out result))
		{
			result.Dispose();
		}
	}
```

- `public GetSourceUpdateData() : Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>`  

```csharp
public NativeQueue<VFXUpdateInfo> GetSourceUpdateData()
	{
		NativeQueue<VFXUpdateInfo> nativeQueue = new NativeQueue<VFXUpdateInfo>(Allocator.TempJob);
		m_SourceUpdateQueue.Enqueue(nativeQueue);
		return nativeQueue;
	}
```

- `private Initialize() : System.Boolean`  

```csharp
private bool Initialize()
	{
		if (!m_Initialized && !m_VFXPrefabQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray = m_VFXPrefabQuery.ToEntityArray(Allocator.TempJob);
			NativeArray<VFXData> nativeArray2 = m_VFXPrefabQuery.ToComponentDataArray<VFXData>(Allocator.TempJob);
			m_Effects = new EffectInfo[nativeArray.Length];
			for (int i = 0; i < nativeArray.Length; i++)
			{
				base.World.EntityManager.GetComponentData<VFXData>(nativeArray[i]);
				EffectPrefab prefab = m_PrefabSystem.GetPrefab<EffectPrefab>(nativeArray[i]);
				VFX component = prefab.GetComponent<VFX>();
				VisualEffect visualEffect = new GameObject("VFX " + prefab.name).AddComponent<VisualEffect>();
				visualEffect.visualEffectAsset = component.m_Effect;
				visualEffect.SetCheckedInt(VFXIDs.Count, 0);
				m_Effects[i].m_VisualEffect = visualEffect;
				VFXData componentData = nativeArray2[i];
				componentData.m_MaxCount = component.m_MaxCount;
				componentData.m_Index = i;
				base.World.EntityManager.SetComponentData(nativeArray[i], componentData);
				Texture2D texture2D = new Texture2D(component.m_MaxCount, 3, GraphicsFormat.R32G32B32A32_SFloat, 1, TextureCreationFlags.None)
				{
					name = "VFXTexture " + prefab.name,
					hideFlags = HideFlags.HideAndDontSave
				};
				m_Effects[i].m_Texture = texture2D;
				visualEffect.SetCheckedTexture(VFXIDs.InstanceData, texture2D);
				m_Effects[i].m_Instances = new NativeArray<int>(componentData.m_MaxCount, Allocator.Persistent);
				m_Effects[i].m_Indices = new NativeParallelHashMap<int, int>(componentData.m_MaxCount, Allocator.Persistent);
			}
			nativeArray2.Dispose();
			nativeArray.Dispose();
			m_Initialized = true;
			return true;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SourceUpdateQueue = new Queue<NativeQueue<VFXUpdateInfo>>();
		m_VFXPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<VFXData>());
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_WindTextureSystem = base.World.GetOrCreateSystemManaged<WindTextureSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_EffectControlSystem = base.World.GetOrCreateSystemManaged<EffectControlSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		if (m_Initialized && m_Effects != null)
		{
			for (int i = 0; i < m_Effects.Length; i++)
			{
				UnityEngine.Object.Destroy(m_Effects[i].m_Texture);
				if (m_Effects[i].m_Instances.IsCreated)
				{
					m_Effects[i].m_Instances.Dispose();
				}
				if (m_Effects[i].m_Indices.IsCreated)
				{
					m_Effects[i].m_Indices.Dispose();
				}
			}
		}
		ClearQueue();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_Initialized && !Initialize())
		{
			ClearQueue();
			return;
		}
		m_TextureUpdate.Complete();
		m_SourceUpdateWriter.Complete();
		JobHandle dependencies;
		NativeList<EnabledEffectData> enabledData = m_EffectControlSystem.GetEnabledData(readOnly: true, out dependencies);
		NativeQueue<VFXUpdateInfo> result;
		while (m_SourceUpdateQueue.TryDequeue(out result))
		{
			if (!result.IsEmpty())
			{
				dependencies.Complete();
				VFXUpdateInfo item;
				while (result.TryDequeue(out item))
				{
					EnabledEffectData enabledEffectData = enabledData[item.m_EnabledIndex.x];
					if (!base.EntityManager.TryGetComponent<VFXData>(enabledEffectData.m_Prefab, out var component))
					{
						continue;
					}
					int index = component.m_Index;
					switch (item.m_Type)
					{
					case VFXUpdateType.Add:
						if (!m_Effects[index].m_Indices.ContainsKey(item.m_EnabledIndex.x) && index >= 0 && m_Effects[index].m_Indices.Count() < m_Effects[index].m_Instances.Length)
						{
							int num = m_Effects[index].m_Indices.Count();
							m_Effects[index].m_Instances[num] = item.m_EnabledIndex.x;
							m_Effects[index].m_Indices[item.m_EnabledIndex.x] = num;
							if (m_Effects[index].m_VisualEffect != null)
							{
								m_Effects[index].m_VisualEffect.SetCheckedInt(VFXIDs.Count, m_Effects[index].m_Indices.Count());
							}
						}
						break;
					case VFXUpdateType.Remove:
						if (m_Effects[index].m_Indices.ContainsKey(item.m_EnabledIndex.x))
						{
							int num2 = m_Effects[index].m_Instances[m_Effects[index].m_Indices.Count() - 1];
							int num3 = m_Effects[index].m_Indices[item.m_EnabledIndex.x];
							if (item.m_EnabledIndex.x != num2)
							{
								m_Effects[index].m_Instances[num3] = num2;
								m_Effects[index].m_Indices[num2] = num3;
							}
							m_Effects[index].m_Instances[m_Effects[index].m_Indices.Count() - 1] = -1;
							m_Effects[index].m_Indices.Remove(item.m_EnabledIndex.x);
							if (m_Effects[index].m_VisualEffect != null)
							{
								m_Effects[index].m_VisualEffect.SetCheckedInt(VFXIDs.Count, m_Effects[index].m_Indices.Count());
							}
						}
						break;
					case VFXUpdateType.MoveIndex:
					{
						if (m_Effects[index].m_Indices.TryGetValue(item.m_EnabledIndex.y, out var item2))
						{
							m_Effects[index].m_Indices.Remove(item.m_EnabledIndex.y);
							m_Effects[index].m_Indices[item.m_EnabledIndex.x] = item2;
							m_Effects[index].m_Instances[item2] = item.m_EnabledIndex.x;
						}
						break;
					}
					}
				}
			}
			result.Dispose();
		}
		float playRate = m_RenderingSystem.frameDelta / math.max(1E-06f, base.CheckedStateRef.WorldUnmanaged.Time.DeltaTime * 60f);
		for (int i = 0; i < m_Effects.Length; i++)
		{
			if (m_Effects[i].m_VisualEffect != null)
			{
				m_Effects[i].m_VisualEffect.playRate = playRate;
				m_Effects[i].m_VisualEffect.SetCheckedTexture(VFXIDs.WindTexture, m_WindTextureSystem.WindTexture);
				m_Effects[i].m_VisualEffect.SetCheckedVector4(VFXIDs.MapOffsetScale, m_TerrainSystem.mapOffsetScale);
			}
			int num4 = math.max(m_Effects[i].m_Indices.Count(), m_Effects[i].m_LastCount);
			if (m_Effects[i].m_NeedApply)
			{
				m_Effects[i].m_Texture.Apply();
				m_Effects[i].m_NeedApply = false;
			}
			m_Effects[i].m_VisualEffect.SetCheckedInt(VFXIDs.Count, m_Effects[i].m_LastCount);
			m_Effects[i].m_LastCount = m_Effects[i].m_Indices.Count();
			if (num4 != 0)
			{
				VFXTextureUpdateJob jobData = new VFXTextureUpdateJob
				{
					m_TextureData = m_Effects[i].m_Texture.GetRawTextureData<float4>(),
					m_Instances = m_Effects[i].m_Instances,
					m_EnabledData = enabledData,
					m_Count = num4,
					m_TextureWidth = m_Effects[i].m_Texture.width
				};
				m_Effects[i].m_NeedApply = true;
				m_TextureUpdate = JobHandle.CombineDependencies(m_TextureUpdate, IJobExtensions.Schedule(jobData, dependencies));
			}
		}
		m_EffectControlSystem.AddEnabledDataReader(m_TextureUpdate);
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		if (m_Initialized && m_Effects != null)
		{
			m_TextureUpdate.Complete();
			for (int i = 0; i < m_Effects.Length; i++)
			{
				if (m_Effects[i].m_VisualEffect != null)
				{
					m_Effects[i].m_VisualEffect.SetCheckedInt(VFXIDs.Count, 0);
					UnityEngine.Object.Destroy(m_Effects[i].m_VisualEffect.gameObject);
				}
				if (m_Effects[i].m_Instances.IsCreated)
				{
					m_Effects[i].m_Instances.Dispose();
				}
				if (m_Effects[i].m_Indices.IsCreated)
				{
					m_Effects[i].m_Indices.Dispose();
				}
			}
			m_Initialized = false;
		}
		ClearQueue();
	}
```


## Nested types

- `Game.Effects.VFXSystem+VFXIDs`  
- `Game.Effects.VFXSystem+EffectInfo`  
- `Game.Effects.VFXSystem+VFXTextureUpdateJob`  

