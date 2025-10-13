# Game.Simulation.SnowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `FormerlySerializedAs`  

## Code

```csharp
public class SnowSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private UnityEngine.RenderTexture m_snowHeightBackdropTextureFinal;
    private UnityEngine.ComputeBuffer m_snowBackdropBuffer;
    private UnityEngine.ComputeBuffer m_MinHeights;
    private System.Int32 <SnowSimSpeed>k__BackingField;
    private UnityEngine.RenderTexture[] m_SnowHeights;
    private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
    private UnityEngine.ComputeShader m_SnowUpdateShader;
    private UnityEngine.ComputeShader <m_SnowTransferShader>k__BackingField;
    private UnityEngine.ComputeShader <m_DynamicHeightShader>k__BackingField;
    private System.Int32 m_TransferKernel;
    private System.Int32 m_AddKernel;
    private System.Int32 m_ResetKernel;
    private System.Int32 m_LoadKernel;
    private System.Int32 m_LoadOldFormatKernel;
    private System.Int32 m_UpdateBackdropSnowHeightTextureKernel;
    private System.Int32 m_ClearBackdropSnowHeightTextureKernel;
    private System.Int32 m_FinalizeBackdropSnowHeightTextureKernel;
    private System.Int32 m_ID_SnowDepth;
    private System.Int32 m_ID_OldSnowDepth;
    private System.Int32 m_ID_Timestep;
    private System.Int32 m_ID_AddMultiplier;
    private System.Int32 m_ID_MeltMultiplier;
    private System.Int32 m_ID_AddWaterMultiplier;
    private System.Int32 m_ID_ElapseWaterMultiplier;
    private System.Int32 m_ID_Temperature;
    private System.Int32 m_ID_Rain;
    private System.Int32 m_ID_Wind;
    private System.Int32 m_ID_Time;
    private System.Int32 m_ID_SnowScale;
    private System.Int32 m_ID_MinHeights;
    private System.Int32 m_ID_SnowHeightBackdropBuffer;
    private System.Int32 m_ID_SnowHeightBackdropFinal;
    private System.Int32 m_ID_SnowBackdropUpdateLerpFactor;
    private System.Int32 m_ID_SnowHeightBackdropBufferSize;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private System.Int32 <Write>k__BackingField;
    private System.Boolean <IsAsync>k__BackingField;
    private static Colossal.Logging.ILog log;
    private static const System.Int32 kTexSize;
    private static const System.Int32 kGroupSizeAddSnow;
    private static const System.Int32 kNumGroupAddSnow;
    private static const System.Single kTimeStep;
    private static const System.Single kSnowHeightScale;
    private static const System.Single kSnowMeltScale;
    private static const System.Single m_SnowAddConstant;
    private static const System.Single m_WaterAddConstant;
    private static const System.Int32 kSnowHeightBackdropTextureSize;
    private static const System.Single kSnowBackdropUpdateLerpFactor;

    public UnityEngine.RenderTexture SnowHeightBackdropTexture { get; }
    public System.Int32 SnowSimSpeed { get; set; }
    public Unity.Mathematics.int2 TextureSize { get; }
    public System.Boolean Loaded { get; }
    private UnityEngine.ComputeShader m_SnowTransferShader { private get; set; }
    private UnityEngine.ComputeShader m_DynamicHeightShader { private get; set; }
    private Unity.Mathematics.float4 SnowScaleVector { private get; }
    private System.Int32 Write { private get; private set; }
    private System.Int32 Read { private get; }
    public UnityEngine.RenderTexture SnowDepth { get; }
    public System.Boolean IsAsync { get; set; }

    public SnowSystem();

    private System.Void AddSnow(UnityEngine.Rendering.CommandBuffer cmd);
    private UnityEngine.RenderTexture CreateTexture(System.String name);
    public System.Void DebugReset();
    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void FlipSnow();
    private System.Single GetSnowiness();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    private System.Void InitShader();
    private System.Void InitTextures();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void SnowTransfer(UnityEngine.Rendering.CommandBuffer cmd);
    public System.Void UpdateDynamicHeights();
    private System.Void UpdateSnowBackdropTexture(UnityEngine.Rendering.CommandBuffer cmd, System.Single lerpFactor);
}
```


## Fields

- `private UnityEngine.RenderTexture m_snowHeightBackdropTextureFinal`  

