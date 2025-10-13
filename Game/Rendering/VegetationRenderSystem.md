# Game.Rendering.VegetationRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class VegetationRenderSystem : Game.GameSystemBase
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private UnityEngine.VFX.VisualEffect m_FoliageVFX;
    private static UnityEngine.VFX.VisualEffectAsset s_FoliageVFXAsset;

    public VegetationRenderSystem();

    private System.Void CreateDynamicVFXIfNeeded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    private System.Void UpdateEffect();
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

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private UnityEngine.VFX.VisualEffect m_FoliageVFX`  

```csharp
private UnityEngine.VFX.VisualEffect m_FoliageVFX;
```

- `private static UnityEngine.VFX.VisualEffectAsset s_FoliageVFXAsset`  

```csharp
private static UnityEngine.VFX.VisualEffectAsset s_FoliageVFXAsset;
```


## Constructors

- `public VegetationRenderSystem()`  

```csharp
[Preserve]
	public VegetationRenderSystem()
	{
	}
```


## Methods

- `private CreateDynamicVFXIfNeeded() : System.Void`  

```csharp
private void CreateDynamicVFXIfNeeded()
	{
		if (s_FoliageVFXAsset != null && m_FoliageVFX == null)
		{
			COSystemBase.baseLog.DebugFormat("Creating FoliageVFX");
			m_FoliageVFX = new GameObject("FoliageVFX").AddComponent<VisualEffect>();
			m_FoliageVFX.visualEffectAsset = s_FoliageVFXAsset;
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_TerrainMaterialSystem = base.World.GetOrCreateSystemManaged<TerrainMaterialSystem>();
		s_FoliageVFXAsset = Resources.Load<VisualEffectAsset>("Vegetation/FoliageVFX");
		base.Enabled = false;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
		CoreUtils.Destroy(m_FoliageVFX);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_CameraUpdateSystem.activeViewer != null)
		{
			CreateDynamicVFXIfNeeded();
			UpdateEffect();
		}
	}
```

- `private UpdateEffect() : System.Void`  

```csharp
private void UpdateEffect()
	{
		Bounds terrainBounds = m_TerrainSystem.GetTerrainBounds();
		m_FoliageVFX.SetVector3("TerrainBounds_center", terrainBounds.center);
		m_FoliageVFX.SetVector3("TerrainBounds_size", terrainBounds.size);
		m_FoliageVFX.SetTexture("Terrain HeightMap", m_TerrainSystem.heightmap);
		m_FoliageVFX.SetTexture("Terrain SplatMap", m_TerrainMaterialSystem.splatmap);
		Vector4 globalVector = Shader.GetGlobalVector("colossal_TerrainScale");
		Vector4 globalVector2 = Shader.GetGlobalVector("colossal_TerrainOffset");
		m_FoliageVFX.SetVector4("Terrain Offset Scale", new Vector4(globalVector.x, globalVector.z, globalVector2.x, globalVector2.z));
		m_FoliageVFX.SetVector3("CameraPosition", m_CameraUpdateSystem.position);
		m_FoliageVFX.SetVector3("CameraDirection", m_CameraUpdateSystem.direction);
	}
```


