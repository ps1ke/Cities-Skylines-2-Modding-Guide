# Game.Rendering.WaterRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Code

```csharp
public class WaterRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private UnityEngine.Texture <overrideOverlaymap>k__BackingField;
    private UnityEngine.Texture <overlayExtramap>k__BackingField;
    private Unity.Mathematics.float4 <overlayPollutionMask>k__BackingField;
    private Unity.Mathematics.float4 <overlayArrowMask>k__BackingField;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private System.Boolean <IsAsync>k__BackingField;

    public UnityEngine.Texture overrideOverlaymap { get; set; }
    public UnityEngine.Texture overlayExtramap { get; set; }
    public Unity.Mathematics.float4 overlayPollutionMask { get; set; }
    public Unity.Mathematics.float4 overlayArrowMask { get; set; }
    public UnityEngine.Texture waterTexture { get; }
    public UnityEngine.Texture flowTexture { get; }
    public System.Boolean IsAsync { get; set; }

    public WaterRenderSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem`  

```csharp
private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private UnityEngine.Texture <overrideOverlaymap>k__BackingField`  

```csharp
private UnityEngine.Texture <overrideOverlaymap>k__BackingField;
```

- `private UnityEngine.Texture <overlayExtramap>k__BackingField`  

```csharp
private UnityEngine.Texture <overlayExtramap>k__BackingField;
```

- `private Unity.Mathematics.float4 <overlayPollutionMask>k__BackingField`  

```csharp
private Unity.Mathematics.float4 <overlayPollutionMask>k__BackingField;
```

- `private Unity.Mathematics.float4 <overlayArrowMask>k__BackingField`  

```csharp
private Unity.Mathematics.float4 <overlayArrowMask>k__BackingField;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private System.Boolean <IsAsync>k__BackingField`  

```csharp
private System.Boolean <IsAsync>k__BackingField;
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

- `public Unity.Mathematics.float4 overlayPollutionMask { get; set }`  

```csharp
public Unity.Mathematics.float4 overlayPollutionMask { get; set; }
```

- `public Unity.Mathematics.float4 overlayArrowMask { get; set }`  

```csharp
public Unity.Mathematics.float4 overlayArrowMask { get; set; }
```

- `public UnityEngine.Texture waterTexture { get }`  

```csharp
public UnityEngine.Texture waterTexture { get; }
```

- `public UnityEngine.Texture flowTexture { get }`  

```csharp
public UnityEngine.Texture flowTexture { get; }
```

- `public System.Boolean IsAsync { get; set }`  

```csharp
public System.Boolean IsAsync { get; set; }
```


## Constructors

- `public WaterRenderSystem()`  

```csharp
[Preserve]
	public WaterRenderSystem()
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
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		foreach (WaterSurface instance in WaterSurface.instances)
		{
			if (instance.customMaterial != null)
			{
				instance.customMaterial = new Material(instance.customMaterial);
			}
		}
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		foreach (WaterSurface instance in WaterSurface.instances)
		{
			if (instance.customMaterial != null)
			{
				CoreUtils.Destroy(instance.customMaterial);
			}
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_TerrainSystem.GetCascadeInfo(out var _, out var baseLOD, out var areas, out var _, out var _);
		foreach (WaterSurface instance in WaterSurface.instances)
		{
			float timeMultiplier = m_RenderingSystem.frameDelta / math.max(1E-06f, base.CheckedStateRef.WorldUnmanaged.Time.DeltaTime * 60f);
			instance.timeMultiplier = timeMultiplier;
			instance.CascadeArea = areas;
			if (baseLOD == 0)
			{
				instance.WaterSimArea = new Vector4(areas.c0.x, areas.c1.x, areas.c2.x - areas.c0.x, areas.c3.x - areas.c1.x);
			}
			else
			{
				instance.WaterSimArea = new Vector4(areas.c0.y, areas.c1.y, areas.c2.y - areas.c0.y, areas.c3.y - areas.c1.y);
			}
			instance.TerrainScaleOffset = m_TerrainSystem.heightScaleOffset;
			instance.TerrainCascadeTexture = m_TerrainSystem.GetCascadeTexture();
			if (m_WaterSystem.Loaded)
			{
				instance.WaterSimulationTexture = m_WaterSystem.WaterTexture;
			}
			else
			{
				instance.WaterSimulationTexture = Texture2D.blackTexture;
			}
			if (!instance.customMaterial)
			{
				continue;
			}
			instance.customMaterial.SetVector(TerrainRenderSystem.ShaderID._OverlayArrowMask, overlayArrowMask);
			instance.customMaterial.SetVector(TerrainRenderSystem.ShaderID._OverlayPollutionMask, overlayPollutionMask);
			if (overrideOverlaymap != null)
			{
				instance.customMaterial.SetTexture(TerrainRenderSystem.ShaderID._BaseColorMap, overrideOverlaymap);
			}
			if (overlayExtramap != null)
			{
				if (overrideOverlaymap == null)
				{
					overrideOverlaymap = Texture2D.whiteTexture;
				}
				if (overlayExtramap == flowTexture)
				{
					instance.customMaterial.SetFloat(TerrainRenderSystem.ShaderID._OverlayArrowSource, 1f);
				}
				else
				{
					instance.customMaterial.SetTexture(TerrainRenderSystem.ShaderID._OverlayExtra, overlayExtramap);
					instance.customMaterial.SetFloat(TerrainRenderSystem.ShaderID._OverlayArrowSource, 0f);
				}
				instance.customMaterial.EnableKeyword("OVERRIDE_OVERLAY_EXTRA");
			}
			else
			{
				instance.customMaterial.DisableKeyword("OVERRIDE_OVERLAY_EXTRA");
			}
		}
		_ = m_WaterSystem.Loaded;
	}
```


