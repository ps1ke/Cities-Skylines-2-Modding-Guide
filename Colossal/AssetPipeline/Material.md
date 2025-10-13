# Colossal.AssetPipeline.Constants+Material

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class Material
{
    public static readonly System.String[] kEmissiveMaps;
    public static readonly System.String[] kEmissiveMapIDs;
    public static const System.String kWindRangeLvlB;
    public static const System.String kWindElasticityLvlB;
    public static const System.String kInteriorAtlas;
    public static const System.String kBaseColor;
    public static const System.String kBaseColorMap;
    public static const System.String kControlMask;
    public static const System.String kMaskMap;
    public static const System.String kNormalDepthMap;
    public static const System.String kNormal;
    public static const System.String kNormalMap;
    public static const System.String kEmissiveColorMap;
    public static const System.String kMainTex;
    public static const System.String kEmissiveMask;
    public static const System.String kEmissive0;
    public static const System.String kEmissive1;
    public static const System.String kEmissive2;
    public static const System.String kEmissive3;
    public static const System.String kEmissiveID0;
    public static const System.String kEmissiveID2;
    public static const System.String kEmissiveID3;
    public static const System.String kEmissiveID1;
    public static const System.String kWorldspaceBaseColor;
    public static const System.String kWorldspaceBaseColorMap;
    public static const System.String kWorldspaceNormal;
    public static const System.String kWorldspaceNormalMap;
    public static const System.String kWorldspaceMaskMap;
    public static const System.String kWorldspaceAlbedo;
    public static const System.String kWindFlutterMap;
    public static const System.String kImpostorFrames;
    public static const System.String kImpostorSize;
    public static const System.String kImpostorOffset;

    public static System.String GetBakingTextureProperty(System.String suffix);
    public static System.String GetShaderProperty(System.String suffix, Colossal.AssetPipeline.Diagnostic.Report+Asset report);
    public static System.Boolean IsBaseColorMap(System.String suffix);
    public static System.Boolean IsMaskMap(System.String suffix);
    public static System.Boolean IsNormalMap(System.String suffix);
}
```


## Fields

- `public static readonly System.String[] kEmissiveMaps`  

```csharp
public static readonly System.String[] kEmissiveMaps;
```

- `public static readonly System.String[] kEmissiveMapIDs`  

```csharp
public static readonly System.String[] kEmissiveMapIDs;
```

- `public static const System.String kWindRangeLvlB`  

```csharp
public static const System.String kWindRangeLvlB;
```

- `public static const System.String kWindElasticityLvlB`  

```csharp
public static const System.String kWindElasticityLvlB;
```

- `public static const System.String kInteriorAtlas`  

```csharp
public static const System.String kInteriorAtlas;
```

- `public static const System.String kBaseColor`  

```csharp
public static const System.String kBaseColor;
```

- `public static const System.String kBaseColorMap`  

```csharp
public static const System.String kBaseColorMap;
```

- `public static const System.String kControlMask`  

```csharp
public static const System.String kControlMask;
```

- `public static const System.String kMaskMap`  

```csharp
public static const System.String kMaskMap;
```

- `public static const System.String kNormalDepthMap`  

```csharp
public static const System.String kNormalDepthMap;
```

- `public static const System.String kNormal`  

```csharp
public static const System.String kNormal;
```

- `public static const System.String kNormalMap`  

```csharp
public static const System.String kNormalMap;
```

- `public static const System.String kEmissiveColorMap`  

```csharp
public static const System.String kEmissiveColorMap;
```

- `public static const System.String kMainTex`  

```csharp
public static const System.String kMainTex;
```

- `public static const System.String kEmissiveMask`  

```csharp
public static const System.String kEmissiveMask;
```

- `public static const System.String kEmissive0`  

```csharp
public static const System.String kEmissive0;
```

- `public static const System.String kEmissive1`  

```csharp
public static const System.String kEmissive1;
```

- `public static const System.String kEmissive2`  

```csharp
public static const System.String kEmissive2;
```

- `public static const System.String kEmissive3`  

```csharp
public static const System.String kEmissive3;
```

- `public static const System.String kEmissiveID0`  

```csharp
public static const System.String kEmissiveID0;
```

- `public static const System.String kEmissiveID2`  

```csharp
public static const System.String kEmissiveID2;
```

- `public static const System.String kEmissiveID3`  

```csharp
public static const System.String kEmissiveID3;
```

- `public static const System.String kEmissiveID1`  

```csharp
public static const System.String kEmissiveID1;
```

- `public static const System.String kWorldspaceBaseColor`  

```csharp
public static const System.String kWorldspaceBaseColor;
```

- `public static const System.String kWorldspaceBaseColorMap`  

```csharp
public static const System.String kWorldspaceBaseColorMap;
```

- `public static const System.String kWorldspaceNormal`  

```csharp
public static const System.String kWorldspaceNormal;
```

- `public static const System.String kWorldspaceNormalMap`  

```csharp
public static const System.String kWorldspaceNormalMap;
```

- `public static const System.String kWorldspaceMaskMap`  

```csharp
public static const System.String kWorldspaceMaskMap;
```

- `public static const System.String kWorldspaceAlbedo`  

```csharp
public static const System.String kWorldspaceAlbedo;
```

- `public static const System.String kWindFlutterMap`  

```csharp
public static const System.String kWindFlutterMap;
```

- `public static const System.String kImpostorFrames`  

```csharp
public static const System.String kImpostorFrames;
```

- `public static const System.String kImpostorSize`  

```csharp
public static const System.String kImpostorSize;
```

- `public static const System.String kImpostorOffset`  

```csharp
public static const System.String kImpostorOffset;
```


## Methods

- `public static GetBakingTextureProperty(System.String suffix) : System.String`  

```csharp
public static System.String GetBakingTextureProperty(System.String suffix);
```

- `public static GetShaderProperty(System.String suffix, Colossal.AssetPipeline.Diagnostic.Report+Asset report) : System.String`  

```csharp
public static System.String GetShaderProperty(System.String suffix, Colossal.AssetPipeline.Diagnostic.Report+Asset report);
```

- `public static IsBaseColorMap(System.String suffix) : System.Boolean`  

```csharp
public static System.Boolean IsBaseColorMap(System.String suffix);
```

- `public static IsMaskMap(System.String suffix) : System.Boolean`  

```csharp
public static System.Boolean IsMaskMap(System.String suffix);
```

- `public static IsNormalMap(System.String suffix) : System.Boolean`  

```csharp
public static System.Boolean IsNormalMap(System.String suffix);
```


## Nested types

- `Colossal.AssetPipeline.Constants+Material+Shader`  
- `Colossal.AssetPipeline.Constants+Material+Keyword`  

