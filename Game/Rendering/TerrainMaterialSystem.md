# Game.Rendering.TerrainMaterialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Code

```csharp
public class TerrainMaterialSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Colossal.Logging.ILog log;
    private System.Single m_TerrainVTBorder;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.SnowSystem m_SnowSystem;
    private UnityEngine.Material m_SplatMaterial;
    private UnityEngine.MaterialPropertyBlock m_Properties;
    private UnityEngine.Mesh m_BlitMesh;
    private UnityEngine.RenderTexture m_SplatMap;
    private UnityEngine.RenderTexture m_SplatWorldMap;
    private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
    private UnityEngine.Texture2D m_Noise;
    private System.Int32 m_UpdateIndex;
    private System.Int32 m_UpdateTick;
    private System.Boolean m_ForceUpdateWholeSplatmap;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_MaterialPrefabs;
    private static readonly Unity.Mathematics.float4 kClearViewport;
    private static const System.Int32 m_SplatUpdateSize;
    private static const System.Int32 m_SplatRegularUpdateTick;

    private UnityEngine.Material splatMaterial { private get; private set; }
    public UnityEngine.Texture splatmap { get; }

    public TerrainMaterialSystem();

    private System.Void CreateNoiseTexture();
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void ForceUpdateWholeSplatmap();
    public System.Int32 GetOrAddMaterialIndex(Unity.Entities.Entity prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PatchReferences(Game.Serialization.PrefabReferences& references);
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Void UpdateMaterial(UnityEngine.Material material);
    private System.Void UpdateSplatmap(UnityEngine.Rendering.CommandBuffer cmd, Unity.Mathematics.float4 viewport, System.Boolean bWorldUpdate);
}
```


## Fields

- `private Colossal.Logging.ILog log`  

```csharp
private Colossal.Logging.ILog log;
```

- `private System.Single m_TerrainVTBorder`  

```csharp
private System.Single m_TerrainVTBorder;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Rendering.WaterRenderSystem m_WaterRenderSystem`  

```csharp
private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.SnowSystem m_SnowSystem`  

```csharp
private Game.Simulation.SnowSystem m_SnowSystem;
```

- `private UnityEngine.Material m_SplatMaterial`  

```csharp
private UnityEngine.Material m_SplatMaterial;
```

- `private UnityEngine.MaterialPropertyBlock m_Properties`  

```csharp
private UnityEngine.MaterialPropertyBlock m_Properties;
```

- `private UnityEngine.Mesh m_BlitMesh`  

```csharp
private UnityEngine.Mesh m_BlitMesh;
```

- `private UnityEngine.RenderTexture m_SplatMap`  

```csharp
private UnityEngine.RenderTexture m_SplatMap;
```

- `private UnityEngine.RenderTexture m_SplatWorldMap`  

```csharp
private UnityEngine.RenderTexture m_SplatWorldMap;
```

- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  

```csharp
private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
```

- `private UnityEngine.Texture2D m_Noise`  

```csharp
private UnityEngine.Texture2D m_Noise;
```

- `private System.Int32 m_UpdateIndex`  

```csharp
private System.Int32 m_UpdateIndex;
```

- `private System.Int32 m_UpdateTick`  

```csharp
private System.Int32 m_UpdateTick;
```

- `private System.Boolean m_ForceUpdateWholeSplatmap`  

```csharp
private System.Boolean m_ForceUpdateWholeSplatmap;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_MaterialPrefabs`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_MaterialPrefabs;
```

- `private static readonly Unity.Mathematics.float4 kClearViewport`  

```csharp
private static readonly Unity.Mathematics.float4 kClearViewport;
```

- `private static const System.Int32 m_SplatUpdateSize`  

```csharp
private static const System.Int32 m_SplatUpdateSize;
```

- `private static const System.Int32 m_SplatRegularUpdateTick`  

```csharp
private static const System.Int32 m_SplatRegularUpdateTick;
```


## Properties

- `private UnityEngine.Material splatMaterial { private get; private set }`  

```csharp
private UnityEngine.Material splatMaterial { private get; private set; }
```

- `public UnityEngine.Texture splatmap { get }`  

```csharp
public UnityEngine.Texture splatmap { get; }
```


## Constructors

- `public TerrainMaterialSystem()`  

```csharp
[Preserve]
	public TerrainMaterialSystem()
	{
	}
