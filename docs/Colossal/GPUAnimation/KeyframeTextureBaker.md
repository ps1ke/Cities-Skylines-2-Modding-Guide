# Colossal.GPUAnimation.KeyframeTextureBaker

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.GPUAnimation`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Methods

- `public static BakeClips(UnityEngine.GameObject animationRoot, UnityEngine.AnimationClip[] animationClips, System.Single framerate) : Colossal.GPUAnimation.KeyframeTextureBaker+BakedData`  
- `public static CopyMeshData(UnityEngine.Mesh originalMesh, UnityEngine.Mesh newMesh, UnityEngine.Vector4[] boneIds, UnityEngine.Vector4[] boneInfluences) : System.Void`  
- `public static CreateMesh(UnityEngine.SkinnedMeshRenderer originalRenderer, UnityEngine.Mesh mesh = null) : UnityEngine.Mesh`  
- `private static CreateTexture(System.Int32 numberOfKeyFrames, System.Int32 numberOfBones) : UnityEngine.Texture2D`  
- `private static CreateTextureArray(System.Int32 numberOfKeyFrames, System.Int32 numberOfBones) : UnityEngine.Texture2DArray`  
- `private static Distance(UnityEngine.Color r1, UnityEngine.Color r2) : System.Single`  
- `public static Format(UnityEngine.Vector4 v) : System.String`  
- `public static Format(UnityEngine.Color v) : System.String`  
- `private static Get1DCoord(System.Int32 x, System.Int32 y, System.Int32 width) : System.Int32`  
- `private static GetRotation(UnityEngine.Quaternion rotation) : UnityEngine.Color`  
- `private static GetTranslation(UnityEngine.Vector4 rawTranslation, UnityEngine.Color rotation) : UnityEngine.Color`  
- `private static Negate(UnityEngine.Color c) : UnityEngine.Color`  
- `private static SampleAnimationClip(UnityEngine.GameObject root, UnityEngine.AnimationClip clip, UnityEngine.SkinnedMeshRenderer renderer, System.Single framerate) : UnityEngine.Matrix4x4[]`  

## Nested types

- `Colossal.GPUAnimation.KeyframeTextureBaker+BakedData`  
- `Colossal.GPUAnimation.KeyframeTextureBaker+AnimationClipData`  
- `Colossal.GPUAnimation.KeyframeTextureBaker+<>c`  
- `Colossal.GPUAnimation.KeyframeTextureBaker+<>c__DisplayClass7_0`  

