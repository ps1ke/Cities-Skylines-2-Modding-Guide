# Game.Rendering.Debug.RenderPrefabRenderer+Instance

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Debug`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Instance
{
    private Colossal.Rendering.VTTextureRequester m_VTTexturesRequester;
    private System.Collections.Generic.List<System.Int32> m_VTTexturesIndices;
    private UnityEngine.GameObject m_Root;
    private System.Collections.Generic.List<UnityEngine.MeshRenderer> m_MeshRenderers;
    private Colossal.Mathematics.Bounds3 m_Bounds;
    private Game.Rendering.Debug.RenderPrefabRenderer m_Owner;
    private Game.Prefabs.ColorProperties m_ColorProperties;
    private Game.Prefabs.EmissiveProperties m_EmissiveProperties;
    private Game.Prefabs.ProceduralAnimationProperties m_ProceduralAnimationProperties;
    private Game.Prefabs.CharacterProperties m_CharacterProperties;
    private Game.Rendering.Debug.CharacterGroupRenderer m_CharacterGroupRenderer;
    private Game.Prefabs.DecalProperties m_DecalProperties;
    private UnityEngine.ComputeBuffer m_LightBuffer;
    private UnityEngine.ComputeBuffer m_AnimationBuffer;
    private Game.Prefabs.RenderPrefab m_Prefab;
    private System.Collections.Generic.Dictionary<System.String, UnityEngine.Transform> m_BoneMap;
    private UnityEngine.Matrix4x4[] m_SkinMatrices;

    public System.String name { get; }
    public UnityEngine.GameObject root { get; }
    public System.Boolean enabled { get; set; }

    public Instance(Game.Rendering.Debug.RenderPrefabRenderer mpr, Game.Prefabs.RenderPrefab basePrefab, Game.Prefabs.RenderPrefab prefab, System.Boolean useVT);

    public System.Void Dispose();
    private Unity.Mathematics.float4x4 GetBone(System.String name, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] bones, UnityEngine.Transform root);
    private System.Single GetMaxPixelSize();
    private System.Single GetPixelSize(UnityEngine.Camera camera, System.Single radius);
    public System.String GetStats();
    public System.Void SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block);
    public System.Void SetColorProperties(System.Int32 index, UnityEngine.MaterialPropertyBlock& block);
    public System.Void SetDecalProperties(UnityEngine.MaterialPropertyBlock& block);
    public System.Void SetEmissiveProperties(System.Int32 lightIndex, UnityEngine.MaterialPropertyBlock& block);
    private System.Void SetKeyword(UnityEngine.Material[] materials, System.String keywordName, System.Boolean enabled);
    public System.Void SetProceduralAnimationProperties(UnityEngine.MaterialPropertyBlock& block);
    private System.Void SetShaderPass(UnityEngine.Material[] materials, System.String passName, System.Boolean enabled);
    private System.Void SetupEmissiveProperties(System.Int32 lightIndex);
    private System.Void SetupProceduralAnimationProperties();
    public System.Void SetWindowProperties(System.Single randomWin, UnityEngine.MaterialPropertyBlock& block);
    public System.Void Update();
}
```


## Fields

- `private Colossal.Rendering.VTTextureRequester m_VTTexturesRequester`  

```csharp
private Colossal.Rendering.VTTextureRequester m_VTTexturesRequester;
```

- `private System.Collections.Generic.List<System.Int32> m_VTTexturesIndices`  

```csharp
private System.Collections.Generic.List<System.Int32> m_VTTexturesIndices;
```

- `private UnityEngine.GameObject m_Root`  

```csharp
private UnityEngine.GameObject m_Root;
```

- `private System.Collections.Generic.List<UnityEngine.MeshRenderer> m_MeshRenderers`  

```csharp
private System.Collections.Generic.List<UnityEngine.MeshRenderer> m_MeshRenderers;
```

- `private Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
private Colossal.Mathematics.Bounds3 m_Bounds;
```

- `private Game.Rendering.Debug.RenderPrefabRenderer m_Owner`  

```csharp
private Game.Rendering.Debug.RenderPrefabRenderer m_Owner;
```

- `private Game.Prefabs.ColorProperties m_ColorProperties`  

```csharp
private Game.Prefabs.ColorProperties m_ColorProperties;
```

- `private Game.Prefabs.EmissiveProperties m_EmissiveProperties`  

```csharp
private Game.Prefabs.EmissiveProperties m_EmissiveProperties;
```

- `private Game.Prefabs.ProceduralAnimationProperties m_ProceduralAnimationProperties`  

```csharp
private Game.Prefabs.ProceduralAnimationProperties m_ProceduralAnimationProperties;
```