```


## Methods

- `private CreateNoiseTexture() : System.Void`  

```csharp
private void CreateNoiseTexture()
	{
		m_Noise = new Texture2D(256, 256, TextureFormat.R8, mipChain: false);
		byte[] array = new byte[65536];
		float num = 0f;
		for (int i = 0; i < 256; i++)
		{
			for (int j = 0; j < 256; j++)
			{
				num = Mathf.PerlinNoise((float)j * (5f / 128f), (float)i * (5f / 128f));
				array[i * 256 + j] = (byte)(255f * num);
			}
		}
		m_Noise.SetPixelData(array, 0);
		m_Noise.Apply();
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public ForceUpdateWholeSplatmap() : System.Void`  

```csharp
public void ForceUpdateWholeSplatmap()
	{
		m_ForceUpdateWholeSplatmap = true;
	}
```

- `public GetOrAddMaterialIndex(Unity.Entities.Entity prefab) : System.Int32`  

```csharp
public int GetOrAddMaterialIndex(Entity prefab)
	{
		for (int i = 0; i < m_MaterialPrefabs.Length; i++)
		{
			if (m_MaterialPrefabs[i] == prefab)
			{
				return i;
			}
		}
		TerraformingPrefab prefab2 = m_PrefabSystem.GetPrefab<TerraformingPrefab>(prefab);
		UnityEngine.Debug.Log("Adding terrain material: " + prefab2.name, prefab2);
		int length = m_MaterialPrefabs.Length;
		m_MaterialPrefabs.Add(in prefab);
		prefab2.GetComponent<TerrainMaterialProperties>();
		return length;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterRenderSystem = base.World.GetOrCreateSystemManaged<WaterRenderSystem>();
		m_SnowSystem = base.World.GetOrCreateSystemManaged<SnowSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CommandBuffer = new CommandBuffer();
		m_CommandBuffer.name = "TerrainMaterialSystem";
		AssetDatabaseResources.Terrain terrain = AssetDatabase.global.resources.terrain;
		splatMaterial = terrain.splatMaterial;
		Shader.SetGlobalTexture(ShaderID._COTerrainRockDiffuse, terrain.rockDiffuse);
		Shader.SetGlobalTexture(ShaderID._COTerrainDirtDiffuse, terrain.dirtDiffuse);
		Shader.SetGlobalTexture(ShaderID._COTerrainGrassDiffuse, terrain.grassDiffuse);
		Shader.SetGlobalTexture(ShaderID._COTerrainRockNormal, terrain.rockNormal);
		Shader.SetGlobalTexture(ShaderID._COTerrainDirtNormal, terrain.dirtNormal);
		Shader.SetGlobalTexture(ShaderID._COTerrainGrassNormal, terrain.grassNormal);
		Shader.SetGlobalVector(ShaderID._COTerrainTextureTiling, new Vector4(terrain.terrainFarTiling, terrain.terrainCloseTiling, terrain.terrainCloseDirtTiling, 1f));
		CreateNoiseTexture();
		m_SplatMap = new RenderTexture(4096, 4096, 0, GraphicsFormat.R8G8_UNorm)
		{
			name = "Splatmap",
			hideFlags = HideFlags.DontSave
		};
		m_SplatMap.Create();
		m_SplatWorldMap = new RenderTexture(1024, 1024, 0, GraphicsFormat.R8G8_UNorm)
		{
			name = "SplatmapWorld",
			hideFlags = HideFlags.DontSave
		};
		m_SplatWorldMap.Create();
		m_SplatMaterial.SetTexture(ShaderID._NoiseTex, m_Noise);
		m_BlitMesh = new Mesh();
		m_BlitMesh.vertices = new Vector3[3]
		{
			new Vector3(-1f, -1f, 0f),
			new Vector3(3f, -1f, 0f),
			new Vector3(-1f, 3f, 0f)
		};
		m_BlitMesh.uv = new Vector2[3]
		{
			new Vector2(0f, 0f),
			new Vector2(2f, 0f),
			new Vector2(0f, 2f)
		};
		m_BlitMesh.subMeshCount = 1;
		m_BlitMesh.SetTriangles(new int[3] { 0, 2, 1 }, 0);
		m_BlitMesh.UploadMeshData(markNoLongerReadable: true);
		m_MaterialPrefabs = new NativeList<Entity>(Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		CoreUtils.Destroy(m_SplatMap);
		CoreUtils.Destroy(m_SplatWorldMap);
		m_MaterialPrefabs.Dispose();
		CoreUtils.Destroy(m_Noise);
		CoreUtils.Destroy(m_BlitMesh);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_SplatMaterial == null || m_TerrainSystem.GetCascadeTexture() == null)
		{
			return;
		}
		log.Trace("Updating..");
		log.indent++;
		using (new ProfilingScope(m_CommandBuffer, ProfilingSampler.Get(ProfileId.UpdateSplatmap)))
		{
			bool flag = false;
			if (m_TerrainSystem.heightMapRenderRequired)
			{
				if (m_TerrainSystem.heightMapSliceUpdated[TerrainSystem.baseLod])
				{
					m_UpdateTick = 0;
					float4 @float = m_TerrainSystem.heightMapViewport[TerrainSystem.baseLod];
					UpdateSplatmap(m_CommandBuffer, @float, math.all(@float == kClearViewport));
					flag = true;
				}
			}
			else if (m_ForceUpdateWholeSplatmap)
			{
				UpdateSplatmap(m_CommandBuffer, kClearViewport, bWorldUpdate: true);
				m_ForceUpdateWholeSplatmap = false;
				flag = true;
				m_UpdateTick = 0;
			}
			else if (++m_UpdateTick >= 8)
			{
				m_UpdateTick = 0;
				int num = 32;
				int num2 = m_UpdateIndex % num;
				int num3 = m_UpdateIndex / num;
				if (++m_UpdateIndex >= num * num)
				{
					m_UpdateIndex = 0;
				}
				float4 viewport = new float4((float)num2 / (float)num, (float)num3 / (float)num, 1f / (float)num, 1f / (float)num);
				flag = true;
				UpdateSplatmap(m_CommandBuffer, viewport, bWorldUpdate: false);
				float2 float2 = m_TerrainSystem.playableOffset + viewport.xy * m_TerrainSystem.playableArea;
				float2 float3 = viewport.zw * m_TerrainSystem.playableArea;
				foreach (WaterSurface instance in WaterSurface.instances)
				{
					instance.UpdateMinMaxArea(float2, float3);
				}
			}
			if (m_TerrainSystem.NewMap)
			{
				m_ForceUpdateWholeSplatmap = true;
				m_TerrainSystem.HandleNewMap();
				foreach (WaterSurface instance2 in WaterSurface.instances)
				{
					instance2.UpdateMinMaxArea(m_TerrainSystem.worldOffset, m_TerrainSystem.worldSize);
				}
			}
			if (flag)
			{
				log.Trace("Executing command buffer");
				Graphics.ExecuteCommandBuffer(m_CommandBuffer);
			}
		}
		log.indent--;
	}
```

- `public PatchReferences(Game.Serialization.PrefabReferences& references) : System.Void`  

```csharp
public void PatchReferences(ref PrefabReferences references)
	{
		for (int i = 0; i < m_MaterialPrefabs.Length; i++)
		{
			m_MaterialPrefabs[i] = references.Check(base.EntityManager, m_MaterialPrefabs[i]);
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
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
		m_MaterialPrefabs.Clear();
	}
```

- `public UpdateMaterial(UnityEngine.Material material) : System.Void`  

```csharp
public void UpdateMaterial(Material material)
	{
		material.SetTexture(ShaderID._Splatmap, splatmap);
		material.SetTexture(ShaderID._BackdropSnowHeightTexture, m_SnowSystem.SnowHeightBackdropTexture);
		float2 @float = new float2(m_TerrainVTBorder) / (m_TerrainSystem.playableArea + 2f * m_TerrainVTBorder);
		float4 float2 = new float4(1f / @float, @float);
		float4 float3 = new float4(m_TerrainSystem.playableArea / (m_TerrainSystem.playableArea + 2f * m_TerrainVTBorder), @float);
		material.SetVector(ShaderID._VTInvBorder, float2);
		material.SetVector(ShaderID._PlayableScaleOffset, float3);
		Shader.SetGlobalTexture(ShaderID._COSplatmap, m_SplatMap);
		Shader.SetGlobalTexture(ShaderID._COWorldSplatmap, m_SplatWorldMap);
		Shader.SetGlobalVector(ShaderID._COInvVTBorder, float2);
		Shader.SetGlobalVector(ShaderID._COPlayableScaleOffset, float3);
	}
```

- `private UpdateSplatmap(UnityEngine.Rendering.CommandBuffer cmd, Unity.Mathematics.float4 viewport, System.Boolean bWorldUpdate) : System.Void`  

```csharp
private void UpdateSplatmap(CommandBuffer cmd, float4 viewport, bool bWorldUpdate)
	{
		log.Trace("UpdateSplatmap");
		cmd.Clear();
		float4 @float = new float4((m_TerrainSystem.worldOffset - m_TerrainSystem.playableOffset) / m_TerrainSystem.playableArea, m_TerrainSystem.worldSize / m_TerrainSystem.playableArea);
		float4 float2 = new float4(m_TerrainSystem.heightScaleOffset, 0f, 0f);
		float4 float3 = new float4(0.2f, 0.4f, -1f, 0f);
		float4 float4 = new float4(500f, 1500f, 0.75f, 0f);
		float4 float5 = new float4(20f, 300f, 500f, 0.5f);
		float4 float6 = new float4(1f, 1f, 0.001f, 0.002f);
		Texture cascadeTexture = m_TerrainSystem.GetCascadeTexture();
		m_Properties.Clear();
		m_Properties.SetTexture(ShaderID._HeightmapArray, cascadeTexture);
		m_Properties.SetTexture(ShaderID._WaterTexture, m_WaterRenderSystem.waterTexture ?? Texture2D.blackTexture);
		m_Properties.SetTexture(ShaderID._NoiseTex, m_Noise);
		m_Properties.SetInt(ShaderID._HeightMapArrayIndex, TerrainSystem.baseLod);
		m_Properties.SetVector(ShaderID._HeightScaleOffset, float2);
		m_Properties.SetVector(ShaderID._HeightMapArrayOffsetScale, viewport);
		m_Properties.SetVector(ShaderID._VTScaleOffset, new Vector4(1f, 1f, 0f, 0f));
		m_Properties.SetVector(ShaderID._SplatHeightVariance, float3);
		m_Properties.SetVector(ShaderID._SplatRockLimit, float4);
		m_Properties.SetVector(ShaderID._SplatGrassLimit, float5);
		m_Properties.SetVector(ShaderID._NoiseOffset, float6);
		m_Properties.SetVector(ShaderID._WaterTextureOffsetScale, viewport);
		m_Properties.SetFloat(ShaderID._WorldAdjust, 1f);
		Rect viewport2 = new Rect(viewport.x * (float)m_SplatMap.width, viewport.y * (float)m_SplatMap.height, viewport.z * (float)m_SplatMap.width, viewport.w * (float)m_SplatMap.height);
		bool flag = viewport.x == 0f && viewport.y == 0f && viewport.z == 1f && viewport.w == 1f;
		cmd.SetRenderTarget(m_SplatMap, flag ? RenderBufferLoadAction.DontCare : RenderBufferLoadAction.Load, RenderBufferStoreAction.Store);
		cmd.SetViewProjectionMatrices(Matrix4x4.identity, Matrix4x4.identity);
		cmd.SetViewport(viewport2);
		cmd.DrawMesh(m_BlitMesh, Matrix4x4.identity, m_SplatMaterial, 0, 0, m_Properties);
		if (bWorldUpdate)
		{
			cmd.SetRenderTarget(m_SplatWorldMap, RenderBufferLoadAction.DontCare, RenderBufferStoreAction.Store);
			cmd.SetViewport(new Rect(0f, 0f, m_SplatWorldMap.width, m_SplatWorldMap.height));
			m_Properties.SetInt(ShaderID._HeightMapArrayIndex, 0);
			m_Properties.SetVector(ShaderID._HeightMapArrayOffsetScale, new Vector4(0f, 0f, 1f, 1f));
			m_Properties.SetVector(ShaderID._WaterTextureOffsetScale, @float);
			float3.xy *= 0.25f;
			m_Properties.SetVector(ShaderID._SplatHeightVariance, float3);
			m_Properties.SetFloat(ShaderID._WorldAdjust, 0.7f);
			cmd.DrawMesh(m_BlitMesh, Matrix4x4.identity, m_SplatMaterial, 0, 0, m_Properties);
		}
	}
```


## Nested types

- `Game.Rendering.TerrainMaterialSystem+ShaderID`  

