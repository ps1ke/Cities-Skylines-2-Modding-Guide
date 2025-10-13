# Colossal.InstaLOD.OptimizeSettings

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct OptimizeSettings
{
    public Colossal.InstaLOD.FeatureImportance automaticQuality;
    public System.Single percentTriangles;
    public System.Single maxDeviation;
    public System.Single weldingThreshold;
    public System.Single weldingNormalAngleThreshold;
    public System.Single healTJunctionThreshold;
    private System.Int32 m_LockBoundaries;
    public System.Single unitScaleFactor;
    public Colossal.InstaLOD.FeatureImportance boundaryImportance;
    public Colossal.InstaLOD.FeatureImportance textureImportance;
    public Colossal.InstaLOD.FeatureImportance shadingImportance;
    public Colossal.InstaLOD.FeatureImportance silhouetteImportance;
    public Colossal.InstaLOD.FeatureImportance skinningImportance;

    public System.Boolean lockBoundaries { get; set; }

    public static Colossal.InstaLOD.OptimizeSettings Default();
}
```


## Fields

- `public Colossal.InstaLOD.FeatureImportance automaticQuality`  

```csharp
public Colossal.InstaLOD.FeatureImportance automaticQuality;
```

- `public System.Single percentTriangles`  

```csharp
public System.Single percentTriangles;
```

- `public System.Single maxDeviation`  

```csharp
public System.Single maxDeviation;
```

- `public System.Single weldingThreshold`  

```csharp
public System.Single weldingThreshold;
```

- `public System.Single weldingNormalAngleThreshold`  

```csharp
public System.Single weldingNormalAngleThreshold;
```

- `public System.Single healTJunctionThreshold`  

```csharp
public System.Single healTJunctionThreshold;
```

- `private System.Int32 m_LockBoundaries`  

```csharp
private System.Int32 m_LockBoundaries;
```

- `public System.Single unitScaleFactor`  

```csharp
public System.Single unitScaleFactor;
```

- `public Colossal.InstaLOD.FeatureImportance boundaryImportance`  

```csharp
public Colossal.InstaLOD.FeatureImportance boundaryImportance;
```

- `public Colossal.InstaLOD.FeatureImportance textureImportance`  

```csharp
public Colossal.InstaLOD.FeatureImportance textureImportance;
```

- `public Colossal.InstaLOD.FeatureImportance shadingImportance`  

```csharp
public Colossal.InstaLOD.FeatureImportance shadingImportance;
```

- `public Colossal.InstaLOD.FeatureImportance silhouetteImportance`  

```csharp
public Colossal.InstaLOD.FeatureImportance silhouetteImportance;
```

- `public Colossal.InstaLOD.FeatureImportance skinningImportance`  

```csharp
public Colossal.InstaLOD.FeatureImportance skinningImportance;
```


## Properties

- `public System.Boolean lockBoundaries { get; set }`  

```csharp
public System.Boolean lockBoundaries { get; set; }
```


## Methods

- `public static Default() : Colossal.InstaLOD.OptimizeSettings`  

```csharp
public static Colossal.InstaLOD.OptimizeSettings Default();
```