- `private Game.Prefabs.CharacterProperties m_CharacterProperties`  

```csharp
private Game.Prefabs.CharacterProperties m_CharacterProperties;
```

- `private Game.Rendering.Debug.CharacterGroupRenderer m_CharacterGroupRenderer`  

```csharp
private Game.Rendering.Debug.CharacterGroupRenderer m_CharacterGroupRenderer;
```

- `private Game.Prefabs.DecalProperties m_DecalProperties`  

```csharp
private Game.Prefabs.DecalProperties m_DecalProperties;
```

- `private UnityEngine.ComputeBuffer m_LightBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_LightBuffer;
```

- `private UnityEngine.ComputeBuffer m_AnimationBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_AnimationBuffer;
```

- `private Game.Prefabs.RenderPrefab m_Prefab`  

```csharp
private Game.Prefabs.RenderPrefab m_Prefab;
```

- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Transform> m_BoneMap`  

```csharp
private System.Collections.Generic.Dictionary<System.String, UnityEngine.Transform> m_BoneMap;
```

- `private UnityEngine.Matrix4x4[] m_SkinMatrices`  

```csharp
private UnityEngine.Matrix4x4[] m_SkinMatrices;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public UnityEngine.GameObject root { get }`  

```csharp
public UnityEngine.GameObject root { get; }
```

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```


## Constructors

- `public Instance(Game.Rendering.Debug.RenderPrefabRenderer mpr, Game.Prefabs.RenderPrefab basePrefab, Game.Prefabs.RenderPrefab prefab, System.Boolean useVT = True)`  

```csharp
public Instance(Game.Rendering.Debug.RenderPrefabRenderer mpr, Game.Prefabs.RenderPrefab basePrefab, Game.Prefabs.RenderPrefab prefab, System.Boolean useVT);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private GetBone(System.String name, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] bones, UnityEngine.Transform root) : Unity.Mathematics.float4x4`  

```csharp
private Unity.Mathematics.float4x4 GetBone(System.String name, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] bones, UnityEngine.Transform root);
```

- `private GetMaxPixelSize() : System.Single`  

```csharp
private System.Single GetMaxPixelSize();
```

- `private GetPixelSize(UnityEngine.Camera camera, System.Single radius) : System.Single`  

```csharp
private System.Single GetPixelSize(UnityEngine.Camera camera, System.Single radius);
```

- `public GetStats() : System.String`  

```csharp
public System.String GetStats();
```

- `public SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block) : System.Void`  

```csharp
public System.Void SetCharacterProperties(UnityEngine.MaterialPropertyBlock& block);
```

- `public SetColorProperties(System.Int32 index, UnityEngine.MaterialPropertyBlock& block) : System.Void`  

```csharp
public System.Void SetColorProperties(System.Int32 index, UnityEngine.MaterialPropertyBlock& block);
```

- `public SetDecalProperties(UnityEngine.MaterialPropertyBlock& block) : System.Void`  

```csharp
public System.Void SetDecalProperties(UnityEngine.MaterialPropertyBlock& block);
```

- `public SetEmissiveProperties(System.Int32 lightIndex, UnityEngine.MaterialPropertyBlock& block) : System.Void`  

```csharp
public System.Void SetEmissiveProperties(System.Int32 lightIndex, UnityEngine.MaterialPropertyBlock& block);
```

- `private SetKeyword(UnityEngine.Material[] materials, System.String keywordName, System.Boolean enabled) : System.Void`  

```csharp
private System.Void SetKeyword(UnityEngine.Material[] materials, System.String keywordName, System.Boolean enabled);
```

- `public SetProceduralAnimationProperties(UnityEngine.MaterialPropertyBlock& block) : System.Void`  

```csharp
public System.Void SetProceduralAnimationProperties(UnityEngine.MaterialPropertyBlock& block);
```

- `private SetShaderPass(UnityEngine.Material[] materials, System.String passName, System.Boolean enabled) : System.Void`  

```csharp
private System.Void SetShaderPass(UnityEngine.Material[] materials, System.String passName, System.Boolean enabled);
```

- `private SetupEmissiveProperties(System.Int32 lightIndex) : System.Void`  

```csharp
private System.Void SetupEmissiveProperties(System.Int32 lightIndex);
```

- `private SetupProceduralAnimationProperties() : System.Void`  

```csharp
private System.Void SetupProceduralAnimationProperties();
```

- `public SetWindowProperties(System.Single randomWin, UnityEngine.MaterialPropertyBlock& block) : System.Void`  

```csharp
public System.Void SetWindowProperties(System.Single randomWin, UnityEngine.MaterialPropertyBlock& block);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


