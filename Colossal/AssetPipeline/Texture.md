# Colossal.AssetPipeline.Settings+Defaults+Texture

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class Texture
{
    public static const System.String kDefault;
    public static const System.String kDefaultRepeat;
    public static const System.String kNormalMap;
    public static const System.String kNormalMapRepeat;
    public static const System.String kLinearMap;
    public static const System.String kLinearMapRepeat;
    public static const System.String kBakingMap;
    public static const System.String kAlphaDetect;

    public static Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+PostProcessSettings GetAlphaDetect();
    public static Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings GetBaking();
    public static Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings GetDefault(UnityEngine.TextureWrapMode wrapMode, UnityEngine.FilterMode filterMode, System.Int32 anisoLevel);
    public static Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings GetLinear(UnityEngine.TextureWrapMode wrapMode, UnityEngine.FilterMode filterMode, System.Int32 anisoLevel);
    public static Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings GetNormal(UnityEngine.TextureWrapMode wrapMode, UnityEngine.FilterMode filterMode, System.Int32 anisoLevel);
}
```


## Fields

- `public static const System.String kDefault`  

```csharp
public static const System.String kDefault;
```

- `public static const System.String kDefaultRepeat`  

```csharp
public static const System.String kDefaultRepeat;
```

- `public static const System.String kNormalMap`  

```csharp
public static const System.String kNormalMap;
```

- `public static const System.String kNormalMapRepeat`  

```csharp
public static const System.String kNormalMapRepeat;
```

- `public static const System.String kLinearMap`  

```csharp
public static const System.String kLinearMap;
```

- `public static const System.String kLinearMapRepeat`  

```csharp
public static const System.String kLinearMapRepeat;
```

- `public static const System.String kBakingMap`  

```csharp
public static const System.String kBakingMap;
```

- `public static const System.String kAlphaDetect`  

```csharp
public static const System.String kAlphaDetect;
```


## Methods

- `public static GetAlphaDetect() : Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+PostProcessSettings`  

```csharp
public static Colossal.AssetPipeline.PostProcessors.AlphaDetectPostProcessor+PostProcessSettings GetAlphaDetect();
```

- `public static GetBaking() : Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings`  

```csharp
public static Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings GetBaking();
```

- `public static GetDefault(UnityEngine.TextureWrapMode wrapMode = Clamp, UnityEngine.FilterMode filterMode = Trilinear, System.Int32 anisoLevel = 16) : Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings`  

```csharp
public static Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings GetDefault(UnityEngine.TextureWrapMode wrapMode, UnityEngine.FilterMode filterMode, System.Int32 anisoLevel);
```

- `public static GetLinear(UnityEngine.TextureWrapMode wrapMode = Clamp, UnityEngine.FilterMode filterMode = Trilinear, System.Int32 anisoLevel = 16) : Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings`  

```csharp
public static Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings GetLinear(UnityEngine.TextureWrapMode wrapMode, UnityEngine.FilterMode filterMode, System.Int32 anisoLevel);
```

- `public static GetNormal(UnityEngine.TextureWrapMode wrapMode = Clamp, UnityEngine.FilterMode filterMode = Trilinear, System.Int32 anisoLevel = 16) : Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings`  

```csharp
public static Colossal.AssetPipeline.Importers.DefaultTextureImporter+ImportSettings GetNormal(UnityEngine.TextureWrapMode wrapMode, UnityEngine.FilterMode filterMode, System.Int32 anisoLevel);
```


