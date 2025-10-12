# Colossal.Rendering.DebugCustomPass

**Assembly:** `Game`  
**Namespace:** `Colossal.Rendering`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.HighDefinition.CustomPass`  
**Implements:** `UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>`  

## Fields

- `private UnityEngine.Material m_DebugBlitMaterial`  
- `private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock`  
- `private UnityEngine.ComputeBuffer m_TopViewRenderIndirectArgs`  
- `private UnityEngine.Material m_TopViewMaterial`  
- `private UnityEngine.Rendering.RTHandle m_TopViewRenderTexture`  
- `private System.Int32 <activeInstance>k__BackingField`  
- `private System.Int32 <sliceIndex>k__BackingField`  
- `private System.Single <debugOverlayRatio>k__BackingField`  
- `private Colossal.Rendering.DebugCustomPass+TextureDebugMode <textureDebugMode>k__BackingField`  
- `private System.Single <zoom>k__BackingField`  
- `private System.Boolean <showExtra>k__BackingField`  
- `private System.Single <minValue>k__BackingField`  
- `private System.Single <maxValue>k__BackingField`  
- `private static const System.Int32 kPadding`  
- `public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kGlobalMapStart`  
- `public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kGlobalMapEnd`  
- `public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kWaterSimulationMapStart`  
- `public static const Colossal.Rendering.DebugCustomPass+TextureDebugMode kWaterSimulationMapEnd`  

## Properties

- `public System.Int32 activeInstance { get; set }`  
- `public System.Int32 sliceIndex { get; set }`  
- `public System.Single debugOverlayRatio { get; set }`  
- `public Colossal.Rendering.DebugCustomPass+TextureDebugMode textureDebugMode { get; set }`  
- `public System.Single zoom { get; set }`  
- `public System.Boolean showExtra { get; set }`  
- `public System.Single minValue { get; set }`  
- `public System.Single maxValue { get; set }`  

## Constructors

- `public DebugCustomPass()`  

## Methods

- `private CheckResources(System.Int32 size) : System.Void`  
- `protected virtual Cleanup() : System.Void`  
- `private static DisplayTexture(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Rect viewportSize, UnityEngine.Texture texture, UnityEngine.Material debugMaterial, System.Int32 mode, UnityEngine.MaterialPropertyBlock mpb, System.Boolean applyExposure) : System.Void`  
- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  
- `private static GetCustomPass<T>(System.String passName, UnityEngine.Rendering.HighDefinition.CustomPassInjectionPoint injectionPoint) : T`  
- `private GetDebugTesselationTexture() : UnityEngine.Texture`  
- `public GetDefaultMaxValue() : System.Single`  
- `public GetDefaultMinValue() : System.Single`  
- `public GetMaxValue() : System.Single`  
- `public GetMinValue() : System.Single`  
- `private static GetRuntimeDebugPanelWidth(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Int32`  
- `private static GetRuntimePadding(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Int32`  
- `private static GetSystem<T>() : T`  
- `public HasExtra() : System.Boolean`  
- `private static RemToPxScale(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Single`  
- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `public SetupTexture(UnityEngine.Texture& tex, System.Int32& sliceCount) : System.Boolean`  

## Nested types

- `Colossal.Rendering.DebugCustomPass+TextureDebugMode`  

