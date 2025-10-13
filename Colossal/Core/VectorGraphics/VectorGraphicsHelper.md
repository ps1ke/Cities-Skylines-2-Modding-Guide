# Colossal.Core.VectorGraphics.VectorGraphicsHelper

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Core.VectorGraphics`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class VectorGraphicsHelper
{
    private static System.Void ComputeTessellationOptions(Unity.VectorGraphics.SVGParser+SceneInfo sceneInfo, System.Single svgPixelsPerUnit, System.Int32 targetResolution, System.Single multiplier, System.Single& stepDist, System.Single& maxCord, System.Single& maxTangent);
    private static UnityEngine.Material GetMaterialForSVGSprite(System.Boolean hasTexture);
    public static UnityEngine.Texture2D LoadTextureFromSVG(System.String path, System.Int32 width, System.Int32 height);
}
```


## Methods

- `private static ComputeTessellationOptions(Unity.VectorGraphics.SVGParser+SceneInfo sceneInfo, System.Single svgPixelsPerUnit, System.Int32 targetResolution, System.Single multiplier, System.Single& stepDist, System.Single& maxCord, System.Single& maxTangent) : System.Void`  

```csharp
private static System.Void ComputeTessellationOptions(Unity.VectorGraphics.SVGParser+SceneInfo sceneInfo, System.Single svgPixelsPerUnit, System.Int32 targetResolution, System.Single multiplier, System.Single& stepDist, System.Single& maxCord, System.Single& maxTangent);
```

- `private static GetMaterialForSVGSprite(System.Boolean hasTexture) : UnityEngine.Material`  

```csharp
private static UnityEngine.Material GetMaterialForSVGSprite(System.Boolean hasTexture);
```

- `public static LoadTextureFromSVG(System.String path, System.Int32 width, System.Int32 height) : UnityEngine.Texture2D`  

```csharp
public static UnityEngine.Texture2D LoadTextureFromSVG(System.String path, System.Int32 width, System.Int32 height);
```


