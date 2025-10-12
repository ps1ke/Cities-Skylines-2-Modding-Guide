# Game.Rendering.Debug.RenderPrefabRenderer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Debug`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Fields

- `public System.Boolean m_NoVT`  
- `public Game.Prefabs.RenderPrefab m_Prefab`  
- `public System.Single m_WindowsLight`  
- `public System.Int32 m_EmissiveLight`  
- `public System.Int32 m_ColorIndex`  
- `public System.Int32 m_LODIndex`  
- `public System.Boolean m_Animate`  
- `private System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+Instance> m_Hierarchies`  
- `private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock`  
- `private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+AnimationState>> m_AnimationStates`  
- `private static const System.Boolean kRefreshPrefabDataEveryFrame`  

## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Rendering.Debug.RenderPrefabRenderer+Instance> hierarchies { get }`  

## Constructors

- `public RenderPrefabRenderer()`  

## Methods

- `public GetActiveRoot() : UnityEngine.GameObject`  
- `private OnDisable() : System.Void`  
- `private OnDrawGizmosSelected() : System.Void`  
- `private OnEnable() : System.Void`  
- `private RegisterForAnimation(System.String boneName, UnityEngine.Transform target, Game.Prefabs.ProceduralAnimationProperties+BoneInfo boneInfo) : System.Void`  
- `private Update() : System.Void`  
- `private UpdateAnimations() : System.Void`  

## Nested types

- `Game.Rendering.Debug.RenderPrefabRenderer+Instance`  
- `Game.Rendering.Debug.RenderPrefabRenderer+ShaderIDs`  
- `Game.Rendering.Debug.RenderPrefabRenderer+AnimationState`  
- `Game.Rendering.Debug.RenderPrefabRenderer+<>c__DisplayClass19_0`  