```csharp
private UnityEngine.RenderTexture m_snowHeightBackdropTextureFinal;
```

- `private UnityEngine.ComputeBuffer m_snowBackdropBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_snowBackdropBuffer;
```

- `private UnityEngine.ComputeBuffer m_MinHeights`  

```csharp
private UnityEngine.ComputeBuffer m_MinHeights;
```

- `private System.Int32 <SnowSimSpeed>k__BackingField`  

```csharp
private System.Int32 <SnowSimSpeed>k__BackingField;
```

- `private UnityEngine.RenderTexture[] m_SnowHeights`  

```csharp
private UnityEngine.RenderTexture[] m_SnowHeights;
```

- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  

```csharp
private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
```

- `private UnityEngine.ComputeShader m_SnowUpdateShader`  

```csharp
private UnityEngine.ComputeShader m_SnowUpdateShader;
```

- `private UnityEngine.ComputeShader <m_SnowTransferShader>k__BackingField`  

```csharp
private UnityEngine.ComputeShader <m_SnowTransferShader>k__BackingField;
```

- `private UnityEngine.ComputeShader <m_DynamicHeightShader>k__BackingField`  

```csharp
private UnityEngine.ComputeShader <m_DynamicHeightShader>k__BackingField;
```

- `private System.Int32 m_TransferKernel`  

```csharp
private System.Int32 m_TransferKernel;
```

- `private System.Int32 m_AddKernel`  

```csharp
private System.Int32 m_AddKernel;
```

- `private System.Int32 m_ResetKernel`  

```csharp
private System.Int32 m_ResetKernel;
```

- `private System.Int32 m_LoadKernel`  

```csharp
private System.Int32 m_LoadKernel;
```

- `private System.Int32 m_LoadOldFormatKernel`  

```csharp
private System.Int32 m_LoadOldFormatKernel;
```

- `private System.Int32 m_UpdateBackdropSnowHeightTextureKernel`  

```csharp
private System.Int32 m_UpdateBackdropSnowHeightTextureKernel;
```

- `private System.Int32 m_ClearBackdropSnowHeightTextureKernel`  

```csharp
private System.Int32 m_ClearBackdropSnowHeightTextureKernel;
```

- `private System.Int32 m_FinalizeBackdropSnowHeightTextureKernel`  

```csharp
private System.Int32 m_FinalizeBackdropSnowHeightTextureKernel;
```

- `private System.Int32 m_ID_SnowDepth`  

```csharp
private System.Int32 m_ID_SnowDepth;
```

- `private System.Int32 m_ID_OldSnowDepth`  

```csharp
private System.Int32 m_ID_OldSnowDepth;
```

- `private System.Int32 m_ID_Timestep`  

```csharp
private System.Int32 m_ID_Timestep;
```

- `private System.Int32 m_ID_AddMultiplier`  

```csharp
private System.Int32 m_ID_AddMultiplier;
```

- `private System.Int32 m_ID_MeltMultiplier`  

```csharp
private System.Int32 m_ID_MeltMultiplier;
```

- `private System.Int32 m_ID_AddWaterMultiplier`  

```csharp
private System.Int32 m_ID_AddWaterMultiplier;
```

- `private System.Int32 m_ID_ElapseWaterMultiplier`  

```csharp
private System.Int32 m_ID_ElapseWaterMultiplier;
```

- `private System.Int32 m_ID_Temperature`  

```csharp
private System.Int32 m_ID_Temperature;
```

- `private System.Int32 m_ID_Rain`  

```csharp
private System.Int32 m_ID_Rain;
```

- `private System.Int32 m_ID_Wind`  

```csharp
private System.Int32 m_ID_Wind;
```

- `private System.Int32 m_ID_Time`  

```csharp
private System.Int32 m_ID_Time;
```

- `private System.Int32 m_ID_SnowScale`  

```csharp
private System.Int32 m_ID_SnowScale;
```

- `private System.Int32 m_ID_MinHeights`  

```csharp
private System.Int32 m_ID_MinHeights;
```

- `private System.Int32 m_ID_SnowHeightBackdropBuffer`  

```csharp
private System.Int32 m_ID_SnowHeightBackdropBuffer;
```

- `private System.Int32 m_ID_SnowHeightBackdropFinal`  

```csharp
private System.Int32 m_ID_SnowHeightBackdropFinal;
```

- `private System.Int32 m_ID_SnowBackdropUpdateLerpFactor`  

