# Game.ArtPipeline.MeshPrefabRendererOld

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Fields

- `public System.Boolean m_NoVT`  
- `public Game.Prefabs.RenderPrefab m_Prefab`  
- `public System.Int32 m_LOD`  
- `public System.Int32 playClipId`  
- `public System.Single m_TimeScale`  
- `public System.Boolean m_CycleColors`  
- `public System.Boolean m_CycleWindownsLights`  
- `public System.Boolean m_AnimateProceduralBones`  
- `public System.Boolean m_AnimateEmissiveLighting`  
- `private System.Int32 currentlyPlayingId`  
- `private Game.Prefabs.AnimationClip animationClip`  
- `private System.Single m_Time`  
- `private System.Single m_PreviousTime`  
- `private System.Int32 m_WindowSubMesh`  
- `private UnityEngine.MeshFilter m_Filter`  
- `private UnityEngine.MeshRenderer m_Renderer`  
- `private Game.Prefabs.ColorProperties m_ColorProperties`  
- `private Game.Prefabs.AnimationProperties m_AnimationProperties`  
- `private Game.Prefabs.ProceduralAnimationProperties m_ProceduralAnimationProperties`  
- `private Game.Prefabs.DecalProperties m_DecalProperties`  
- `private Game.Prefabs.EmissiveProperties m_EmissiveProperties`  
- `private System.Int32[] m_VTTexturesIndices`  
- `private Colossal.Rendering.VTTextureRequester m_VTTexturesRequester`  
- `private Game.Prefabs.RenderPrefab m_MeshPrefab`  
- `private UnityEngine.Mesh m_Mesh`  
- `private System.Collections.Generic.List<UnityEngine.MeshRenderer> m_LODMeshRenderers`  
- `private UnityEngine.ComputeBuffer m_AnimationBuffer`  
- `private UnityEngine.ComputeBuffer m_LightBuffer`  
- `private System.Int32 m_EmissivePresetIdx`  
- `private System.Single m_EmissiveTime`  
- `private UnityEngine.Matrix4x4[] m_SkinMatrices`  
- `private UnityEngine.Transform m_LookAtTarget`  
- `private Game.ArtPipeline.MeshPrefabRendererOld+MaterialPropertyOverride m_MaterialPropertyOverride`  
- `private UnityEngine.Bounds m_Bounds`  
- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Transform> m_BoneMap`  

## Constructors

- `public MeshPrefabRendererOld()`  

## Methods

- `private GetBone(System.String name, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] bones) : Unity.Mathematics.float4x4`  
- `private GetMaxPixelSize() : System.Single`  
- `private GetPixelSize(UnityEngine.Camera camera, System.Single radius) : System.Single`  
- `private InstantiatePrefabData(System.Boolean noVT) : UnityEngine.MeshRenderer`  
- `private IsNullOrInvalid(UnityEngine.Material[] materials) : System.Boolean`  
- `private OnDestroy() : System.Void`  
- `private OnDisable() : System.Void`  
- `public SetMaterialProperty(System.String property, System.Single value) : System.Void`  
- `public SetMaterialProperty(System.String property, UnityEngine.Vector4 value) : System.Void`  
- `private Start() : System.Void`  
- `private Update() : System.Void`  
- `public Update(System.Boolean noVT) : System.Void`  

## Nested types

- `Game.ArtPipeline.MeshPrefabRendererOld+MaterialPropertyOverride`  

