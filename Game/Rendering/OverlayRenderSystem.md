# Game.Rendering.OverlayRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class OverlayRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private UnityEngine.Mesh m_BoxMesh;
    private UnityEngine.Mesh m_QuadMesh;
    private UnityEngine.Material m_ProjectedMaterial;
    private UnityEngine.Material m_AbsoluteMaterial;
    private UnityEngine.ComputeBuffer m_ArgsBuffer;
    private UnityEngine.ComputeBuffer m_ProjectedBuffer;
    private UnityEngine.ComputeBuffer m_AbsoluteBuffer;
    private System.Collections.Generic.List<System.UInt32> m_ArgsArray;
    private System.Int32 m_ProjectedInstanceCount;
    private System.Int32 m_AbsoluteInstanceCount;
    private System.Int32 m_CurveBufferID;
    private System.Int32 m_GradientScaleID;
    private System.Int32 m_ScaleRatioAID;
    private System.Int32 m_FaceDilateID;
    private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedData;
    private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteData;
    private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_BoundsData;
    private Unity.Jobs.JobHandle m_BufferWriters;
    private TMPro.TextMeshPro m_TextMesh;

    public OverlayRenderSystem();

    public System.Void AddBufferWriter(Unity.Jobs.JobHandle handle);
    public System.Void CopyFontAtlasParameters(UnityEngine.Material source, UnityEngine.Material target);
    private TMPro.TMP_FontAsset CreateFont(Game.Prefabs.FontInfo info);
    public Game.Rendering.OverlayRenderSystem+Buffer GetBuffer(Unity.Jobs.JobHandle& dependencies);
    private System.Void GetCurveBuffer(UnityEngine.ComputeBuffer& buffer, System.Int32 count);
    private System.Void GetCurveMaterial(UnityEngine.Material& material, System.Boolean projected);
    private System.Void GetMesh(UnityEngine.Mesh& mesh, System.Boolean box);
    public TMPro.TextMeshPro GetTextMesh();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private UnityEngine.Mesh m_BoxMesh`  

```csharp
private UnityEngine.Mesh m_BoxMesh;
```

- `private UnityEngine.Mesh m_QuadMesh`  

```csharp
private UnityEngine.Mesh m_QuadMesh;
```

- `private UnityEngine.Material m_ProjectedMaterial`  

```csharp
private UnityEngine.Material m_ProjectedMaterial;
```

- `private UnityEngine.Material m_AbsoluteMaterial`  

```csharp
private UnityEngine.Material m_AbsoluteMaterial;
```

- `private UnityEngine.ComputeBuffer m_ArgsBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_ArgsBuffer;
```

- `private UnityEngine.ComputeBuffer m_ProjectedBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_ProjectedBuffer;
```

- `private UnityEngine.ComputeBuffer m_AbsoluteBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_AbsoluteBuffer;
```

- `private System.Collections.Generic.List<System.UInt32> m_ArgsArray`  

```csharp
private System.Collections.Generic.List<System.UInt32> m_ArgsArray;
```

- `private System.Int32 m_ProjectedInstanceCount`  

```csharp
private System.Int32 m_ProjectedInstanceCount;
```

- `private System.Int32 m_AbsoluteInstanceCount`  

```csharp
private System.Int32 m_AbsoluteInstanceCount;
```

- `private System.Int32 m_CurveBufferID`  

```csharp
private System.Int32 m_CurveBufferID;
```

- `private System.Int32 m_GradientScaleID`  

```csharp
private System.Int32 m_GradientScaleID;
```

- `private System.Int32 m_ScaleRatioAID`  

```csharp
private System.Int32 m_ScaleRatioAID;
```

- `private System.Int32 m_FaceDilateID`  

```csharp
private System.Int32 m_FaceDilateID;
```

- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedData;
```

- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteData;
```

- `private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_BoundsData`  

```csharp
private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_BoundsData;
```

- `private Unity.Jobs.JobHandle m_BufferWriters`  

```csharp
private Unity.Jobs.JobHandle m_BufferWriters;
```

- `private TMPro.TextMeshPro m_TextMesh`  

```csharp
private TMPro.TextMeshPro m_TextMesh;
```


## Constructors

- `public OverlayRenderSystem()`  

```csharp
[Preserve]
	public OverlayRenderSystem()
	{
	}
```


## Methods

- `public AddBufferWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddBufferWriter(JobHandle handle)
	{
		m_BufferWriters = JobHandle.CombineDependencies(m_BufferWriters, handle);
	}
