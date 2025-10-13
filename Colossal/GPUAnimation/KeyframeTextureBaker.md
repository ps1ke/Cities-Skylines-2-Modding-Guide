# Colossal.GPUAnimation.KeyframeTextureBaker

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.GPUAnimation`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class KeyframeTextureBaker
{
    public static Colossal.GPUAnimation.KeyframeTextureBaker+BakedData BakeClips(UnityEngine.GameObject animationRoot, UnityEngine.AnimationClip[] animationClips, System.Single framerate);
    public static System.Void CopyMeshData(UnityEngine.Mesh originalMesh, UnityEngine.Mesh newMesh, UnityEngine.Vector4[] boneIds, UnityEngine.Vector4[] boneInfluences);
    public static UnityEngine.Mesh CreateMesh(UnityEngine.SkinnedMeshRenderer originalRenderer, UnityEngine.Mesh mesh);
    private static UnityEngine.Texture2D CreateTexture(System.Int32 numberOfKeyFrames, System.Int32 numberOfBones);
    private static UnityEngine.Texture2DArray CreateTextureArray(System.Int32 numberOfKeyFrames, System.Int32 numberOfBones);
    private static System.Single Distance(UnityEngine.Color r1, UnityEngine.Color r2);
    public static System.String Format(UnityEngine.Vector4 v);
    public static System.String Format(UnityEngine.Color v);
    private static System.Int32 Get1DCoord(System.Int32 x, System.Int32 y, System.Int32 width);
    private static UnityEngine.Color GetRotation(UnityEngine.Quaternion rotation);
    private static UnityEngine.Color GetTranslation(UnityEngine.Vector4 rawTranslation, UnityEngine.Color rotation);
    private static UnityEngine.Color Negate(UnityEngine.Color c);
    private static UnityEngine.Matrix4x4[] SampleAnimationClip(UnityEngine.GameObject root, UnityEngine.AnimationClip clip, UnityEngine.SkinnedMeshRenderer renderer, System.Single framerate);
}
```


## Methods

- `public static BakeClips(UnityEngine.GameObject animationRoot, UnityEngine.AnimationClip[] animationClips, System.Single framerate) : Colossal.GPUAnimation.KeyframeTextureBaker+BakedData`  

```csharp
public static Colossal.GPUAnimation.KeyframeTextureBaker+BakedData BakeClips(UnityEngine.GameObject animationRoot, UnityEngine.AnimationClip[] animationClips, System.Single framerate);
```

- `public static CopyMeshData(UnityEngine.Mesh originalMesh, UnityEngine.Mesh newMesh, UnityEngine.Vector4[] boneIds, UnityEngine.Vector4[] boneInfluences) : System.Void`  

```csharp
public static System.Void CopyMeshData(UnityEngine.Mesh originalMesh, UnityEngine.Mesh newMesh, UnityEngine.Vector4[] boneIds, UnityEngine.Vector4[] boneInfluences);
```

- `public static CreateMesh(UnityEngine.SkinnedMeshRenderer originalRenderer, UnityEngine.Mesh mesh = null) : UnityEngine.Mesh`  

```csharp
public static UnityEngine.Mesh CreateMesh(UnityEngine.SkinnedMeshRenderer originalRenderer, UnityEngine.Mesh mesh);
```

- `private static CreateTexture(System.Int32 numberOfKeyFrames, System.Int32 numberOfBones) : UnityEngine.Texture2D`  

```csharp
private static UnityEngine.Texture2D CreateTexture(System.Int32 numberOfKeyFrames, System.Int32 numberOfBones);
```

- `private static CreateTextureArray(System.Int32 numberOfKeyFrames, System.Int32 numberOfBones) : UnityEngine.Texture2DArray`  

```csharp
private static UnityEngine.Texture2DArray CreateTextureArray(System.Int32 numberOfKeyFrames, System.Int32 numberOfBones);
```

- `private static Distance(UnityEngine.Color r1, UnityEngine.Color r2) : System.Single`  

```csharp
private static System.Single Distance(UnityEngine.Color r1, UnityEngine.Color r2);
```

- `public static Format(UnityEngine.Vector4 v) : System.String`  

```csharp
public static System.String Format(UnityEngine.Vector4 v);
```

- `public static Format(UnityEngine.Color v) : System.String`  

```csharp
public static System.String Format(UnityEngine.Color v);
```

- `private static Get1DCoord(System.Int32 x, System.Int32 y, System.Int32 width) : System.Int32`  

```csharp
private static System.Int32 Get1DCoord(System.Int32 x, System.Int32 y, System.Int32 width);
```

- `private static GetRotation(UnityEngine.Quaternion rotation) : UnityEngine.Color`  

```csharp
private static UnityEngine.Color GetRotation(UnityEngine.Quaternion rotation);
```

- `private static GetTranslation(UnityEngine.Vector4 rawTranslation, UnityEngine.Color rotation) : UnityEngine.Color`  

```csharp
private static UnityEngine.Color GetTranslation(UnityEngine.Vector4 rawTranslation, UnityEngine.Color rotation);
```

- `private static Negate(UnityEngine.Color c) : UnityEngine.Color`  

```csharp
private static UnityEngine.Color Negate(UnityEngine.Color c);
```

- `private static SampleAnimationClip(UnityEngine.GameObject root, UnityEngine.AnimationClip clip, UnityEngine.SkinnedMeshRenderer renderer, System.Single framerate) : UnityEngine.Matrix4x4[]`  

```csharp
private static UnityEngine.Matrix4x4[] SampleAnimationClip(UnityEngine.GameObject root, UnityEngine.AnimationClip clip, UnityEngine.SkinnedMeshRenderer renderer, System.Single framerate);
```


## Nested types

- `Colossal.GPUAnimation.KeyframeTextureBaker+BakedData`  
- `Colossal.GPUAnimation.KeyframeTextureBaker+AnimationClipData`  
- `Colossal.GPUAnimation.KeyframeTextureBaker+<>c`  
- `Colossal.GPUAnimation.KeyframeTextureBaker+<>c__DisplayClass7_0`  

