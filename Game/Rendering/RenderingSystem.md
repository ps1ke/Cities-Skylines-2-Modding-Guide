# Game.Rendering.RenderingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RenderingSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private System.UInt32 <frameIndex>k__BackingField;
    private System.Single <frameTime>k__BackingField;
    private System.Single <frameDelta>k__BackingField;
    private System.Single <frameLod>k__BackingField;
    private System.Single <timeOfDay>k__BackingField;
    private System.Int32 <lodTimerDelta>k__BackingField;
    private System.Single <frameOffset>k__BackingField;
    private System.Boolean <hideOverlay>k__BackingField;
    private System.Boolean <unspawnedVisible>k__BackingField;
    private System.Boolean <markersVisible>k__BackingField;
    private System.Single <levelOfDetail>k__BackingField;
    private System.Boolean <lodCrossFade>k__BackingField;
    private System.Int32 <maxLightCount>k__BackingField;
    private System.Boolean <debugCrossFade>k__BackingField;
    private System.Boolean <disableLodModels>k__BackingField;
    private Unity.Mathematics.float4 <editorBuildingStateOverride>k__BackingField;
    private System.Boolean <motionVectors>k__BackingField;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private System.Collections.Generic.Dictionary<UnityEngine.Shader, System.Boolean> m_EnabledShaders;
    private Unity.Entities.EntityQuery m_TimeSettingGroup;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private System.Int32 m_TotalLoadingCount;
    private System.Int32 m_EnabledShaderCount;
    private System.Single m_LastFrameOffset;
    private System.Single m_LodTimer;
    private System.Boolean m_IsLoading;
    private System.Boolean m_EnabledShadersUpdated;
    public static const System.String kLoadingTask;

    public System.UInt32 frameIndex { get; private set; }
    public System.Single frameTime { get; private set; }
    public System.Single frameDelta { get; private set; }
    public System.Single frameLod { get; private set; }
    public System.Single timeOfDay { get; private set; }
    public System.Int32 lodTimerDelta { get; private set; }
    public System.Single frameOffset { get; set; }
    public System.Boolean hideOverlay { get; set; }
    public System.Boolean unspawnedVisible { get; set; }
    public System.Boolean markersVisible { get; set; }
    public System.Single levelOfDetail { get; set; }
    public System.Boolean lodCrossFade { get; set; }
    public System.Int32 maxLightCount { get; set; }
    public System.Boolean debugCrossFade { get; set; }
    public System.Boolean disableLodModels { get; set; }
    public Unity.Mathematics.float4 editorBuildingStateOverride { get; set; }
    public System.Single loadingProgress { get; private set; }
    public System.Boolean motionVectors { get; private set; }
    public System.Collections.Generic.IReadOnlyDictionary<UnityEngine.Shader, System.Boolean> enabledShaders { get; }

    public RenderingSystem();

    private System.Boolean GetMotionVectorsEnabled();
    public Unity.Mathematics.float3 GetShadowCullingData();
    public System.Boolean IsShaderEnabled(UnityEngine.Shader shader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void PrepareRendering();
    public System.Void SetShaderEnabled(UnityEngine.Shader shader, System.Boolean isEnabled);
    private System.Void UpdateLoadingProgress();
}
```


## Fields

- `private System.UInt32 <frameIndex>k__BackingField`  

```csharp
private System.UInt32 <frameIndex>k__BackingField;
```

- `private System.Single <frameTime>k__BackingField`  

```csharp
private System.Single <frameTime>k__BackingField;
```

- `private System.Single <frameDelta>k__BackingField`  

```csharp
private System.Single <frameDelta>k__BackingField;
```

- `private System.Single <frameLod>k__BackingField`  

```csharp
private System.Single <frameLod>k__BackingField;
```

- `private System.Single <timeOfDay>k__BackingField`  

```csharp
private System.Single <timeOfDay>k__BackingField;
```

- `private System.Int32 <lodTimerDelta>k__BackingField`  

```csharp
private System.Int32 <lodTimerDelta>k__BackingField;
```

- `private System.Single <frameOffset>k__BackingField`  

```csharp
private System.Single <frameOffset>k__BackingField;
```

- `private System.Boolean <hideOverlay>k__BackingField`  

```csharp
private System.Boolean <hideOverlay>k__BackingField;
```

- `private System.Boolean <unspawnedVisible>k__BackingField`  

```csharp
private System.Boolean <unspawnedVisible>k__BackingField;
```

- `private System.Boolean <markersVisible>k__BackingField`  

```csharp
private System.Boolean <markersVisible>k__BackingField;
```

- `private System.Single <levelOfDetail>k__BackingField`  

```csharp
private System.Single <levelOfDetail>k__BackingField;
```

- `private System.Boolean <lodCrossFade>k__BackingField`  

```csharp
private System.Boolean <lodCrossFade>k__BackingField;
```

- `private System.Int32 <maxLightCount>k__BackingField`  

```csharp
private System.Int32 <maxLightCount>k__BackingField;
```

- `private System.Boolean <debugCrossFade>k__BackingField`  

```csharp
private System.Boolean <debugCrossFade>k__BackingField;
```

- `private System.Boolean <disableLodModels>k__BackingField`  

```csharp
private System.Boolean <disableLodModels>k__BackingField;
```

- `private Unity.Mathematics.float4 <editorBuildingStateOverride>k__BackingField`  

```csharp
private Unity.Mathematics.float4 <editorBuildingStateOverride>k__BackingField;
```

- `private System.Boolean <motionVectors>k__BackingField`  

```csharp
private System.Boolean <motionVectors>k__BackingField;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.Rendering.AreaBatchSystem m_AreaBatchSystem`  

```csharp
private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private System.Collections.Generic.Dictionary<UnityEngine.Shader, System.Boolean> m_EnabledShaders`  

```csharp
private System.Collections.Generic.Dictionary<UnityEngine.Shader, System.Boolean> m_EnabledShaders;
```

- `private Unity.Entities.EntityQuery m_TimeSettingGroup`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingGroup;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private System.Int32 m_TotalLoadingCount`  

