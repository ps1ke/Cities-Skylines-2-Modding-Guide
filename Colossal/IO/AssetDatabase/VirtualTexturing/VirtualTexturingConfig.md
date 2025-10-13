# Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class VirtualTexturingConfig : UnityEngine.ScriptableObject
{
    public UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode;
    public System.Int32 NumRequests;
    public System.Int32 tileSize;
    public System.Int32 maxTextureSize;
    public Colossal.IO.AssetDatabase.VirtualTexturing.StackData[] stackDatas;
    public System.Int32 cpuCacheSize;
    public System.UInt32 bc7GPUCacheSize;
    public System.UInt32 bc7UNormGPUCacheSize;
    public System.UInt32 stagingAreaInTiles;
    public Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig+CacheSizeOverride[] m_CacheSizeOverrides;
    public System.Int32 nbVTMaterialsToStartAsyncLoadingPerFrame;
    public System.Int32 nbVTMaterialsToStartAsyncDuplicateInitPerFrame;
    private static const System.Int32 MaxNbTilesPerDimension;
    public static const System.Int32 MaxNbLayersPerStack;
    public static const System.Int32 Padding;
    public static const System.Int32 DblPadding;
    public static const System.Int32 MaxNbStacksPerMaterial;
    public static const System.Int32 NbBytesPerPixel;

    public System.Int32 CPUCacheSize { get; }
    public System.UInt32 BC7GPUCacheSize { get; }
    public System.UInt32 BC7UNormGPUCacheSize { get; }
    public System.UInt32 StagingAreaInTiles { get; }
    public System.Int32 TotalWidth { get; }
    public System.Int32 TotalHeight { get; }

    public VirtualTexturingConfig();

}
```


## Fields

- `public UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode`  

```csharp
public UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode;
```

- `public System.Int32 NumRequests`  

```csharp
public System.Int32 NumRequests;
```

- `public System.Int32 tileSize`  

```csharp
public System.Int32 tileSize;
```

- `public System.Int32 maxTextureSize`  

```csharp
public System.Int32 maxTextureSize;
```

- `public Colossal.IO.AssetDatabase.VirtualTexturing.StackData[] stackDatas`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.StackData[] stackDatas;
```

- `public System.Int32 cpuCacheSize`  

```csharp
public System.Int32 cpuCacheSize;
```

- `public System.UInt32 bc7GPUCacheSize`  

```csharp
public System.UInt32 bc7GPUCacheSize;
```

- `public System.UInt32 bc7UNormGPUCacheSize`  

```csharp
public System.UInt32 bc7UNormGPUCacheSize;
```

- `public System.UInt32 stagingAreaInTiles`  

```csharp
public System.UInt32 stagingAreaInTiles;
```

- `public Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig+CacheSizeOverride[] m_CacheSizeOverrides`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig+CacheSizeOverride[] m_CacheSizeOverrides;
```

- `public System.Int32 nbVTMaterialsToStartAsyncLoadingPerFrame`  

```csharp
public System.Int32 nbVTMaterialsToStartAsyncLoadingPerFrame;
```

- `public System.Int32 nbVTMaterialsToStartAsyncDuplicateInitPerFrame`  

```csharp
public System.Int32 nbVTMaterialsToStartAsyncDuplicateInitPerFrame;
```

- `private static const System.Int32 MaxNbTilesPerDimension`  

```csharp
private static const System.Int32 MaxNbTilesPerDimension;
```

- `public static const System.Int32 MaxNbLayersPerStack`  

```csharp
public static const System.Int32 MaxNbLayersPerStack;
```

- `public static const System.Int32 Padding`  

```csharp
public static const System.Int32 Padding;
```

- `public static const System.Int32 DblPadding`  

```csharp
public static const System.Int32 DblPadding;
```

- `public static const System.Int32 MaxNbStacksPerMaterial`  

```csharp
public static const System.Int32 MaxNbStacksPerMaterial;
```

- `public static const System.Int32 NbBytesPerPixel`  

```csharp
public static const System.Int32 NbBytesPerPixel;
```


## Properties

- `public System.Int32 CPUCacheSize { get }`  

```csharp
public System.Int32 CPUCacheSize { get; }
```

- `public System.UInt32 BC7GPUCacheSize { get }`  

```csharp
public System.UInt32 BC7GPUCacheSize { get; }
```

- `public System.UInt32 BC7UNormGPUCacheSize { get }`  

```csharp
public System.UInt32 BC7UNormGPUCacheSize { get; }
```

- `public System.UInt32 StagingAreaInTiles { get }`  

```csharp
public System.UInt32 StagingAreaInTiles { get; }
```

- `public System.Int32 TotalWidth { get }`  

```csharp
public System.Int32 TotalWidth { get; }
```

- `public System.Int32 TotalHeight { get }`  

```csharp
public System.Int32 TotalHeight { get; }
```


## Constructors

- `public VirtualTexturingConfig()`  

```csharp
public VirtualTexturingConfig();
```


## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig+CacheSizeOverride`  

