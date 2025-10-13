# Game.ArtPipeline.Impostors.BakeMesh

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Impostors`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class BakeMesh
{
    public static UnityEngine.Mesh CreateBillboardMesh(UnityEngine.BoundingSphere bounds);
    public static UnityEngine.Mesh CreateTightMesh(Game.ArtPipeline.Impostors.BakingScene scene, UnityEngine.BoundingSphere bounds, System.Single detail, System.UInt32 extrude);
    private static UnityEngine.Texture2D ToTexture2D(UnityEngine.RenderTexture target, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Boolean compress);
}
```


## Methods

- `public static CreateBillboardMesh(UnityEngine.BoundingSphere bounds) : UnityEngine.Mesh`  

```csharp
public static UnityEngine.Mesh CreateBillboardMesh(UnityEngine.BoundingSphere bounds);
```

- `public static CreateTightMesh(Game.ArtPipeline.Impostors.BakingScene scene, UnityEngine.BoundingSphere bounds, System.Single detail, System.UInt32 extrude) : UnityEngine.Mesh`  

```csharp
public static UnityEngine.Mesh CreateTightMesh(Game.ArtPipeline.Impostors.BakingScene scene, UnityEngine.BoundingSphere bounds, System.Single detail, System.UInt32 extrude);
```

- `private static ToTexture2D(UnityEngine.RenderTexture target, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Boolean compress = True) : UnityEngine.Texture2D`  

```csharp
private static UnityEngine.Texture2D ToTexture2D(UnityEngine.RenderTexture target, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Boolean compress);
```