```csharp
private System.Int32 m_TotalLoadingCount;
```

- `private System.Int32 m_EnabledShaderCount`  

```csharp
private System.Int32 m_EnabledShaderCount;
```

- `private System.Single m_LastFrameOffset`  

```csharp
private System.Single m_LastFrameOffset;
```

- `private System.Single m_LodTimer`  

```csharp
private System.Single m_LodTimer;
```

- `private System.Boolean m_IsLoading`  

```csharp
private System.Boolean m_IsLoading;
```

- `private System.Boolean m_EnabledShadersUpdated`  

```csharp
private System.Boolean m_EnabledShadersUpdated;
```

- `public static const System.String kLoadingTask`  

```csharp
public static const System.String kLoadingTask;
```


## Properties

- `public System.UInt32 frameIndex { get; private set }`  

```csharp
public System.UInt32 frameIndex { get; private set; }
```

- `public System.Single frameTime { get; private set }`  

```csharp
public System.Single frameTime { get; private set; }
```

- `public System.Single frameDelta { get; private set }`  

```csharp
public System.Single frameDelta { get; private set; }
```

- `public System.Single frameLod { get; private set }`  

```csharp
public System.Single frameLod { get; private set; }
```

- `public System.Single timeOfDay { get; private set }`  

```csharp
public System.Single timeOfDay { get; private set; }
```

- `public System.Int32 lodTimerDelta { get; private set }`  

```csharp
public System.Int32 lodTimerDelta { get; private set; }
```

- `public System.Single frameOffset { get; set }`  

```csharp
public System.Single frameOffset { get; set; }
```

- `public System.Boolean hideOverlay { get; set }`  

```csharp
public System.Boolean hideOverlay { get; set; }
```

- `public System.Boolean unspawnedVisible { get; set }`  

```csharp
public System.Boolean unspawnedVisible { get; set; }
```

- `public System.Boolean markersVisible { get; set }`  

```csharp
public System.Boolean markersVisible { get; set; }
```

- `public System.Single levelOfDetail { get; set }`  

```csharp
public System.Single levelOfDetail { get; set; }
```

- `public System.Boolean lodCrossFade { get; set }`  

```csharp
public System.Boolean lodCrossFade { get; set; }
```

- `public System.Int32 maxLightCount { get; set }`  

```csharp
public System.Int32 maxLightCount { get; set; }
```

- `public System.Boolean debugCrossFade { get; set }`  

