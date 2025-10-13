# Colossal.Rendering.DebugCustomPass

**Assembly:** `Game`  
**Namespace:** `Colossal.Rendering`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.HighDefinition.CustomPass`  
**Implements:** `UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>`  

## Code

```csharp
public class DebugCustomPass : UnityEngine.Rendering.HighDefinition.CustomPass, UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>
{
    private UnityEngine.Material m_DebugBlitMaterial;
    private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock;
    private UnityEngine.ComputeBuffer m_TopViewRenderIndirectArgs;
    private UnityEngine.Material m_TopViewMaterial;
    private UnityEngine.Rendering.RTHandle m_TopViewRenderTexture;
    private System.Int32 <activeInstance>k__BackingField;
    private System.Int32 <sliceIndex>k__BackingField;
    private System.Single <debugOverlayRatio>k__BackingField;
    private Colossal.Rendering.DebugCustomPass+TextureDebugMode <textureDebugMode>k__BackingField;
    private System.Single <zoom>k__BackingField;
    private System.Boolean <showExtra>k__BackingField;
    private System.Single <minValue>k__BackingField;
    private System.Single <maxValue>k__BackingField;
    private static const System.Int32 kPadding;
    public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kGlobalMapStart;
    public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kGlobalMapEnd;
    public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kWaterSimulationMapStart;
    public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kWaterSimulationMapEnd;

    public System.Int32 activeInstance { get; set; }
    public System.Int32 sliceIndex { get; set; }
    public System.Single debugOverlayRatio { get; set; }
    public Colossal.Rendering.DebugCustomPass+TextureDebugMode textureDebugMode { get; set; }
    public System.Single zoom { get; set; }
    public System.Boolean showExtra { get; set; }
    public System.Single minValue { get; set; }
    public System.Single maxValue { get; set; }

    public DebugCustomPass();

