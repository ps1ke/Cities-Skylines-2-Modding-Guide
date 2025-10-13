# Colossal.AssetPipeline.PostProcessors.PostProcessorCache

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class PostProcessorCache
{
    private static Colossal.Logging.ILog log;
    private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelPostProcessor> sModelPostProcessors;
    private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor> sModelSurfacePostProcessors;
    private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor> sGeometryPostProcessors;
    private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.ITexturePostProcessor> sTexturePostProcessors;

    public static System.Void CachePostProcessors(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
    public static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor> GetGeometryPostProcessors();
    public static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelPostProcessor> GetModelPostProcessors();
    public static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor> GetModelSurfacePostProcessors();
    public static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.ITexturePostProcessor> GetTexturePostProcessors();
}
```


## Fields

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelPostProcessor> sModelPostProcessors`  

```csharp
private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelPostProcessor> sModelPostProcessors;
```

- `private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor> sModelSurfacePostProcessors`  

```csharp
private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor> sModelSurfacePostProcessors;
```

- `private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor> sGeometryPostProcessors`  

```csharp
private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor> sGeometryPostProcessors;
```

- `private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.ITexturePostProcessor> sTexturePostProcessors`  

```csharp
private static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.ITexturePostProcessor> sTexturePostProcessors;
```


## Methods

- `public static CachePostProcessors(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report = null) : System.Void`  

```csharp
public static System.Void CachePostProcessors(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
```

- `public static GetGeometryPostProcessors() : System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor>`  

```csharp
public static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor> GetGeometryPostProcessors();
```

- `public static GetModelPostProcessors() : System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelPostProcessor>`  

```csharp
public static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelPostProcessor> GetModelPostProcessors();
```

- `public static GetModelSurfacePostProcessors() : System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor>`  

```csharp
public static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor> GetModelSurfacePostProcessors();
```

- `public static GetTexturePostProcessors() : System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.ITexturePostProcessor>`  

```csharp
public static System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.PostProcessors.ITexturePostProcessor> GetTexturePostProcessors();
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.PostProcessorCache+<>c`  

