# Game.Rendering.Debug.RenderPrefabRenderer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Debug`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class RenderPrefabRenderer : UnityEngine.MonoBehaviour
{
    public System.Boolean m_NoVT;
    public Game.Prefabs.RenderPrefab m_Prefab;
    public System.Single m_WindowsLight;
    public System.Int32 m_EmissiveLight;
    public System.Int32 m_ColorIndex;
    public System.Int32 m_LODIndex;
    public System.Boolean m_Animate;
    private System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+Instance> m_Hierarchies;
    private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock;
    private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+AnimationState>> m_AnimationStates;
    private static const System.Boolean kRefreshPrefabDataEveryFrame;

    public System.Collections.Generic.IReadOnlyList<Game.Rendering.Debug.RenderPrefabRenderer+Instance> hierarchies { get; }

    public RenderPrefabRenderer();

    public UnityEngine.GameObject GetActiveRoot();
    private System.Void OnDisable();
    private System.Void OnDrawGizmosSelected();
    private System.Void OnEnable();
    private System.Void RegisterForAnimation(System.String boneName, UnityEngine.Transform target, Game.Prefabs.ProceduralAnimationProperties+BoneInfo boneInfo);
    private System.Void Update();
    private System.Void UpdateAnimations();
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

- `public System.Single m_WindowsLight`  

```csharp
public System.Single m_WindowsLight;
```

- `public System.Int32 m_EmissiveLight`  

```csharp
public System.Int32 m_EmissiveLight;
```

- `public System.Int32 m_ColorIndex`  

```csharp
public System.Int32 m_ColorIndex;
```

- `public System.Int32 m_LODIndex`  

```csharp
public System.Int32 m_LODIndex;
```

- `public System.Boolean m_Animate`  

```csharp
public System.Boolean m_Animate;
```

- `private System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+Instance> m_Hierarchies`  

```csharp
private System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+Instance> m_Hierarchies;
```

- `private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock`  

```csharp
private UnityEngine.MaterialPropertyBlock m_MaterialPropertyBlock;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+AnimationState>> m_AnimationStates`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Game.Rendering.Debug.RenderPrefabRenderer+AnimationState>> m_AnimationStates;
```

- `private static const System.Boolean kRefreshPrefabDataEveryFrame`  

```csharp
private static const System.Boolean kRefreshPrefabDataEveryFrame;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Rendering.Debug.RenderPrefabRenderer+Instance> hierarchies { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Rendering.Debug.RenderPrefabRenderer+Instance> hierarchies { get; }
```


## Constructors

- `public RenderPrefabRenderer()`  

```csharp
public RenderPrefabRenderer();
```


## Methods

- `public GetActiveRoot() : UnityEngine.GameObject`  

```csharp
public UnityEngine.GameObject GetActiveRoot();
```

- `private OnDisable() : System.Void`  

```csharp
private System.Void OnDisable();
```

- `private OnDrawGizmosSelected() : System.Void`  

```csharp
private System.Void OnDrawGizmosSelected();
```

- `private OnEnable() : System.Void`  

```csharp
private System.Void OnEnable();
```

- `private RegisterForAnimation(System.String boneName, UnityEngine.Transform target, Game.Prefabs.ProceduralAnimationProperties+BoneInfo boneInfo) : System.Void`  

```csharp
private System.Void RegisterForAnimation(System.String boneName, UnityEngine.Transform target, Game.Prefabs.ProceduralAnimationProperties+BoneInfo boneInfo);
```

- `private Update() : System.Void`  

```csharp
private System.Void Update();
```

- `private UpdateAnimations() : System.Void`  

```csharp
private System.Void UpdateAnimations();
```


## Nested types

- `Game.Rendering.Debug.RenderPrefabRenderer+Instance`  
- `Game.Rendering.Debug.RenderPrefabRenderer+ShaderIDs`  
- `Game.Rendering.Debug.RenderPrefabRenderer+AnimationState`  
- `Game.Rendering.Debug.RenderPrefabRenderer+<>c__DisplayClass19_0`  