```

- `public CopyFontAtlasParameters(UnityEngine.Material source, UnityEngine.Material target) : System.Void`  

```csharp
public void CopyFontAtlasParameters(Material source, Material target)
	{
		target.SetFloat(m_GradientScaleID, source.GetFloat(m_GradientScaleID) * 2f);
		target.SetFloat(m_ScaleRatioAID, source.GetFloat(m_ScaleRatioAID));
		target.mainTexture = source.mainTexture;
	}
```

- `private CreateFont(Game.Prefabs.FontInfo info) : TMPro.TMP_FontAsset`  

```csharp
private TMP_FontAsset CreateFont(FontInfo info)
	{
		TMP_FontAsset tMP_FontAsset = TMP_FontAsset.CreateFontAsset(info.m_Font, info.m_SamplingPointSize, info.m_AtlasPadding, GlyphRenderMode.SDFAA_HINTED, info.m_AtlasWidth, info.m_AtlasHeight);
		tMP_FontAsset.material.SetFloat(m_FaceDilateID, 1f);
		return tMP_FontAsset;
	}
```

- `public GetBuffer(Unity.Jobs.JobHandle& dependencies) : Game.Rendering.OverlayRenderSystem+Buffer`  

```csharp
public Buffer GetBuffer(out JobHandle dependencies)
	{
		if (!m_ProjectedData.IsCreated)
		{
			m_ProjectedData = new NativeList<CurveData>(Allocator.Persistent);
		}
		if (!m_AbsoluteData.IsCreated)
		{
			m_AbsoluteData = new NativeList<CurveData>(Allocator.Persistent);
		}
		if (!m_BoundsData.IsCreated)
		{
			m_BoundsData = new NativeValue<BoundsData>(Allocator.Persistent);
		}
		dependencies = m_BufferWriters;
		return new Buffer(m_ProjectedData, m_AbsoluteData, m_BoundsData, m_TerrainSystem.heightScaleOffset.y - 50f, m_TerrainSystem.heightScaleOffset.x + 100f);
	}
```

- `private GetCurveBuffer(UnityEngine.ComputeBuffer& buffer, System.Int32 count) : System.Void`  

```csharp
private unsafe void GetCurveBuffer(ref ComputeBuffer buffer, int count)
	{
		if (buffer != null && buffer.count < count)
		{
			count = math.max(buffer.count * 2, count);
			buffer.Release();
			buffer = null;
		}
		if (buffer == null)
		{
			buffer = new ComputeBuffer(math.max(64, count), sizeof(CurveData));
			buffer.name = "Overlay curve buffer";
		}
	}
```

- `private GetCurveMaterial(UnityEngine.Material& material, System.Boolean projected) : System.Void`  

```csharp
private void GetCurveMaterial(ref Material material, bool projected)
	{
		if (material == null)
		{
			OverlayConfigurationPrefab singletonPrefab = m_PrefabSystem.GetSingletonPrefab<OverlayConfigurationPrefab>(m_SettingsQuery);
			material = new Material(singletonPrefab.m_CurveMaterial);
			material.name = "Overlay curves";
			if (projected)
			{
				material.EnableKeyword("PROJECTED_MODE");
			}
		}
	}
```

- `private GetMesh(UnityEngine.Mesh& mesh, System.Boolean box) : System.Void`  

```csharp
private void GetMesh(ref Mesh mesh, bool box)
	{
		if (mesh == null)
		{
			mesh = new Mesh();
			mesh.name = "Overlay";
			if (box)
			{
				mesh.vertices = new Vector3[8]
				{
					new Vector3(-1f, 0f, -1f),
					new Vector3(-1f, 0f, 1f),
					new Vector3(1f, 0f, 1f),
					new Vector3(1f, 0f, -1f),
					new Vector3(-1f, 1f, -1f),
					new Vector3(-1f, 1f, 1f),
					new Vector3(1f, 1f, 1f),
					new Vector3(1f, 1f, -1f)
				};
				mesh.triangles = new int[36]
				{
					0, 1, 5, 5, 4, 0, 3, 7, 6, 6,
					2, 3, 0, 3, 2, 2, 1, 0, 4, 5,
					6, 6, 7, 4, 0, 4, 7, 7, 3, 0,
					1, 2, 6, 6, 5, 1
				};
			}
			else
			{
				mesh.vertices = new Vector3[4]
				{
					new Vector3(-1f, 0f, -1f),
					new Vector3(-1f, 0f, 1f),
					new Vector3(1f, 0f, 1f),
					new Vector3(1f, 0f, -1f)
				};
				mesh.triangles = new int[12]
				{
					0, 3, 2, 2, 1, 0, 0, 1, 2, 2,
					3, 0
				};
			}
		}
	}