    private System.Void CheckResources(System.Int32 size);
    protected virtual System.Void Cleanup();
    private static System.Void DisplayTexture(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Rect viewportSize, UnityEngine.Texture texture, UnityEngine.Material debugMaterial, System.Int32 mode, UnityEngine.MaterialPropertyBlock mpb, System.Boolean applyExposure);
    protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
    private static T GetCustomPass<T>(System.String passName, UnityEngine.Rendering.HighDefinition.CustomPassInjectionPoint injectionPoint);
    private UnityEngine.Texture GetDebugTesselationTexture();
    public System.Single GetDefaultMaxValue();
    public System.Single GetDefaultMinValue();
    public System.Single GetMaxValue();
    public System.Single GetMinValue();
    private static System.Int32 GetRuntimeDebugPanelWidth(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
    private static System.Int32 GetRuntimePadding(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
    private static T GetSystem<T>();
    public System.Boolean HasExtra();
    private static System.Single RemToPxScale(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
    protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
    public System.Boolean SetupTexture(UnityEngine.Texture& tex, System.Int32& sliceCount);
}
```


## Fields

- `private UnityEngine.Material m_DebugBlitMaterial`  

```csharp
private UnityEngine.Material m_DebugBlitMaterial;
```

- `private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock`  

```csharp
private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock;
```

- `private UnityEngine.ComputeBuffer m_TopViewRenderIndirectArgs`  

```csharp
private UnityEngine.ComputeBuffer m_TopViewRenderIndirectArgs;
```

- `private UnityEngine.Material m_TopViewMaterial`  

```csharp
private UnityEngine.Material m_TopViewMaterial;
```

- `private UnityEngine.Rendering.RTHandle m_TopViewRenderTexture`  

```csharp
private UnityEngine.Rendering.RTHandle m_TopViewRenderTexture;
```

- `private System.Int32 <activeInstance>k__BackingField`  

```csharp
private System.Int32 <activeInstance>k__BackingField;
```

- `private System.Int32 <sliceIndex>k__BackingField`  

```csharp
private System.Int32 <sliceIndex>k__BackingField;
```

- `private System.Single <debugOverlayRatio>k__BackingField`  

```csharp
private System.Single <debugOverlayRatio>k__BackingField;
```

- `private Colossal.Rendering.DebugCustomPass+TextureDebugMode <textureDebugMode>k__BackingField`  

```csharp
private Colossal.Rendering.DebugCustomPass+TextureDebugMode <textureDebugMode>k__BackingField;
```

- `private System.Single <zoom>k__BackingField`  

```csharp
private System.Single <zoom>k__BackingField;
```

- `private System.Boolean <showExtra>k__BackingField`  

```csharp
private System.Boolean <showExtra>k__BackingField;
```

- `private System.Single <minValue>k__BackingField`  

```csharp
private System.Single <minValue>k__BackingField;
```

- `private System.Single <maxValue>k__BackingField`  

```csharp
private System.Single <maxValue>k__BackingField;
```

- `private static const System.Int32 kPadding`  

```csharp
private static const System.Int32 kPadding;
```

- `public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kGlobalMapStart`  

```csharp
public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kGlobalMapStart;
```

- `public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kGlobalMapEnd`  

```csharp
public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kGlobalMapEnd;
```

- `public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kWaterSimulationMapStart`  

```csharp
public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kWaterSimulationMapStart;
```

- `public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kWaterSimulationMapEnd`  

```csharp
public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kWaterSimulationMapEnd;
```


## Properties

- `public System.Int32 activeInstance { get; set }`  

```csharp
public System.Int32 activeInstance { get; set; }
```

- `public System.Int32 sliceIndex { get; set }`  

```csharp
public System.Int32 sliceIndex { get; set; }
```

- `public System.Single debugOverlayRatio { get; set }`  

```csharp
public System.Single debugOverlayRatio { get; set; }
```

- `public Colossal.Rendering.DebugCustomPass+TextureDebugMode textureDebugMode { get; set }`  

```csharp
public Colossal.Rendering.DebugCustomPass+TextureDebugMode textureDebugMode { get; set; }
```

- `public System.Single zoom { get; set }`  

```csharp
public System.Single zoom { get; set; }
```

- `public System.Boolean showExtra { get; set }`  

```csharp
public System.Boolean showExtra { get; set; }
```

- `public System.Single minValue { get; set }`  

```csharp
public System.Single minValue { get; set; }
```

- `public System.Single maxValue { get; set }`  

```csharp
public System.Single maxValue { get; set; }
```


## Constructors

- `public DebugCustomPass()`  

```csharp
public DebugCustomPass();
```


## Methods

- `private CheckResources(System.Int32 size) : System.Void`  

```csharp
private System.Void CheckResources(System.Int32 size);
```

- `protected virtual Cleanup() : System.Void`  

```csharp
protected virtual System.Void Cleanup();
```

- `private static DisplayTexture(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Rect viewportSize, UnityEngine.Texture texture, UnityEngine.Material debugMaterial, System.Int32 mode, UnityEngine.MaterialPropertyBlock mpb, System.Boolean applyExposure) : System.Void`  

```csharp
private static System.Void DisplayTexture(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Rect viewportSize, UnityEngine.Texture texture, UnityEngine.Material debugMaterial, System.Int32 mode, UnityEngine.MaterialPropertyBlock mpb, System.Boolean applyExposure);
```

- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
```

- `private static GetCustomPass<T>(System.String passName, UnityEngine.Rendering.HighDefinition.CustomPassInjectionPoint injectionPoint) : T`  

```csharp
private static T GetCustomPass<T>(System.String passName, UnityEngine.Rendering.HighDefinition.CustomPassInjectionPoint injectionPoint);
```

- `private GetDebugTesselationTexture() : UnityEngine.Texture`  

```csharp
private UnityEngine.Texture GetDebugTesselationTexture();
```

- `public GetDefaultMaxValue() : System.Single`  

```csharp
public System.Single GetDefaultMaxValue();
```

- `public GetDefaultMinValue() : System.Single`  

```csharp
public System.Single GetDefaultMinValue();
```

- `public GetMaxValue() : System.Single`  

```csharp
public System.Single GetMaxValue();
```

- `public GetMinValue() : System.Single`  

```csharp
public System.Single GetMinValue();
```

- `private static GetRuntimeDebugPanelWidth(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Int32`  

```csharp
private static System.Int32 GetRuntimeDebugPanelWidth(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
```

- `private static GetRuntimePadding(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Int32`  

```csharp
private static System.Int32 GetRuntimePadding(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
```

- `private static GetSystem<T>() : T`  

```csharp
private static T GetSystem<T>();
```

- `public HasExtra() : System.Boolean`  

```csharp
public System.Boolean HasExtra();
```

- `private static RemToPxScale(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Single`  

```csharp
private static System.Single RemToPxScale(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
```

- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
```

- `public SetupTexture(UnityEngine.Texture& tex, System.Int32& sliceCount) : System.Boolean`  

```csharp
public System.Boolean SetupTexture(UnityEngine.Texture& tex, System.Int32& sliceCount);
```


## Nested types

- `Colossal.Rendering.DebugCustomPass+TextureDebugMode`  