```csharp
public System.Boolean debugCrossFade { get; set; }
```

- `public System.Boolean disableLodModels { get; set }`  

```csharp
public System.Boolean disableLodModels { get; set; }
```

- `public Unity.Mathematics.float4 editorBuildingStateOverride { get; set }`  

```csharp
public Unity.Mathematics.float4 editorBuildingStateOverride { get; set; }
```

- `public System.Single loadingProgress { get; private set }`  

```csharp
public System.Single loadingProgress { get; private set; }
```

- `public System.Boolean motionVectors { get; private set }`  

```csharp
public System.Boolean motionVectors { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<UnityEngine.Shader, System.Boolean> enabledShaders { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<UnityEngine.Shader, System.Boolean> enabledShaders { get; }
```


## Constructors

- `public RenderingSystem()`  

```csharp
[Preserve]
	public RenderingSystem()
	{
	}
```


## Methods

- `private GetMotionVectorsEnabled() : System.Boolean`  

```csharp
private bool GetMotionVectorsEnabled()
	{
		return true;
	}
```

- `public GetShadowCullingData() : Unity.Mathematics.float3`  

```csharp
public float3 GetShadowCullingData()
	{
		float3 result = new float3(2048f, 1f, 1f);
		SharedSettings instance = SharedSettings.instance;
		if (instance != null && instance.graphics != null)
		{
			ShadowsQualitySettings qualitySetting = instance.graphics.GetQualitySetting<ShadowsQualitySettings>();
			if (qualitySetting != null)
			{
				result.y = qualitySetting.shadowCullingThresholdHeight;
				result.z = qualitySetting.shadowCullingThresholdVolume;
			}
		}
		return result;
	}
```

- `public IsShaderEnabled(UnityEngine.Shader shader) : System.Boolean`  

```csharp
public bool IsShaderEnabled(Shader shader)
	{
		if (m_EnabledShaders.TryGetValue(shader, out var value))
		{
			return value;
		}
		value = m_EnabledShaderCount != 0 || m_EnabledShaders.Count == 0;
		m_EnabledShaderCount += (value ? 1 : 0);
		m_EnabledShaders.Add(shader, value);
		return value;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
		m_BatchManagerSystem = base.World.GetOrCreateSystemManaged<BatchManagerSystem>();
		m_ManagedBatchSystem = base.World.GetOrCreateSystemManaged<ManagedBatchSystem>();
		m_BatchMeshSystem = base.World.GetOrCreateSystemManaged<BatchMeshSystem>();
		m_AreaBatchSystem = base.World.GetOrCreateSystemManaged<AreaBatchSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_EnabledShaders = new Dictionary<Shader, bool>();
		levelOfDetail = 0.5f;
		maxLightCount = 2048;
		m_TimeSettingGroup = GetEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		motionVectors = GetMotionVectorsEnabled();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		m_TotalLoadingCount = 0;
		m_IsLoading = true;
		frameLod = 0f;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_UpdateSystem.Update(SystemUpdatePhase.Rendering);
		if (m_IsLoading)
		{
			if (loadingProgress != 1f)
			{
				UpdateLoadingProgress();
			}
			else
			{
				m_IsLoading = false;
			}
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		frameIndex = m_SimulationSystem.frameIndex;
		frameTime = m_SimulationSystem.frameTime;
		frameDelta = 0f;
		frameOffset = 1f;
		m_LastFrameOffset = 1f;
	}
```

- `public PrepareRendering() : System.Void`  