```

- `public GetTextMesh() : TMPro.TextMeshPro`  

```csharp
public TextMeshPro GetTextMesh()
	{
		if (m_TextMesh == null)
		{
			OverlayConfigurationPrefab singletonPrefab = m_PrefabSystem.GetSingletonPrefab<OverlayConfigurationPrefab>(m_SettingsQuery);
			GameObject gameObject = new GameObject("TextMeshPro");
			UnityEngine.Object.DontDestroyOnLoad(gameObject);
			m_TextMesh = gameObject.AddComponent<TextMeshPro>();
			m_TextMesh.font = CreateFont(singletonPrefab.m_FontInfos[0]);
			m_TextMesh.font.fallbackFontAssetTable = new List<TMP_FontAsset>(singletonPrefab.m_FontInfos.Length - 1);
			for (int i = 1; i < singletonPrefab.m_FontInfos.Length; i++)
			{
				m_TextMesh.font.fallbackFontAssetTable.Add(CreateFont(singletonPrefab.m_FontInfos[i]));
			}
			m_TextMesh.renderer.enabled = false;
		}
		return m_TextMesh;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_SettingsQuery = GetEntityQuery(ComponentType.ReadOnly<OverlayConfigurationData>());
		m_CurveBufferID = Shader.PropertyToID("colossal_OverlayCurveBuffer");
		m_GradientScaleID = Shader.PropertyToID("_GradientScale");
		m_ScaleRatioAID = Shader.PropertyToID("_ScaleRatioA");
		m_FaceDilateID = Shader.PropertyToID("_FaceDilate");
		RenderPipelineManager.beginContextRendering += Render;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		RenderPipelineManager.beginContextRendering -= Render;
		if (m_BoxMesh != null)
		{
			UnityEngine.Object.Destroy(m_BoxMesh);
		}
		if (m_QuadMesh != null)
		{
			UnityEngine.Object.Destroy(m_QuadMesh);
		}
		if (m_ProjectedMaterial != null)
		{
			UnityEngine.Object.Destroy(m_ProjectedMaterial);
		}
		if (m_AbsoluteMaterial != null)
		{
			UnityEngine.Object.Destroy(m_AbsoluteMaterial);
		}
		if (m_ArgsBuffer != null)
		{
			m_ArgsBuffer.Release();
		}
		if (m_ProjectedBuffer != null)
		{
			m_ProjectedBuffer.Release();
		}
		if (m_AbsoluteBuffer != null)
		{
			m_AbsoluteBuffer.Release();
		}
		if (m_ProjectedData.IsCreated)
		{
			m_ProjectedData.Dispose();
		}
		if (m_AbsoluteData.IsCreated)
		{
			m_AbsoluteData.Dispose();
		}
		if (m_BoundsData.IsCreated)
		{
			m_BoundsData.Dispose();
		}
		if (m_TextMesh != null)
		{
			for (int i = 0; i < m_TextMesh.font.fallbackFontAssetTable.Count; i++)
			{
				UnityEngine.Object.Destroy(m_TextMesh.font.fallbackFontAssetTable[i]);
			}
			UnityEngine.Object.Destroy(m_TextMesh.font);
			UnityEngine.Object.Destroy(m_TextMesh.gameObject);
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_BufferWriters.Complete();
		m_BufferWriters = default(JobHandle);
		m_ProjectedInstanceCount = 0;
		m_AbsoluteInstanceCount = 0;
		if ((!m_ProjectedData.IsCreated || m_ProjectedData.Length == 0) && (!m_AbsoluteData.IsCreated || m_AbsoluteData.Length == 0))
		{
			return;
		}
		if (m_SettingsQuery.IsEmptyIgnoreFilter)
		{
			if (m_ProjectedData.IsCreated)
			{
				m_ProjectedData.Clear();
			}
			if (m_AbsoluteData.IsCreated)
			{
				m_AbsoluteData.Clear();
			}
			return;
		}
		if (m_ProjectedData.IsCreated && m_ProjectedData.Length != 0)
		{
			m_ProjectedInstanceCount = m_ProjectedData.Length;
			GetCurveMaterial(ref m_ProjectedMaterial, projected: true);
			GetCurveBuffer(ref m_ProjectedBuffer, m_ProjectedInstanceCount);
			m_ProjectedBuffer.SetData(m_ProjectedData.AsArray(), 0, 0, m_ProjectedInstanceCount);
			m_ProjectedMaterial.SetBuffer(m_CurveBufferID, m_ProjectedBuffer);
			m_ProjectedData.Clear();
		}
		if (m_AbsoluteData.IsCreated && m_AbsoluteData.Length != 0)
		{
			m_AbsoluteInstanceCount = m_AbsoluteData.Length;
			GetCurveMaterial(ref m_AbsoluteMaterial, projected: false);
			GetCurveBuffer(ref m_AbsoluteBuffer, m_AbsoluteInstanceCount);
			m_AbsoluteBuffer.SetData(m_AbsoluteData.AsArray(), 0, 0, m_AbsoluteInstanceCount);
			m_AbsoluteMaterial.SetBuffer(m_CurveBufferID, m_AbsoluteBuffer);
			m_AbsoluteData.Clear();
		}
	}
```

- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

```csharp
private void Render(ScriptableRenderContext context, List<Camera> cameras)
	{
		try
		{
			if (m_RenderingSystem.hideOverlay)
			{
				return;
			}
			int num = 0;
			if (m_ProjectedInstanceCount != 0)
			{
				num += 5;
			}
			if (m_AbsoluteInstanceCount != 0)
			{
				num += 5;
			}
			if (num == 0)
			{
				return;
			}
			if (m_ArgsBuffer != null && m_ArgsBuffer.count < num)
			{
				m_ArgsBuffer.Release();
				m_ArgsBuffer = null;
			}
			if (m_ArgsBuffer == null)
			{
				m_ArgsBuffer = new ComputeBuffer(num, 4, ComputeBufferType.DrawIndirect);
				m_ArgsBuffer.name = "Overlay args buffer";
			}
			if (m_ArgsArray == null)
			{
				m_ArgsArray = new List<uint>();
			}
			m_ArgsArray.Clear();
			Bounds bounds = RenderingUtils.ToBounds(m_BoundsData.value.m_CurveBounds);
			int num2 = 0;
			int num3 = 0;
			if (m_ProjectedInstanceCount != 0)
			{
				GetMesh(ref m_BoxMesh, box: true);
				GetCurveMaterial(ref m_ProjectedMaterial, projected: true);
				num2 = m_ArgsArray.Count;
				m_ArgsArray.Add(m_BoxMesh.GetIndexCount(0));
				m_ArgsArray.Add((uint)m_ProjectedInstanceCount);
				m_ArgsArray.Add(m_BoxMesh.GetIndexStart(0));
				m_ArgsArray.Add(m_BoxMesh.GetBaseVertex(0));
				m_ArgsArray.Add(0u);
			}
			if (m_AbsoluteInstanceCount != 0)
			{
				GetMesh(ref m_QuadMesh, box: false);
				GetCurveMaterial(ref m_AbsoluteMaterial, projected: false);
				num3 = m_ArgsArray.Count;
				m_ArgsArray.Add(m_QuadMesh.GetIndexCount(0));
				m_ArgsArray.Add((uint)m_AbsoluteInstanceCount);
				m_ArgsArray.Add(m_QuadMesh.GetIndexStart(0));
				m_ArgsArray.Add(m_QuadMesh.GetBaseVertex(0));
				m_ArgsArray.Add(0u);
			}
			foreach (Camera camera in cameras)
			{
				if (camera.cameraType == CameraType.Game || camera.cameraType == CameraType.SceneView)
				{
					if (m_ProjectedInstanceCount != 0)
					{
						Graphics.DrawMeshInstancedIndirect(m_BoxMesh, 0, m_ProjectedMaterial, bounds, m_ArgsBuffer, num2 * 4, null, ShadowCastingMode.Off, receiveShadows: false, 0, camera);
					}
					if (m_AbsoluteInstanceCount != 0)
					{
						Graphics.DrawMeshInstancedIndirect(m_QuadMesh, 0, m_AbsoluteMaterial, bounds, m_ArgsBuffer, num3 * 4, null, ShadowCastingMode.Off, receiveShadows: false, 0, camera);
					}
				}
			}
			m_ArgsBuffer.SetData(m_ArgsArray, 0, 0, m_ArgsArray.Count);
		}
		finally
		{
		}
	}
```


## Nested types

- `Game.Rendering.OverlayRenderSystem+CurveData`  
- `Game.Rendering.OverlayRenderSystem+BoundsData`  
- `Game.Rendering.OverlayRenderSystem+StyleFlags`  
- `Game.Rendering.OverlayRenderSystem+Buffer`  

