# Game.Rendering.TerrainRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `FormerlySerializedAs`  

## Code

```csharp
public class TerrainRenderSystem : Game.GameSystemBase
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
    private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem;
    private Game.Simulation.SnowSystem m_SnowSystem;
    private UnityEngine.Texture <overrideOverlaymap>k__BackingField;
    private UnityEngine.Texture <overlayExtramap>k__BackingField;
    private Unity.Mathematics.float4 <overlayArrowMask>k__BackingField;
    private UnityEngine.Material m_CachedMaterial;

    public UnityEngine.Texture overrideOverlaymap { get; set; }
    public UnityEngine.Texture overlayExtramap { get; set; }
    public Unity.Mathematics.float4 overlayArrowMask { get; set; }
    private UnityEngine.Material material { private get; private set; }

    public TerrainRenderSystem();

    public UnityEngine.Bounds GetCascadeCullArea(System.Int32 index);
    public UnityEngine.Bounds GetCascadeRegion(System.Int32 index);
    public UnityEngine.Bounds GetCascadeViewport(System.Int32 index);
    public UnityEngine.Bounds GetLastCullArea();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void SetKeywords(UnityEngine.Material materialToUpdate);
    private System.Void UpdateMaterial();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem`  

```csharp
private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
```

- `private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem`  

```csharp
private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem;
```

- `private Game.Simulation.SnowSystem m_SnowSystem`  

```csharp
private Game.Simulation.SnowSystem m_SnowSystem;
```

- `private UnityEngine.Texture <overrideOverlaymap>k__BackingField`  

```csharp
private UnityEngine.Texture <overrideOverlaymap>k__BackingField;
```

- `private UnityEngine.Texture <overlayExtramap>k__BackingField`  

```csharp
private UnityEngine.Texture <overlayExtramap>k__BackingField;
```

- `private Unity.Mathematics.float4 <overlayArrowMask>k__BackingField`  

```csharp
private Unity.Mathematics.float4 <overlayArrowMask>k__BackingField;
```

- `private UnityEngine.Material m_CachedMaterial`  

```csharp
private UnityEngine.Material m_CachedMaterial;
```


## Properties

- `public UnityEngine.Texture overrideOverlaymap { get; set }`  

```csharp
public UnityEngine.Texture overrideOverlaymap { get; set; }
```

- `public UnityEngine.Texture overlayExtramap { get; set }`  

```csharp
public UnityEngine.Texture overlayExtramap { get; set; }
```

- `public Unity.Mathematics.float4 overlayArrowMask { get; set }`  

```csharp
public Unity.Mathematics.float4 overlayArrowMask { get; set; }
```

- `private UnityEngine.Material material { private get; private set }`  

```csharp
private UnityEngine.Material material { private get; private set; }
```


## Constructors

- `public TerrainRenderSystem()`  

```csharp
[Preserve]
	public TerrainRenderSystem()
	{
	}
```


## Methods

- `public GetCascadeCullArea(System.Int32 index) : UnityEngine.Bounds`  

```csharp
public Bounds GetCascadeCullArea(int index)
	{
		Bounds result = default(Bounds);
		if (index >= 0 && index < m_TerrainSystem.heightMapCullArea.Length)
		{
			float3 @float = new float3(m_TerrainSystem.heightMapCullArea[index].x, float.MaxValue, m_TerrainSystem.heightMapCullArea[index].y);
			result.SetMinMax(max: new float3(m_TerrainSystem.heightMapCullArea[index].z, float.MinValue, m_TerrainSystem.heightMapCullArea[index].w), min: @float);
		}
		return result;
	}
```

- `public GetCascadeRegion(System.Int32 index) : UnityEngine.Bounds`  

```csharp
public Bounds GetCascadeRegion(int index)
	{
		Bounds result = default(Bounds);
		if (index >= 0 && index < m_TerrainSystem.heightMapSliceArea.Length)
		{
			float3 @float = new float3(m_TerrainSystem.heightMapSliceArea[index].x, m_TerrainSystem.heightScaleOffset.x, m_TerrainSystem.heightMapSliceArea[index].y);
			result.SetMinMax(max: new float3(m_TerrainSystem.heightMapSliceArea[index].z, 0f, m_TerrainSystem.heightMapSliceArea[index].w), min: @float);
		}
		return result;
	}
```

- `public GetCascadeViewport(System.Int32 index) : UnityEngine.Bounds`  

```csharp
public Bounds GetCascadeViewport(int index)
	{
		Bounds result = default(Bounds);
		if (index >= 0 && index < m_TerrainSystem.heightMapViewportUpdated.Length)
		{
			float2 xy = m_TerrainSystem.heightMapSliceArea[index].xy;
			float2 @float = m_TerrainSystem.heightMapSliceArea[index].zw - m_TerrainSystem.heightMapSliceArea[index].xy;
			float3 zero = float3.zero;
			float3 zero2 = float3.zero;
			zero.xz = xy + @float * m_TerrainSystem.heightMapViewportUpdated[index].xy;
			zero2.xz = xy + @float * (m_TerrainSystem.heightMapViewportUpdated[index].xy + m_TerrainSystem.heightMapViewportUpdated[index].zw);
			zero.y = 0f;
			zero2.y = m_TerrainSystem.heightScaleOffset.x;
			result.SetMinMax(zero, zero2);
		}
		return result;
	}
```

