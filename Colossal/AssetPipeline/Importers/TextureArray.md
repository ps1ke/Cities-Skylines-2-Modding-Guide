# Colossal.AssetPipeline.Importers.TextureImporter+TextureArray

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.Importers.TextureImporter+ITexture`, `System.IDisposable`  

## Code

```csharp
public class TextureArray : Colossal.AssetPipeline.Importers.TextureImporter+ITexture, System.IDisposable
{
    private System.Collections.Generic.List<Colossal.AssetPipeline.Importers.TextureImporter+Texture> m_Textures;
    private UnityEngine.Texture2DArray m_CachedObject;

    public System.String name { get; }
    public System.Int32 width { get; }
    public System.Int32 height { get; }
    public System.Int32 mipsCount { get; }
    public System.Int32 rawMipsCount { get; }
    public System.Int32 compressedMipsCount { get; }
    public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
    public UnityEngine.Experimental.Rendering.GraphicsFormat rawFormat { get; }
    public UnityEngine.Experimental.Rendering.GraphicsFormat compressedFormat { get; }
    public UnityEngine.Rendering.TextureDimension dimension { get; }
    public System.Int32 depth { get; }
    public UnityEngine.FilterMode filterMode { get; set; }
    public UnityEngine.TextureWrapMode wrapMode { get; set; }
    public System.Int32 anisoLevel { get; }
    public Colossal.AssetPipeline.IAsset sourceAsset { get; }

    public TextureArray(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.TextureImporter+Texture> textures);
    public TextureArray();

    public System.Boolean AddSlice(Colossal.AssetPipeline.Importers.TextureImporter+Texture texture);
    private System.Boolean CheckTextureSize(Colossal.AssetPipeline.Importers.TextureImporter+Texture texture);
    public System.Void Dispose();
    public Unity.Collections.NativeArray<System.Byte> GetCompressedMipData(System.Int32 slice, System.Int32 mip);
    public Unity.Collections.NativeArray<System.Byte> GetMipData(System.Int32 slice, System.Int32 mip);
    public Unity.Collections.NativeArray<System.Byte> GetRawMipData(System.Int32 slice, System.Int32 mip);
    public UnityEngine.Texture ToUnityTexture(System.Boolean hideAndDontSave);
    public UnityEngine.Texture ToUnityTextureRaw(System.Boolean hideAndDontSave);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.AssetPipeline.Importers.TextureImporter+Texture> m_Textures`  

```csharp
private System.Collections.Generic.List<Colossal.AssetPipeline.Importers.TextureImporter+Texture> m_Textures;
```

- `private UnityEngine.Texture2DArray m_CachedObject`  

```csharp
private UnityEngine.Texture2DArray m_CachedObject;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Int32 width { get }`  

```csharp
public System.Int32 width { get; }
```

- `public System.Int32 height { get }`  

```csharp
public System.Int32 height { get; }
```

- `public System.Int32 mipsCount { get }`  

```csharp
public System.Int32 mipsCount { get; }
```

- `public System.Int32 rawMipsCount { get }`  

```csharp
public System.Int32 rawMipsCount { get; }
```

- `public System.Int32 compressedMipsCount { get }`  

```csharp
public System.Int32 compressedMipsCount { get; }
```

- `public UnityEngine.Experimental.Rendering.GraphicsFormat format { get }`  

```csharp
public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
```

- `public UnityEngine.Experimental.Rendering.GraphicsFormat rawFormat { get }`  

```csharp
public UnityEngine.Experimental.Rendering.GraphicsFormat rawFormat { get; }
```

- `public UnityEngine.Experimental.Rendering.GraphicsFormat compressedFormat { get }`  

```csharp
public UnityEngine.Experimental.Rendering.GraphicsFormat compressedFormat { get; }
```

- `public UnityEngine.Rendering.TextureDimension dimension { get }`  

```csharp
public UnityEngine.Rendering.TextureDimension dimension { get; }
```

- `public System.Int32 depth { get }`  

```csharp
public System.Int32 depth { get; }
```

- `public UnityEngine.FilterMode filterMode { get; set }`  

```csharp
public UnityEngine.FilterMode filterMode { get; set; }
```

- `public UnityEngine.TextureWrapMode wrapMode { get; set }`  

```csharp
public UnityEngine.TextureWrapMode wrapMode { get; set; }
```

- `public System.Int32 anisoLevel { get }`  

```csharp
public System.Int32 anisoLevel { get; }
```

- `public Colossal.AssetPipeline.IAsset sourceAsset { get }`  

```csharp
public Colossal.AssetPipeline.IAsset sourceAsset { get; }
```


## Constructors

- `public TextureArray(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.TextureImporter+Texture> textures)`  

```csharp
public TextureArray(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.TextureImporter+Texture> textures);
```

- `public TextureArray()`  

```csharp
public TextureArray();
```


## Methods

- `public AddSlice(Colossal.AssetPipeline.Importers.TextureImporter+Texture texture) : System.Boolean`  

```csharp
public System.Boolean AddSlice(Colossal.AssetPipeline.Importers.TextureImporter+Texture texture);
```

- `private CheckTextureSize(Colossal.AssetPipeline.Importers.TextureImporter+Texture texture) : System.Boolean`  

```csharp
private System.Boolean CheckTextureSize(Colossal.AssetPipeline.Importers.TextureImporter+Texture texture);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetCompressedMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetCompressedMipData(System.Int32 slice, System.Int32 mip);
```

- `public GetMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetMipData(System.Int32 slice, System.Int32 mip);
```

- `public GetRawMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetRawMipData(System.Int32 slice, System.Int32 mip);
```

- `public ToUnityTexture(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture ToUnityTexture(System.Boolean hideAndDontSave);
```

- `public ToUnityTextureRaw(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture ToUnityTextureRaw(System.Boolean hideAndDontSave);
```