```csharp
private System.Int32 m_ID_SnowBackdropUpdateLerpFactor;
```

- `private System.Int32 m_ID_SnowHeightBackdropBufferSize`  

```csharp
private System.Int32 m_ID_SnowHeightBackdropBufferSize;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  

```csharp
private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private System.Int32 <Write>k__BackingField`  

```csharp
private System.Int32 <Write>k__BackingField;
```

- `private System.Boolean <IsAsync>k__BackingField`  

```csharp
private System.Boolean <IsAsync>k__BackingField;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static const System.Int32 kTexSize`  

```csharp
private static const System.Int32 kTexSize;
```

- `private static const System.Int32 kGroupSizeAddSnow`  

```csharp
private static const System.Int32 kGroupSizeAddSnow;
```

- `private static const System.Int32 kNumGroupAddSnow`  

```csharp
private static const System.Int32 kNumGroupAddSnow;
```

- `private static const System.Single kTimeStep`  

```csharp
private static const System.Single kTimeStep;
```

- `private static const System.Single kSnowHeightScale`  

```csharp
private static const System.Single kSnowHeightScale;
```

- `private static const System.Single kSnowMeltScale`  

```csharp
private static const System.Single kSnowMeltScale;
```

- `private static const System.Single m_SnowAddConstant`  

```csharp
private static const System.Single m_SnowAddConstant;
```

- `private static const System.Single m_WaterAddConstant`  

```csharp
private static const System.Single m_WaterAddConstant;
```

- `private static const System.Int32 kSnowHeightBackdropTextureSize`  

```csharp
private static const System.Int32 kSnowHeightBackdropTextureSize;
```

- `private static const System.Single kSnowBackdropUpdateLerpFactor`  

```csharp
private static const System.Single kSnowBackdropUpdateLerpFactor;
```


## Properties

- `public UnityEngine.RenderTexture SnowHeightBackdropTexture { get }`  

```csharp
public UnityEngine.RenderTexture SnowHeightBackdropTexture { get; }
```

- `public System.Int32 SnowSimSpeed { get; set }`  

```csharp
public System.Int32 SnowSimSpeed { get; set; }
```

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```

- `public System.Boolean Loaded { get }`  

```csharp
public System.Boolean Loaded { get; }
```

- `private UnityEngine.ComputeShader m_SnowTransferShader { private get; set }`  

```csharp
private UnityEngine.ComputeShader m_SnowTransferShader { private get; set; }
```

- `private UnityEngine.ComputeShader m_DynamicHeightShader { private get; set }`  

```csharp
private UnityEngine.ComputeShader m_DynamicHeightShader { private get; set; }
```

- `private Unity.Mathematics.float4 SnowScaleVector { private get }`  

```csharp
private Unity.Mathematics.float4 SnowScaleVector { private get; }
```

- `private System.Int32 Write { private get; private set }`  

```csharp
private System.Int32 Write { private get; private set; }
```

- `private System.Int32 Read { private get }`  

```csharp
private System.Int32 Read { private get; }
```

- `public UnityEngine.RenderTexture SnowDepth { get }`  

```csharp
public UnityEngine.RenderTexture SnowDepth { get; }
```

- `public System.Boolean IsAsync { get; set }`  

```csharp
public System.Boolean IsAsync { get; set; }
```


## Constructors

- `public SnowSystem()`  

```csharp
[Preserve]
	public SnowSystem()
	{
	}
```


## Methods