- `public GetLastCullArea() : UnityEngine.Bounds`  

```csharp
public Bounds GetLastCullArea()
	{
		Bounds result = default(Bounds);
		float3 @float = new float3(m_TerrainSystem.lastCullArea.x, float.MaxValue, m_TerrainSystem.lastCullArea.y);
		result.SetMinMax(max: new float3(m_TerrainSystem.lastCullArea.z, float.MinValue, m_TerrainSystem.lastCullArea.w), min: @float);
		return result;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		RequireForUpdate<TerrainPropertiesData>();
		material = AssetDatabase.global.resources.terrain.renderMaterial;
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_TerrainMaterialSystem = base.World.GetOrCreateSystemManaged<TerrainMaterialSystem>();
		m_OverlayInfomodeSystem = base.World.GetOrCreateSystemManaged<OverlayInfomodeSystem>();
		m_SnowSystem = base.World.GetOrCreateSystemManaged<SnowSystem>();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		CoreUtils.Destroy(m_CachedMaterial);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		UpdateMaterial();
		if (m_TerrainSystem.heightMapRenderRequired)
		{
			m_TerrainSystem.RenderCascades();
		}
	}
```

- `private SetKeywords(UnityEngine.Material materialToUpdate) : System.Void`  

```csharp
private void SetKeywords(Material materialToUpdate)
	{
		if (overlayExtramap != null)
		{
			if (overrideOverlaymap == null)
			{
				overrideOverlaymap = Texture2D.whiteTexture;
			}
			materialToUpdate.EnableKeyword("OVERRIDE_OVERLAY_EXTRA");
			materialToUpdate.DisableKeyword("OVERRIDE_OVERLAY_SIMPLE");
		}
		else if (overrideOverlaymap != null)
		{
			materialToUpdate.DisableKeyword("OVERRIDE_OVERLAY_EXTRA");
			materialToUpdate.EnableKeyword("OVERRIDE_OVERLAY_SIMPLE");
		}
		else
		{
			materialToUpdate.DisableKeyword("OVERRIDE_OVERLAY_EXTRA");
			materialToUpdate.DisableKeyword("OVERRIDE_OVERLAY_SIMPLE");
		}
		if (TerrainSystem.baseLod == 0)
		{
			materialToUpdate.DisableKeyword("_PLAYABLEWORLDSELECT");
		}
		else
		{
			materialToUpdate.EnableKeyword("_PLAYABLEWORLDSELECT");
		}
	}
```

- `private UpdateMaterial() : System.Void`  

```csharp
private void UpdateMaterial()
	{
		TerrainSurface validSurface = TerrainSurface.GetValidSurface();
		m_TerrainSystem.GetCascadeInfo(out var _, out var baseLOD, out var areas, out var ranges, out var _);
		Shader.SetGlobalMatrix(ShaderID._COTerrainTextureArrayLODArea, areas);
		Shader.SetGlobalVector(ShaderID._COTerrainTextureArrayLODRange, ranges);
		Shader.SetGlobalInt(ShaderID._COTerrainTextureArrayBaseLod, baseLOD);
		Shader.SetGlobalVector(ShaderID._COTerrainHeightScaleOffset, new float4(m_TerrainSystem.heightScaleOffset.x, m_TerrainSystem.heightScaleOffset.y, 0f, 0f));
		if (validSurface == null)
		{
			return;
		}
		Material material = ((this.material == null) ? validSurface.material : this.material);
		if (!(material == null))
		{
			SetKeywords(material);
			material.SetMatrix(ShaderID._LODArea, areas);
			material.SetVector(ShaderID._LODRange, ranges);
			material.SetVector(ShaderID._TerrainScaleOffset, new float4(m_TerrainSystem.heightScaleOffset.x, m_TerrainSystem.heightScaleOffset.y, 0f, 0f));
			material.SetVector(ShaderID._VTScaleOffset, m_TerrainSystem.VTScaleOffset);
			Texture heightmap = m_TerrainSystem.heightmap;
			Texture texture = overrideOverlaymap;
			Texture snowDepth = m_SnowSystem.SnowDepth;
			Texture cascadeTexture = m_TerrainSystem.GetCascadeTexture();
			Texture splatmap = m_TerrainMaterialSystem.splatmap;
			if (heightmap != null)
			{
				material.SetTexture(ShaderID._HeightMap, heightmap);
			}
			if (splatmap != null)
			{
				material.SetTexture(ShaderID._SplatMap, splatmap);
			}
			if (cascadeTexture != null)
			{
				material.SetTexture(ShaderID._HeightMapArray, cascadeTexture);
			}
			if (texture != null)
			{
				material.SetTexture(ShaderID._BaseColorMap, texture);
			}
			if (overlayExtramap != null)
			{
				material.SetTexture(ShaderID._OverlayExtra, overlayExtramap);
			}
			if (snowDepth != null)
			{
				material.SetTexture(ShaderID._SnowMap, snowDepth);
			}
			material.SetVector(ShaderID._OverlayArrowMask, overlayArrowMask);
			m_TerrainMaterialSystem.UpdateMaterial(material);
			validSurface.material = material;
		}
	}
```


## Nested types

- `Game.Rendering.TerrainRenderSystem+ShaderID`  

