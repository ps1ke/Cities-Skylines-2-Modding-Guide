# Colossal.IO.AssetDatabase.TextureUtils

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class TextureUtils
{
    public static System.Int32 ComputeMipchainLevels(System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format);
    public static System.Int32 ComputeMipchainLevels(System.Int32 width, System.Int32 height, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat format);
    public static System.Int32 ComputeMipchainSize(System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevels);
    public static System.Int32 ComputeMipchainSize(System.Int32 width, System.Int32 height, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevels);
    public static System.Int32 ComputeMipmapSize(System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevel);
    public static System.Int32 ComputeMipmapSize(System.Int32 width, System.Int32 height, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevel);
    public static System.Int32 GetMinMipmapExtent(UnityEngine.Experimental.Rendering.GraphicsFormat format);
    public static System.Int32 GetSize(System.Int32 size, System.Int32 mipMapLevel);
}
```


## Methods

- `public static ComputeMipchainLevels(System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format) : System.Int32`  

```csharp
public static System.Int32 ComputeMipchainLevels(System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format);
```

- `public static ComputeMipchainLevels(System.Int32 width, System.Int32 height, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat format) : System.Int32`  

```csharp
public static System.Int32 ComputeMipchainLevels(System.Int32 width, System.Int32 height, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat format);
```

- `public static ComputeMipchainSize(System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevels) : System.Int32`  

```csharp
public static System.Int32 ComputeMipchainSize(System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevels);
```

- `public static ComputeMipchainSize(System.Int32 width, System.Int32 height, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevels) : System.Int32`  

```csharp
public static System.Int32 ComputeMipchainSize(System.Int32 width, System.Int32 height, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevels);
```

- `public static ComputeMipmapSize(System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevel) : System.Int32`  

```csharp
public static System.Int32 ComputeMipmapSize(System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevel);
```

- `public static ComputeMipmapSize(System.Int32 width, System.Int32 height, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevel) : System.Int32`  

```csharp
public static System.Int32 ComputeMipmapSize(System.Int32 width, System.Int32 height, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 mipLevel);
```

- `public static GetMinMipmapExtent(UnityEngine.Experimental.Rendering.GraphicsFormat format) : System.Int32`  

```csharp
public static System.Int32 GetMinMipmapExtent(UnityEngine.Experimental.Rendering.GraphicsFormat format);
```

- `public static GetSize(System.Int32 size, System.Int32 mipMapLevel) : System.Int32`  

```csharp
public static System.Int32 GetSize(System.Int32 size, System.Int32 mipMapLevel);
```