- `private AddSnow(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void AddSnow(CommandBuffer cmd)
	{
		using (new ProfilingScope(cmd, ProfilingSampler.Get(ProfileId.AddSnow)))
		{
			cmd.SetComputeFloatParam(m_SnowUpdateShader, m_ID_Timestep, 0.2f);
			cmd.SetComputeFloatParam(m_SnowUpdateShader, m_ID_AddMultiplier, 1E-05f);
			cmd.SetComputeFloatParam(m_SnowUpdateShader, m_ID_MeltMultiplier, 0.00012f);
			cmd.SetComputeFloatParam(m_SnowUpdateShader, m_ID_AddWaterMultiplier, 0.1f);
			cmd.SetComputeFloatParam(m_SnowUpdateShader, m_ID_ElapseWaterMultiplier, 0.05f);
			cmd.SetComputeFloatParam(m_SnowUpdateShader, m_ID_Temperature, m_ClimateSystem.temperature);
			cmd.SetComputeFloatParam(m_SnowUpdateShader, m_ID_Rain, m_ClimateSystem.precipitation);
			cmd.SetComputeVectorParam(m_SnowUpdateShader, m_ID_Wind, new float4(m_WindSimulationSystem.constantWind, 0f, 0f));
			cmd.SetComputeVectorParam(m_SnowUpdateShader, m_ID_SnowScale, SnowScaleVector);
			cmd.SetComputeFloatParam(m_SnowUpdateShader, m_ID_Time, m_TimeSystem.normalizedTime);
			cmd.SetComputeTextureParam(m_SnowUpdateShader, m_AddKernel, "_Terrain", m_TerrainSystem.heightmap);
			cmd.SetComputeVectorParam(m_SnowUpdateShader, "_HeightScale", new float4(m_TerrainSystem.heightScaleOffset, m_ClimateSystem.temperatureBaseHeight, m_ClimateSystem.snowTemperatureHeightScale));
			cmd.SetComputeTextureParam(m_SnowUpdateShader, m_AddKernel, m_ID_OldSnowDepth, m_SnowHeights[Read]);
			cmd.SetComputeTextureParam(m_SnowUpdateShader, m_AddKernel, m_ID_SnowDepth, m_SnowHeights[Write]);
			cmd.SetComputeTextureParam(m_SnowUpdateShader, m_AddKernel, "_Water", m_WaterSystem.WaterTexture);
			cmd.SetComputeBufferParam(m_SnowUpdateShader, m_AddKernel, m_ID_MinHeights, m_MinHeights);
			cmd.DispatchCompute(m_SnowUpdateShader, m_AddKernel, 64, 64, 1);
		}
		FlipSnow();
	}
```

- `private CreateTexture(System.String name) : UnityEngine.RenderTexture`  

```csharp
private RenderTexture CreateTexture(string name)
	{
		RenderTexture renderTexture = new RenderTexture(1024, 1024, 0, GraphicsFormat.R16G16_UNorm);
		renderTexture.name = name;
		renderTexture.hideFlags = HideFlags.DontSave;
		renderTexture.enableRandomWrite = true;
		renderTexture.wrapMode = TextureWrapMode.Clamp;
		renderTexture.filterMode = FilterMode.Bilinear;
		renderTexture.Create();
		return renderTexture;
	}
```

- `public DebugReset() : System.Void`  

```csharp
public void DebugReset()
	{
		m_SnowUpdateShader.SetTexture(m_ResetKernel, "_Result", m_SnowHeights[Write]);
		m_SnowUpdateShader.Dispatch(m_ResetKernel, 64, 64, 1);
		m_SnowUpdateShader.SetTexture(m_ResetKernel, "_Result", m_SnowHeights[Read]);
		m_SnowUpdateShader.Dispatch(m_ResetKernel, 64, 64, 1);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private FlipSnow() : System.Void`  

```csharp
private void FlipSnow()
	{
		Write = 1 - Write;
	}
```

- `private GetSnowiness() : System.Single`  

```csharp
private float GetSnowiness()
	{
		return Mathf.Sin(MathF.PI * 40f * m_TimeSystem.normalizedDate);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 4;
	}
```

- `private InitShader() : System.Void`  

```csharp
private void InitShader()
	{
		m_SnowUpdateShader = AssetDatabase.global.resources.shaders.snowUpdate;
		m_ResetKernel = m_SnowUpdateShader.FindKernel("Reset");
		m_LoadKernel = m_SnowUpdateShader.FindKernel("Load");
		m_LoadOldFormatKernel = m_SnowUpdateShader.FindKernel("LoadOldFormat");
		m_AddKernel = m_SnowUpdateShader.FindKernel("Add");
		m_TransferKernel = m_SnowUpdateShader.FindKernel("Transfer");
		m_UpdateBackdropSnowHeightTextureKernel = m_SnowUpdateShader.FindKernel("UpdateBackdropSnowHeightTexture");
		m_ClearBackdropSnowHeightTextureKernel = m_SnowUpdateShader.FindKernel("ClearBackdropSnowHeightTexture");
		m_FinalizeBackdropSnowHeightTextureKernel = m_SnowUpdateShader.FindKernel("FinalizeBackdropSnowHeightTexture");
	}
```

- `private InitTextures() : System.Void`  

