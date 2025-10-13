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
public TerrainRenderSystem();
```


## Methods

- `public GetCascadeCullArea(System.Int32 index) : UnityEngine.Bounds`  

```csharp
public UnityEngine.Bounds GetCascadeCullArea(System.Int32 index);
```

- `public GetCascadeRegion(System.Int32 index) : UnityEngine.Bounds`  

```csharp
public UnityEngine.Bounds GetCascadeRegion(System.Int32 index);
```

- `public GetCascadeViewport(System.Int32 index) : UnityEngine.Bounds`  

```csharp
public UnityEngine.Bounds GetCascadeViewport(System.Int32 index);
```

- `public GetLastCullArea() : UnityEngine.Bounds`  

```csharp
public UnityEngine.Bounds GetLastCullArea();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private SetKeywords(UnityEngine.Material materialToUpdate) : System.Void`  

```csharp
private System.Void SetKeywords(UnityEngine.Material materialToUpdate);
```

- `private UpdateMaterial() : System.Void`  

```csharp
private System.Void UpdateMaterial();
```


## Nested types

- `Game.Rendering.TerrainRenderSystem+ShaderID`  

