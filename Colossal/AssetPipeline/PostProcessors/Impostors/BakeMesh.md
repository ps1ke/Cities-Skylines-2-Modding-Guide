# Colossal.AssetPipeline.PostProcessors.Impostors.BakeMesh

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Impostors`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class BakeMesh
{
    public static UnityEngine.Mesh CreateBillboardMesh(UnityEngine.BoundingSphere bounds);
    public static UnityEngine.Mesh CreateTightMesh(Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, UnityEngine.BoundingSphere bounds, System.Single detail, System.UInt32 extrude, System.Action<UnityEngine.Texture> onDebugOutputTexture);
    private static UnityEngine.Texture2D ToTexture2D(System.String name, UnityEngine.RenderTexture target, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Boolean compress);
}
```


## Methods

- `public static CreateBillboardMesh(UnityEngine.BoundingSphere bounds) : UnityEngine.Mesh`  

```csharp
public static UnityEngine.Mesh CreateBillboardMesh(UnityEngine.BoundingSphere bounds);
```

- `public static CreateTightMesh(Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, UnityEngine.BoundingSphere bounds, System.Single detail, System.UInt32 extrude, System.Action<UnityEngine.Texture> onDebugOutputTexture = null) : UnityEngine.Mesh`  

```csharp
public static UnityEngine.Mesh CreateTightMesh(Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, UnityEngine.BoundingSphere bounds, System.Single detail, System.UInt32 extrude, System.Action<UnityEngine.Texture> onDebugOutputTexture);
```

- `private static ToTexture2D(System.String name, UnityEngine.RenderTexture target, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Boolean compress = True) : UnityEngine.Texture2D`  

```csharp
private static UnityEngine.Texture2D ToTexture2D(System.String name, UnityEngine.RenderTexture target, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Boolean compress);
```


