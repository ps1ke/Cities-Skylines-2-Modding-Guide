# Game.Rendering.TerrainRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `FormerlySerializedAs`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem`  
- `private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem`  
- `private Game.Simulation.SnowSystem m_SnowSystem`  
- `private UnityEngine.Texture <overrideOverlaymap>k__BackingField`  
- `private UnityEngine.Texture <overlayExtramap>k__BackingField`  
- `private Unity.Mathematics.float4 <overlayArrowMask>k__BackingField`  
- `private UnityEngine.Material m_CachedMaterial`  

## Properties

- `public UnityEngine.Texture overrideOverlaymap { get; set }`  
- `public UnityEngine.Texture overlayExtramap { get; set }`  
- `public Unity.Mathematics.float4 overlayArrowMask { get; set }`  
- `private UnityEngine.Material material { private get; private set }`  

## Constructors

- `public TerrainRenderSystem()`  

## Methods

- `public GetCascadeCullArea(System.Int32 index) : UnityEngine.Bounds`  
- `public GetCascadeRegion(System.Int32 index) : UnityEngine.Bounds`  
- `public GetCascadeViewport(System.Int32 index) : UnityEngine.Bounds`  
- `public GetLastCullArea() : UnityEngine.Bounds`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SetKeywords(UnityEngine.Material materialToUpdate) : System.Void`  
- `private UpdateMaterial() : System.Void`  

## Nested types

- `Game.Rendering.TerrainRenderSystem+ShaderID`  

