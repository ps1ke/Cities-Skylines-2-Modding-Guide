# Game.Rendering.Debug.CharacterGroupRenderer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Debug`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Fields

- `public Game.Prefabs.CharacterGroup m_Prefab`  
- `public System.Boolean m_NoVT`  
- `public System.Int32 m_CharacterIndex`  
- `public System.Int32 m_OverlayColorIndex`  
- `private UnityEngine.GameObject m_Root`  
- `private UnityEngine.ComputeBuffer m_BoneBuffer`  
- `private UnityEngine.ComputeBuffer m_BoneHistoryBuffer`  
- `private UnityEngine.ComputeBuffer m_MetaBuffer`  

## Constructors

- `public CharacterGroupRenderer()`  

## Methods

- `private CreateRenderer() : System.Void`  
- `private GetBlendColor(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeight weight) : UnityEngine.Color`  
- `private GetBlendColors(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeights weights) : Game.Rendering.BlendColors`  
- `private OnDisable() : System.Void`  
- `private OnEnable() : System.Void`  
- `public Recreate() : System.Void`  
- `private ReleaseRenderer() : System.Void`  
- `public SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block) : System.Void`  
- `private SetupBuffers(Game.Prefabs.CharacterGroup+Character character) : System.Void`  