```csharp
public void PrepareRendering()
	{
		int num = 15;
		if (m_LastFrameOffset != frameOffset)
		{
			float num2 = frameOffset * (float)num;
			int num3 = (int)math.floor(num2);
			uint num4 = frameIndex;
			float num5 = frameTime;
			frameIndex = m_SimulationSystem.frameIndex + (uint)num3;
			frameTime = num2 - (float)num3;
			frameDelta = (float)(int)(frameIndex - num4) + (frameTime - num5);
			m_LastFrameOffset = frameOffset;
		}
		else if (m_SimulationSystem.selectedSpeed < 1E-05f)
		{
			frameDelta = 0f;
		}
		else
		{
			int num6 = (int)(frameIndex - m_SimulationSystem.frameIndex);
			float num7 = m_SimulationSystem.frameTime;
			float num8 = (float)num6 + frameTime + UnityEngine.Time.deltaTime * m_SimulationSystem.smoothSpeed * 60f;
			float num9 = num8 - num7;
			float num10 = (float)num * (4f / MathF.PI);
			num9 = math.atan(num9 / num10) * num10;
			num9 = math.clamp(num9, -num, num);
			num8 = num7 + num9;
			num6 = (int)math.floor(num8);
			uint num11 = frameIndex;
			float num12 = frameTime;
			if (num6 < 0 && m_SimulationSystem.frameIndex < (uint)(-num6))
			{
				frameIndex = 0u;
				frameTime = 0f;
			}
			else
			{
				frameIndex = m_SimulationSystem.frameIndex + (uint)num6;
				frameTime = math.saturate(num8 - (float)num6);
			}
			frameDelta = (float)(int)(frameIndex - num11) + (frameTime - num12);
			if (frameDelta < 0f)
			{
				frameIndex = num11;
				frameTime = num12;
				frameDelta = 0f;
			}
			frameOffset = math.clamp((num8 - num7) / (float)num, -1f, 1f);
			m_LastFrameOffset = frameOffset;
		}
		float4 xyxy = (frameIndex % new uint2(60u, 3600u) + new float2(frameTime)).xyxy;
		xyxy *= new float4(1f / 60f, 0.00027777778f, MathF.PI / 30f, 0.0017453294f);
		Shader.SetGlobalVector("colossal_SimulationTime", xyxy);
		float value = (float)(frameIndex % 216000) + frameTime;
		Shader.SetGlobalFloat("colossal_SimulationTime2", value);
		if (m_TimeSettingGroup.TryGetSingleton<TimeSettingsData>(out var value2) && m_TimeDataQuery.TryGetSingleton<TimeData>(out var value3))
		{
			timeOfDay = m_TimeSystem.GetTimeOfDay(value2, value3, (double)(frameIndex - value3.m_FirstFrame) + (double)frameTime);
		}
		else
		{
			timeOfDay = -1f;
		}
		motionVectors = GetMotionVectorsEnabled();
		if (m_BatchManagerSystem.CheckPropertyUpdates())
		{
			frameLod = 0f;
			lodTimerDelta = 255;
		}
		else if (lodCrossFade)
		{
			m_LodTimer += UnityEngine.Time.deltaTime * (debugCrossFade ? 102f : 1020f);
			lodTimerDelta = Mathf.FloorToInt(m_LodTimer);
			m_LodTimer -= lodTimerDelta;
			lodTimerDelta = math.clamp(lodTimerDelta, 0, 255);
		}
		else
		{
			lodTimerDelta = 255;
		}
		frameLod = math.min(frameLod + levelOfDetail * 0.01f, levelOfDetail);
		if (m_EnabledShadersUpdated)
		{
			m_EnabledShadersUpdated = false;
			m_ManagedBatchSystem.EnabledShadersUpdated();
			m_AreaBatchSystem.EnabledShadersUpdated();
		}
	}
```

- `public SetShaderEnabled(UnityEngine.Shader shader, System.Boolean isEnabled) : System.Void`  

```csharp
public void SetShaderEnabled(Shader shader, bool isEnabled)
	{
		if (IsShaderEnabled(shader) != isEnabled)
		{
			m_EnabledShaderCount += (isEnabled ? 1 : (-1));
			m_EnabledShaders[shader] = isEnabled;
			m_EnabledShadersUpdated = true;
		}
	}
```

- `private UpdateLoadingProgress() : System.Void`  

```csharp
private void UpdateLoadingProgress()
	{
		int num = m_BatchMeshSystem.loadingRemaining;
		if (frameLod < levelOfDetail)
		{
			num = math.max(1, (int)((float)num * levelOfDetail / math.max(frameLod, levelOfDetail * 0.01f)));
		}
		m_TotalLoadingCount = math.max(num, m_TotalLoadingCount);
		if (num > 0)
		{
			loadingProgress = math.clamp((float)(m_TotalLoadingCount - num) / (float)m_TotalLoadingCount, 0f, 0.99999f);
			return;
		}
		loadingProgress = 1f;
		m_IsLoading = false;
	}
```