```csharp
private void InitTextures()
	{
		m_SnowHeights = new RenderTexture[2];
		m_SnowHeights[0] = CreateTexture("SnowRT0");
		m_SnowHeights[1] = CreateTexture("SnowRT1");
		m_MinHeights = new ComputeBuffer(4096, UnsafeUtility.SizeOf<float2>(), ComputeBufferType.Default);
		m_snowBackdropBuffer = new ComputeBuffer(1024, UnsafeUtility.SizeOf<uint2>(), ComputeBufferType.Default);
		m_snowHeightBackdropTextureFinal = new RenderTexture(1024, 1, 0, GraphicsFormat.R32_SFloat)
		{
			name = "SnowBackdropHeightTextureFinal",
			hideFlags = HideFlags.DontSave,
			enableRandomWrite = true,
			wrapMode = TextureWrapMode.Clamp,
			filterMode = FilterMode.Bilinear
		};
		m_snowHeightBackdropTextureFinal.Create();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		InitShader();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_WindSimulationSystem = base.World.GetOrCreateSystemManaged<WindSimulationSystem>();
		InitTextures();
		m_ID_SnowDepth = Shader.PropertyToID("_Result");
		m_ID_OldSnowDepth = Shader.PropertyToID("_Previous");
		m_ID_Timestep = Shader.PropertyToID("_Timestep");
		m_ID_AddMultiplier = Shader.PropertyToID("_AddMultiplier");
		m_ID_MeltMultiplier = Shader.PropertyToID("_MeltMultiplier");
		m_ID_AddWaterMultiplier = Shader.PropertyToID("_AddWaterMultiplier");
		m_ID_ElapseWaterMultiplier = Shader.PropertyToID("_ElapseWaterMultiplier");
		m_ID_Temperature = Shader.PropertyToID("_Temperature");
		m_ID_Rain = Shader.PropertyToID("_Rain");
		m_ID_Time = Shader.PropertyToID("_SimTime");
		m_ID_Wind = Shader.PropertyToID("_Wind");
		m_ID_SnowScale = Shader.PropertyToID("_SnowScale");
		m_ID_MinHeights = Shader.PropertyToID("_MinHeights");
		m_ID_SnowHeightBackdropBuffer = Shader.PropertyToID("_SnowHeightBackdropBuffer");
		m_ID_SnowHeightBackdropFinal = Shader.PropertyToID("_SnowHeightBackdropTextureFinal");
		m_ID_SnowBackdropUpdateLerpFactor = Shader.PropertyToID("_SnowBackdropUpdateLerpFactor");
		m_ID_SnowHeightBackdropBufferSize = Shader.PropertyToID("_SnowHeightBackdropBufferSize");
		RequireForUpdate<TerrainPropertiesData>();
		m_CommandBuffer = new CommandBuffer();
		m_CommandBuffer.name = "Snowsystem";
		SnowSimSpeed = 1;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_CommandBuffer.Dispose();
		CoreUtils.Destroy(m_SnowHeights[0]);
		CoreUtils.Destroy(m_SnowHeights[1]);
		m_MinHeights.Release();
		m_snowBackdropBuffer.Release();
		CoreUtils.Destroy(m_snowHeightBackdropTextureFinal);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_WaterSystem.Loaded)
		{
			m_CommandBuffer.Clear();
			for (int i = 0; i < SnowSimSpeed; i++)
			{
				AddSnow(m_CommandBuffer);
				SnowTransfer(m_CommandBuffer);
			}
			UpdateSnowBackdropTexture(m_CommandBuffer, 0.1f);
			Shader.SetGlobalTexture("_SnowMap", SnowDepth);
			Graphics.ExecuteCommandBuffer(m_CommandBuffer);
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (context.version < Version.snow)
		{
			m_SnowUpdateShader.SetTexture(m_ResetKernel, "_Result", m_SnowHeights[Write]);
			m_SnowUpdateShader.Dispatch(m_ResetKernel, 64, 64, 1);
			m_SnowUpdateShader.SetTexture(m_ResetKernel, "_Result", m_SnowHeights[Read]);
			m_SnowUpdateShader.Dispatch(m_ResetKernel, 64, 64, 1);
		}
		Shader.SetGlobalTexture("_SnowMap", SnowDepth);
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
		m_SnowUpdateShader.SetTexture(m_ResetKernel, "_Result", m_SnowHeights[Write]);
		m_SnowUpdateShader.Dispatch(m_ResetKernel, 64, 64, 1);
		m_SnowUpdateShader.SetTexture(m_ResetKernel, "_Result", m_SnowHeights[Read]);
		m_SnowUpdateShader.Dispatch(m_ResetKernel, 64, 64, 1);
		Shader.SetGlobalTexture("_SnowMap", SnowDepth);
	}
```

