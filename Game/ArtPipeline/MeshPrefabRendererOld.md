# Game.ArtPipeline.MeshPrefabRendererOld

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class MeshPrefabRendererOld : UnityEngine.MonoBehaviour
{
    public System.Boolean m_NoVT;
    public Game.Prefabs.RenderPrefab m_Prefab;
    public System.Int32 m_LOD;
    public System.Int32 playClipId;
    public System.Single m_TimeScale;
    public System.Boolean m_CycleColors;
    public System.Boolean m_CycleWindownsLights;
    public System.Boolean m_AnimateProceduralBones;
    public System.Boolean m_AnimateEmissiveLighting;
    private System.Int32 currentlyPlayingId;
    private Game.Prefabs.AnimationClip animationClip;
    private System.Single m_Time;
    private System.Single m_PreviousTime;
    private System.Int32 m_WindowSubMesh;
    private UnityEngine.MeshFilter m_Filter;
    private UnityEngine.MeshRenderer m_Renderer;
    private Game.Prefabs.ColorProperties m_ColorProperties;
    private Game.Prefabs.AnimationProperties m_AnimationProperties;
    private Game.Prefabs.ProceduralAnimationProperties m_ProceduralAnimationProperties;
    private Game.Prefabs.DecalProperties m_DecalProperties;
    private Game.Prefabs.EmissiveProperties m_EmissiveProperties;
    private System.Int32[] m_VTTexturesIndices;
    private Colossal.Rendering.VTTextureRequester m_VTTexturesRequester;
    private Game.Prefabs.RenderPrefab m_MeshPrefab;
    private UnityEngine.Mesh m_Mesh;
    private System.Collections.Generic.List<UnityEngine.MeshRenderer> m_LODMeshRenderers;
    private UnityEngine.ComputeBuffer m_AnimationBuffer;
    private UnityEngine.ComputeBuffer m_LightBuffer;
    private System.Int32 m_EmissivePresetIdx;
    private System.Single m_EmissiveTime;
    private UnityEngine.Matrix4x4[] m_SkinMatrices;
    private UnityEngine.Transform m_LookAtTarget;
    private Game.ArtPipeline.MeshPrefabRendererOld+MaterialPropertyOverride m_MaterialPropertyOverride;
    private UnityEngine.Bounds m_Bounds;
    private System.Collections.Generic.Dictionary<System.String, UnityEngine.Transform> m_BoneMap;

    public MeshPrefabRendererOld();

    private Unity.Mathematics.float4x4 GetBone(System.String name, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] bones);
    private System.Single GetMaxPixelSize();
    private System.Single GetPixelSize(UnityEngine.Camera camera, System.Single radius);
    private UnityEngine.MeshRenderer InstantiatePrefabData(System.Boolean noVT);
    private System.Boolean IsNullOrInvalid(UnityEngine.Material[] materials);
    private System.Void OnDestroy();
    private System.Void OnDisable();
    public System.Void SetMaterialProperty(System.String property, System.Single value);
    public System.Void SetMaterialProperty(System.String property, UnityEngine.Vector4 value);
    private System.Void Start();
    private System.Void Update();
    public System.Void Update(System.Boolean noVT);
}
```


## Fields

- `public System.Boolean m_NoVT`  

```csharp
public System.Boolean m_NoVT;
```

- `public Game.Prefabs.RenderPrefab m_Prefab`  

```csharp
public Game.Prefabs.RenderPrefab m_Prefab;
```

- `public System.Int32 m_LOD`  

```csharp
public System.Int32 m_LOD;
```

- `public System.Int32 playClipId`  

```csharp
public System.Int32 playClipId;
```

- `public System.Single m_TimeScale`  

```csharp
public System.Single m_TimeScale;
```

- `public System.Boolean m_CycleColors`  

```csharp
public System.Boolean m_CycleColors;
```

- `public System.Boolean m_CycleWindownsLights`  

```csharp
public System.Boolean m_CycleWindownsLights;
```

- `public System.Boolean m_AnimateProceduralBones`  

```csharp
public System.Boolean m_AnimateProceduralBones;
```

- `public System.Boolean m_AnimateEmissiveLighting`  

```csharp
public System.Boolean m_AnimateEmissiveLighting;
```

- `private System.Int32 currentlyPlayingId`  

```csharp
private System.Int32 currentlyPlayingId;
```

- `private Game.Prefabs.AnimationClip animationClip`  

```csharp
private Game.Prefabs.AnimationClip animationClip;
```

- `private System.Single m_Time`  

```csharp
private System.Single m_Time;
```

- `private System.Single m_PreviousTime`  

```csharp
private System.Single m_PreviousTime;
```

- `private System.Int32 m_WindowSubMesh`  

```csharp
private System.Int32 m_WindowSubMesh;
```

- `private UnityEngine.MeshFilter m_Filter`  

```csharp
private UnityEngine.MeshFilter m_Filter;
```

- `private UnityEngine.MeshRenderer m_Renderer`  

```csharp
private UnityEngine.MeshRenderer m_Renderer;
```

- `private Game.Prefabs.ColorProperties m_ColorProperties`  

```csharp
private Game.Prefabs.ColorProperties m_ColorProperties;
```

- `private Game.Prefabs.AnimationProperties m_AnimationProperties`  

```csharp
private Game.Prefabs.AnimationProperties m_AnimationProperties;
```

- `private Game.Prefabs.ProceduralAnimationProperties m_ProceduralAnimationProperties`  

```csharp
private Game.Prefabs.ProceduralAnimationProperties m_ProceduralAnimationProperties;
```

- `private Game.Prefabs.DecalProperties m_DecalProperties`  

```csharp
private Game.Prefabs.DecalProperties m_DecalProperties;
```

- `private Game.Prefabs.EmissiveProperties m_EmissiveProperties`  

```csharp
private Game.Prefabs.EmissiveProperties m_EmissiveProperties;
```

- `private System.Int32[] m_VTTexturesIndices`  

```csharp
private System.Int32[] m_VTTexturesIndices;
```

- `private Colossal.Rendering.VTTextureRequester m_VTTexturesRequester`  

```csharp
private Colossal.Rendering.VTTextureRequester m_VTTexturesRequester;
```

- `private Game.Prefabs.RenderPrefab m_MeshPrefab`  

```csharp
private Game.Prefabs.RenderPrefab m_MeshPrefab;
```

- `private UnityEngine.Mesh m_Mesh`  

```csharp
private UnityEngine.Mesh m_Mesh;
```

- `private System.Collections.Generic.List<UnityEngine.MeshRenderer> m_LODMeshRenderers`  

```csharp
private System.Collections.Generic.List<UnityEngine.MeshRenderer> m_LODMeshRenderers;
```

- `private UnityEngine.ComputeBuffer m_AnimationBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_AnimationBuffer;
```

- `private UnityEngine.ComputeBuffer m_LightBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_LightBuffer;
```

- `private System.Int32 m_EmissivePresetIdx`  

```csharp
private System.Int32 m_EmissivePresetIdx;
```

- `private System.Single m_EmissiveTime`  

```csharp
private System.Single m_EmissiveTime;
```

- `private UnityEngine.Matrix4x4[] m_SkinMatrices`  

```csharp
private UnityEngine.Matrix4x4[] m_SkinMatrices;
```

- `private UnityEngine.Transform m_LookAtTarget`  

```csharp
private UnityEngine.Transform m_LookAtTarget;
```

- `private Game.ArtPipeline.MeshPrefabRendererOld+MaterialPropertyOverride m_MaterialPropertyOverride`  

```csharp
private Game.ArtPipeline.MeshPrefabRendererOld+MaterialPropertyOverride m_MaterialPropertyOverride;
```

- `private UnityEngine.Bounds m_Bounds`  

```csharp
private UnityEngine.Bounds m_Bounds;
```

- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Transform> m_BoneMap`  

