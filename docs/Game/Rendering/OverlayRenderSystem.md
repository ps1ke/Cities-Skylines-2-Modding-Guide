# Game.Rendering.OverlayRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_SettingsQuery`  
- `private UnityEngine.Mesh m_BoxMesh`  
- `private UnityEngine.Mesh m_QuadMesh`  
- `private UnityEngine.Material m_ProjectedMaterial`  
- `private UnityEngine.Material m_AbsoluteMaterial`  
- `private UnityEngine.ComputeBuffer m_ArgsBuffer`  
- `private UnityEngine.ComputeBuffer m_ProjectedBuffer`  
- `private UnityEngine.ComputeBuffer m_AbsoluteBuffer`  
- `private System.Collections.Generic.List<System.UInt32> m_ArgsArray`  
- `private System.Int32 m_ProjectedInstanceCount`  
- `private System.Int32 m_AbsoluteInstanceCount`  
- `private System.Int32 m_CurveBufferID`  
- `private System.Int32 m_GradientScaleID`  
- `private System.Int32 m_ScaleRatioAID`  
- `private System.Int32 m_FaceDilateID`  
- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedData`  
- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteData`  
- `private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_BoundsData`  
- `private Unity.Jobs.JobHandle m_BufferWriters`  
- `private TMPro.TextMeshPro m_TextMesh`  

## Constructors

- `public OverlayRenderSystem()`  

## Methods

- `public AddBufferWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public CopyFontAtlasParameters(UnityEngine.Material source, UnityEngine.Material target) : System.Void`  
- `private CreateFont(Game.Prefabs.FontInfo info) : TMPro.TMP_FontAsset`  
- `public GetBuffer(Unity.Jobs.JobHandle& dependencies) : Game.Rendering.OverlayRenderSystem+Buffer`  
- `private GetCurveBuffer(UnityEngine.ComputeBuffer& buffer, System.Int32 count) : System.Void`  
- `private GetCurveMaterial(UnityEngine.Material& material, System.Boolean projected) : System.Void`  
- `private GetMesh(UnityEngine.Mesh& mesh, System.Boolean box) : System.Void`  
- `public GetTextMesh() : TMPro.TextMeshPro`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

## Nested types

- `Game.Rendering.OverlayRenderSystem+CurveData`  
- `Game.Rendering.OverlayRenderSystem+BoundsData`  
- `Game.Rendering.OverlayRenderSystem+StyleFlags`  
- `Game.Rendering.OverlayRenderSystem+Buffer`  

