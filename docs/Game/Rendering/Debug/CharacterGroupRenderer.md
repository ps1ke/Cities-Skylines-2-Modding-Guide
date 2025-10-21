# Game.Rendering.Debug.CharacterGroupRenderer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Debug`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class CharacterGroupRenderer : UnityEngine.MonoBehaviour
{
    public Game.Prefabs.CharacterGroup m_Prefab;
    public System.Boolean m_NoVT;
    public System.Int32 m_CharacterIndex;
    public System.Int32 m_OverlayColorIndex;
    private UnityEngine.GameObject m_Root;
    private UnityEngine.ComputeBuffer m_BoneBuffer;
    private UnityEngine.ComputeBuffer m_BoneHistoryBuffer;
    private UnityEngine.ComputeBuffer m_MetaBuffer;

    public CharacterGroupRenderer();

    private System.Void CreateRenderer();
    private UnityEngine.Color GetBlendColor(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeight weight);
    private Game.Rendering.BlendColors GetBlendColors(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeights weights);
    private System.Void OnDisable();
    private System.Void OnEnable();
    public System.Void Recreate();
    private System.Void ReleaseRenderer();
    public System.Void SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block);
    private System.Void SetupBuffers(Game.Prefabs.CharacterGroup+Character character);
}
```


## Fields

- `public Game.Prefabs.CharacterGroup m_Prefab`  

```csharp
public Game.Prefabs.CharacterGroup m_Prefab;
```

- `public System.Boolean m_NoVT`  

```csharp
public System.Boolean m_NoVT;
```

- `public System.Int32 m_CharacterIndex`  

```csharp
public System.Int32 m_CharacterIndex;
```

- `public System.Int32 m_OverlayColorIndex`  

```csharp
public System.Int32 m_OverlayColorIndex;
```

- `private UnityEngine.GameObject m_Root`  

```csharp
private UnityEngine.GameObject m_Root;
```

- `private UnityEngine.ComputeBuffer m_BoneBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_BoneBuffer;
```

- `private UnityEngine.ComputeBuffer m_BoneHistoryBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_BoneHistoryBuffer;
```

- `private UnityEngine.ComputeBuffer m_MetaBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_MetaBuffer;
```


## Constructors

- `public CharacterGroupRenderer()`  

```csharp
public CharacterGroupRenderer();
```


## Methods

- `private CreateRenderer() : System.Void`  

```csharp
private System.Void CreateRenderer();
```

- `private GetBlendColor(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeight weight) : UnityEngine.Color`  

```csharp
private UnityEngine.Color GetBlendColor(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeight weight);
```

- `private GetBlendColors(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeights weights) : Game.Rendering.BlendColors`  

```csharp
private Game.Rendering.BlendColors GetBlendColors(Game.Prefabs.RenderPrefab[] renderPrefabs, Game.Rendering.BlendWeights weights);
```

- `private OnDisable() : System.Void`  

```csharp
private System.Void OnDisable();
```

- `private OnEnable() : System.Void`  

```csharp
private System.Void OnEnable();
```

- `public Recreate() : System.Void`  

```csharp
public System.Void Recreate();
```

- `private ReleaseRenderer() : System.Void`  

```csharp
private System.Void ReleaseRenderer();
```

- `public SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block) : System.Void`  

```csharp
public System.Void SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block);
```

- `private SetupBuffers(Game.Prefabs.CharacterGroup+Character character) : System.Void`  

```csharp
private System.Void SetupBuffers(Game.Prefabs.CharacterGroup+Character character);
```