```csharp
private System.Collections.Generic.Dictionary<System.String, UnityEngine.Transform> m_BoneMap;
```


## Constructors

- `public MeshPrefabRendererOld()`  

```csharp
public MeshPrefabRendererOld();
```


## Methods

- `private GetBone(System.String name, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] bones) : Unity.Mathematics.float4x4`  

```csharp
private Unity.Mathematics.float4x4 GetBone(System.String name, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] bones);
```

- `private GetMaxPixelSize() : System.Single`  

```csharp
private System.Single GetMaxPixelSize();
```

- `private GetPixelSize(UnityEngine.Camera camera, System.Single radius) : System.Single`  

```csharp
private System.Single GetPixelSize(UnityEngine.Camera camera, System.Single radius);
```

- `private InstantiatePrefabData(System.Boolean noVT) : UnityEngine.MeshRenderer`  

```csharp
private UnityEngine.MeshRenderer InstantiatePrefabData(System.Boolean noVT);
```

- `private IsNullOrInvalid(UnityEngine.Material[] materials) : System.Boolean`  

```csharp
private System.Boolean IsNullOrInvalid(UnityEngine.Material[] materials);
```

- `private OnDestroy() : System.Void`  

```csharp
private System.Void OnDestroy();
```

- `private OnDisable() : System.Void`  

```csharp
private System.Void OnDisable();
```

- `public SetMaterialProperty(System.String property, System.Single value) : System.Void`  

```csharp
public System.Void SetMaterialProperty(System.String property, System.Single value);
```

- `public SetMaterialProperty(System.String property, UnityEngine.Vector4 value) : System.Void`  

```csharp
public System.Void SetMaterialProperty(System.String property, UnityEngine.Vector4 value);
```

- `private Start() : System.Void`  

```csharp
private System.Void Start();
```

- `private Update() : System.Void`  

```csharp
private System.Void Update();
```

- `public Update(System.Boolean noVT) : System.Void`  

```csharp
public System.Void Update(System.Boolean noVT);
```


## Nested types

- `Game.ArtPipeline.MeshPrefabRendererOld+MaterialPropertyOverride`  

