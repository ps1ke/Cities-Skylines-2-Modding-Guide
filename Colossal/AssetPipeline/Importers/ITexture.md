# Colossal.AssetPipeline.Importers.TextureImporter+ITexture

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface ITexture : System.IDisposable
{
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

    public abstract Unity.Collections.NativeArray<System.Byte> GetCompressedMipData(System.Int32 slice, System.Int32 mip);
    public abstract Unity.Collections.NativeArray<System.Byte> GetMipData(System.Int32 slice, System.Int32 mip);
    public abstract Unity.Collections.NativeArray<System.Byte> GetRawMipData(System.Int32 slice, System.Int32 mip);
    public abstract UnityEngine.Texture ToUnityTexture(System.Boolean hideAndDontSave);
    public abstract UnityEngine.Texture ToUnityTextureRaw(System.Boolean hideAndDontSave);
}
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


## Methods

- `public abstract GetCompressedMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public abstract Unity.Collections.NativeArray<System.Byte> GetCompressedMipData(System.Int32 slice, System.Int32 mip);
```

- `public abstract GetMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public abstract Unity.Collections.NativeArray<System.Byte> GetMipData(System.Int32 slice, System.Int32 mip);
```

- `public abstract GetRawMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public abstract Unity.Collections.NativeArray<System.Byte> GetRawMipData(System.Int32 slice, System.Int32 mip);
```

- `public abstract ToUnityTexture(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  

```csharp
public abstract UnityEngine.Texture ToUnityTexture(System.Boolean hideAndDontSave);
```

- `public abstract ToUnityTextureRaw(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  

```csharp
public abstract UnityEngine.Texture ToUnityTextureRaw(System.Boolean hideAndDontSave);
```


