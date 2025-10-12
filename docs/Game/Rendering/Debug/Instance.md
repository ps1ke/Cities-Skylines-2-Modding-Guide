# Game.Rendering.Debug.RenderPrefabRenderer+Instance

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Debug`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Colossal.Rendering.VTTextureRequester m_VTTexturesRequester`  
- `private System.Collections.Generic.List<System.Int32> m_VTTexturesIndices`  
- `private UnityEngine.GameObject m_Root`  
- `private System.Collections.Generic.List<UnityEngine.MeshRenderer> m_MeshRenderers`  
- `private Colossal.Mathematics.Bounds3 m_Bounds`  
- `private Game.Rendering.Debug.RenderPrefabRenderer m_Owner`  
- `private Game.Prefabs.ColorProperties m_ColorProperties`  
- `private Game.Prefabs.EmissiveProperties m_EmissiveProperties`  
- `private Game.Prefabs.ProceduralAnimationProperties m_ProceduralAnimationProperties`  
- `private Game.Prefabs.CharacterProperties m_CharacterProperties`  
- `private Game.Rendering.Debug.CharacterGroupRenderer m_CharacterGroupRenderer`  
- `private Game.Prefabs.DecalProperties m_DecalProperties`  
- `private UnityEngine.ComputeBuffer m_LightBuffer`  
- `private UnityEngine.ComputeBuffer m_AnimationBuffer`  
- `private Game.Prefabs.RenderPrefab m_Prefab`  
- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Transform> m_BoneMap`  
- `private UnityEngine.Matrix4x4[] m_SkinMatrices`  

## Properties

- `public System.String name { get }`  
- `public UnityEngine.GameObject root { get }`  
- `public System.Boolean enabled { get; set }`  

## Constructors

- `public Instance(Game.Rendering.Debug.RenderPrefabRenderer mpr, Game.Prefabs.RenderPrefab basePrefab, Game.Prefabs.RenderPrefab prefab, System.Boolean useVT = True)`  

## Methods

- `public Dispose() : System.Void`  
- `private GetBone(System.String name, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] bones, UnityEngine.Transform root) : Unity.Mathematics.float4x4`  
- `private GetMaxPixelSize() : System.Single`  
- `private GetPixelSize(UnityEngine.Camera camera, System.Single radius) : System.Single`  
- `public GetStats() : System.String`  
- `public SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block) : System.Void`  
- `public SetColorProperties(System.Int32 index, UnityEngine.MaterialPropertyBlock& block) : System.Void`  
- `public SetDecalProperties(UnityEngine.MaterialPropertyBlock& block) : System.Void`  
- `public SetEmissiveProperties(System.Int32 lightIndex, UnityEngine.MaterialPropertyBlock& block) : System.Void`  
- `private SetKeyword(UnityEngine.Material[] materials, System.String keywordName, System.Boolean enabled) : System.Void`  
- `public SetProceduralAnimationProperties(UnityEngine.MaterialPropertyBlock& block) : System.Void`  
- `private SetShaderPass(UnityEngine.Material[] materials, System.String passName, System.Boolean enabled) : System.Void`  
- `private SetupEmissiveProperties(System.Int32 lightIndex) : System.Void`  
- `private SetupProceduralAnimationProperties() : System.Void`  
- `public SetWindowProperties(System.Single randomWin, UnityEngine.MaterialPropertyBlock& block) : System.Void`  
- `public Update() : System.Void`  

