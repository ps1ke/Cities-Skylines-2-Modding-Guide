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
public VegetationRenderSystem();
```


## Methods

- `private CreateDynamicVFXIfNeeded() : System.Void`  

```csharp
private System.Void CreateDynamicVFXIfNeeded();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private UpdateEffect() : System.Void`  

```csharp
private System.Void UpdateEffect();
```


