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
public WaterRenderSystem();
```


## Methods

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