- `private SnowTransfer(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void SnowTransfer(CommandBuffer cmd)
	{
		using (new ProfilingScope(cmd, ProfilingSampler.Get(ProfileId.TransferSnow)))
		{
			if ((float)m_ClimateSystem.precipitation < 0.1f || (float)m_ClimateSystem.temperature - 0.01f * (m_TerrainSystem.heightScaleOffset.x - m_ClimateSystem.temperatureBaseHeight) > 0f)
			{
				return;
			}
			cmd.SetComputeVectorParam(m_SnowUpdateShader, m_ID_SnowScale, SnowScaleVector);
			cmd.SetComputeVectorParam(m_SnowUpdateShader, "_HeightScale", new float4(m_TerrainSystem.heightScaleOffset, m_ClimateSystem.temperatureBaseHeight, 0f));
			cmd.SetComputeTextureParam(m_SnowUpdateShader, m_TransferKernel, m_ID_OldSnowDepth, m_SnowHeights[Read]);
			cmd.SetComputeTextureParam(m_SnowUpdateShader, m_TransferKernel, m_ID_SnowDepth, m_SnowHeights[Write]);
			cmd.SetComputeTextureParam(m_SnowUpdateShader, m_TransferKernel, "_Terrain", m_TerrainSystem.heightmap);
			cmd.SetComputeVectorParam(m_SnowUpdateShader, m_ID_Wind, new float4(m_WindSimulationSystem.constantWind, 0f, 0f));
			cmd.DispatchCompute(m_SnowUpdateShader, m_TransferKernel, 64, 64, 1);
		}
		FlipSnow();
	}
```

- `public UpdateDynamicHeights() : System.Void`  

```csharp
public void UpdateDynamicHeights()
	{
	}
```

- `private UpdateSnowBackdropTexture(UnityEngine.Rendering.CommandBuffer cmd, System.Single lerpFactor) : System.Void`  

```csharp
private void UpdateSnowBackdropTexture(CommandBuffer cmd, float lerpFactor)
	{
		using (new ProfilingScope(m_CommandBuffer, ProfilingSampler.Get(ProfileId.UpdateSnowHeightBackdrop)))
		{
			cmd.SetComputeBufferParam(m_SnowUpdateShader, m_ClearBackdropSnowHeightTextureKernel, m_ID_SnowHeightBackdropBuffer, m_snowBackdropBuffer);
			cmd.DispatchCompute(m_SnowUpdateShader, m_ClearBackdropSnowHeightTextureKernel, 64, 1, 1);
			cmd.SetComputeBufferParam(m_SnowUpdateShader, m_UpdateBackdropSnowHeightTextureKernel, m_ID_SnowHeightBackdropBuffer, m_snowBackdropBuffer);
			cmd.SetComputeBufferParam(m_SnowUpdateShader, m_UpdateBackdropSnowHeightTextureKernel, m_ID_MinHeights, m_MinHeights);
			cmd.SetComputeIntParam(m_SnowUpdateShader, m_ID_SnowHeightBackdropBufferSize, 1024);
			cmd.DispatchCompute(m_SnowUpdateShader, m_UpdateBackdropSnowHeightTextureKernel, 256, 1, 1);
			cmd.SetComputeBufferParam(m_SnowUpdateShader, m_FinalizeBackdropSnowHeightTextureKernel, m_ID_SnowHeightBackdropBuffer, m_snowBackdropBuffer);
			cmd.SetComputeTextureParam(m_SnowUpdateShader, m_FinalizeBackdropSnowHeightTextureKernel, m_ID_SnowHeightBackdropFinal, m_snowHeightBackdropTextureFinal);
			cmd.SetComputeFloatParam(m_SnowUpdateShader, m_ID_SnowBackdropUpdateLerpFactor, lerpFactor);
			cmd.DispatchCompute(m_SnowUpdateShader, m_FinalizeBackdropSnowHeightTextureKernel, 1, 1, 1);
		}
	}
```


## Nested types

- `Game.Simulation.SnowSystem+ushort2`  

