# Game.Rendering.OverlayRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class OverlayRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private UnityEngine.Mesh m_BoxMesh;
    private UnityEngine.Mesh m_QuadMesh;
    private UnityEngine.Material m_ProjectedMaterial;
    private UnityEngine.Material m_AbsoluteMaterial;
    private UnityEngine.ComputeBuffer m_ArgsBuffer;
    private UnityEngine.ComputeBuffer m_ProjectedBuffer;
    private UnityEngine.ComputeBuffer m_AbsoluteBuffer;
    private System.Collections.Generic.List<System.UInt32> m_ArgsArray;
    private System.Int32 m_ProjectedInstanceCount;
    private System.Int32 m_AbsoluteInstanceCount;
    private System.Int32 m_CurveBufferID;
    private System.Int32 m_GradientScaleID;
    private System.Int32 m_ScaleRatioAID;
    private System.Int32 m_FaceDilateID;
    private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedData;
    private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteData;
    private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_BoundsData;
    private Unity.Jobs.JobHandle m_BufferWriters;
    private TMPro.TextMeshPro m_TextMesh;

    public OverlayRenderSystem();

    public System.Void AddBufferWriter(Unity.Jobs.JobHandle handle);
    public System.Void CopyFontAtlasParameters(UnityEngine.Material source, UnityEngine.Material target);
    private TMPro.TMP_FontAsset CreateFont(Game.Prefabs.FontInfo info);
    public Game.Rendering.OverlayRenderSystem+Buffer GetBuffer(Unity.Jobs.JobHandle& dependencies);
    private System.Void GetCurveBuffer(UnityEngine.ComputeBuffer& buffer, System.Int32 count);
    private System.Void GetCurveMaterial(UnityEngine.Material& material, System.Boolean projected);
    private System.Void GetMesh(UnityEngine.Mesh& mesh, System.Boolean box);
    public TMPro.TextMeshPro GetTextMesh();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private UnityEngine.Mesh m_BoxMesh`  

```csharp
private UnityEngine.Mesh m_BoxMesh;
```

- `private UnityEngine.Mesh m_QuadMesh`  

```csharp
private UnityEngine.Mesh m_QuadMesh;
```

- `private UnityEngine.Material m_ProjectedMaterial`  

```csharp
private UnityEngine.Material m_ProjectedMaterial;
```

- `private UnityEngine.Material m_AbsoluteMaterial`  

```csharp
private UnityEngine.Material m_AbsoluteMaterial;
```

- `private UnityEngine.ComputeBuffer m_ArgsBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_ArgsBuffer;
```

- `private UnityEngine.ComputeBuffer m_ProjectedBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_ProjectedBuffer;
```

- `private UnityEngine.ComputeBuffer m_AbsoluteBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_AbsoluteBuffer;
```

- `private System.Collections.Generic.List<System.UInt32> m_ArgsArray`  

```csharp
private System.Collections.Generic.List<System.UInt32> m_ArgsArray;
```

- `private System.Int32 m_ProjectedInstanceCount`  

```csharp
private System.Int32 m_ProjectedInstanceCount;
```

- `private System.Int32 m_AbsoluteInstanceCount`  

```csharp
private System.Int32 m_AbsoluteInstanceCount;
```

- `private System.Int32 m_CurveBufferID`  

```csharp
private System.Int32 m_CurveBufferID;
```

- `private System.Int32 m_GradientScaleID`  

```csharp
private System.Int32 m_GradientScaleID;
```

- `private System.Int32 m_ScaleRatioAID`  

```csharp
private System.Int32 m_ScaleRatioAID;
```

- `private System.Int32 m_FaceDilateID`  

```csharp
private System.Int32 m_FaceDilateID;
```

- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedData;
```

- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteData;
```

- `private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_BoundsData`  

```csharp
private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_BoundsData;
```

- `private Unity.Jobs.JobHandle m_BufferWriters`  

```csharp
private Unity.Jobs.JobHandle m_BufferWriters;
```

- `private TMPro.TextMeshPro m_TextMesh`  

```csharp
private TMPro.TextMeshPro m_TextMesh;
```


## Constructors

- `public OverlayRenderSystem()`  

```csharp
public OverlayRenderSystem();
```


## Methods

- `public AddBufferWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddBufferWriter(Unity.Jobs.JobHandle handle);
```

- `public CopyFontAtlasParameters(UnityEngine.Material source, UnityEngine.Material target) : System.Void`  

```csharp
public System.Void CopyFontAtlasParameters(UnityEngine.Material source, UnityEngine.Material target);
```

- `private CreateFont(Game.Prefabs.FontInfo info) : TMPro.TMP_FontAsset`  

```csharp
private TMPro.TMP_FontAsset CreateFont(Game.Prefabs.FontInfo info);
```

- `public GetBuffer(Unity.Jobs.JobHandle& dependencies) : Game.Rendering.OverlayRenderSystem+Buffer`  

```csharp
public Game.Rendering.OverlayRenderSystem+Buffer GetBuffer(Unity.Jobs.JobHandle& dependencies);
```

- `private GetCurveBuffer(UnityEngine.ComputeBuffer& buffer, System.Int32 count) : System.Void`  

```csharp
private System.Void GetCurveBuffer(UnityEngine.ComputeBuffer& buffer, System.Int32 count);
```

- `private GetCurveMaterial(UnityEngine.Material& material, System.Boolean projected) : System.Void`  

```csharp
private System.Void GetCurveMaterial(UnityEngine.Material& material, System.Boolean projected);
```

- `private GetMesh(UnityEngine.Mesh& mesh, System.Boolean box) : System.Void`  

```csharp
private System.Void GetMesh(UnityEngine.Mesh& mesh, System.Boolean box);
```

- `public GetTextMesh() : TMPro.TextMeshPro`  

```csharp
public TMPro.TextMeshPro GetTextMesh();
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

- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

```csharp
private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
```


## Nested types

- `Game.Rendering.OverlayRenderSystem+CurveData`  
- `Game.Rendering.OverlayRenderSystem+BoundsData`  
- `Game.Rendering.OverlayRenderSystem+StyleFlags`  
- `Game.Rendering.OverlayRenderSystem+Buffer`  

