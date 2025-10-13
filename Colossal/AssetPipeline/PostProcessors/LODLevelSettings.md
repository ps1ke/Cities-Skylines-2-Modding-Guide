# Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct LODLevelSettings
{
    public Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode;
    public Colossal.InstaLOD.FeatureImportance automatic;
    public System.Single maxDeviation;
    public System.Single percentTriangles;
    public System.Single weldingThreshold;
    public System.Boolean lockBoundaries;
    public System.Boolean sloppy;
    public System.Int32 bakeTextureSize;
    public System.Int32 bakeMaxTriangles;
    public System.Int32 bakeVoxelResolution;
    public System.Boolean bakeIgnoreBackface;

    public static System.Boolean IsModeBaking(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode);
    public static System.Boolean IsModeInstaLod(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode);
    public static System.Boolean IsModeMeshOptimizer(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode);
}
```


## Fields

- `public Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode`  

```csharp
public Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode;
```

- `public Colossal.InstaLOD.FeatureImportance automatic`  

```csharp
public Colossal.InstaLOD.FeatureImportance automatic;
```

- `public System.Single maxDeviation`  

```csharp
public System.Single maxDeviation;
```

- `public System.Single percentTriangles`  

```csharp
public System.Single percentTriangles;
```

- `public System.Single weldingThreshold`  

```csharp
public System.Single weldingThreshold;
```

- `public System.Boolean lockBoundaries`  

```csharp
public System.Boolean lockBoundaries;
```

- `public System.Boolean sloppy`  

```csharp
public System.Boolean sloppy;
```

- `public System.Int32 bakeTextureSize`  

```csharp
public System.Int32 bakeTextureSize;
```

- `public System.Int32 bakeMaxTriangles`  

```csharp
public System.Int32 bakeMaxTriangles;
```

- `public System.Int32 bakeVoxelResolution`  

```csharp
public System.Int32 bakeVoxelResolution;
```

- `public System.Boolean bakeIgnoreBackface`  

```csharp
public System.Boolean bakeIgnoreBackface;
```


## Methods

- `public static IsModeBaking(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode) : System.Boolean`  

```csharp
public static System.Boolean IsModeBaking(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode);
```

- `public static IsModeInstaLod(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode) : System.Boolean`  

```csharp
public static System.Boolean IsModeInstaLod(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode);
```

- `public static IsModeMeshOptimizer(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode) : System.Boolean`  

```csharp
public static System.Boolean IsModeMeshOptimizer(Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode mode);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings+LODMode`  

