# Game.Rendering.WaterRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Fields

- `private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private UnityEngine.Texture <overrideOverlaymap>k__BackingField`  
- `private UnityEngine.Texture <overlayExtramap>k__BackingField`  
- `private Unity.Mathematics.float4 <overlayPollutionMask>k__BackingField`  
- `private Unity.Mathematics.float4 <overlayArrowMask>k__BackingField`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private System.Boolean <IsAsync>k__BackingField`  

## Properties

- `public UnityEngine.Texture overrideOverlaymap { get; set }`  
- `public UnityEngine.Texture overlayExtramap { get; set }`  
- `public Unity.Mathematics.float4 overlayPollutionMask { get; set }`  
- `public Unity.Mathematics.float4 overlayArrowMask { get; set }`  
- `public UnityEngine.Texture waterTexture { get }`  
- `public UnityEngine.Texture flowTexture { get }`  
- `public System.Boolean IsAsync { get; set }`  

## Constructors

- `public WaterRenderSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

