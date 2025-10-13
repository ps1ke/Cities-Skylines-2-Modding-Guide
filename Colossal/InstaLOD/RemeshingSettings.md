# Colossal.InstaLOD.RemeshingSettings

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct RemeshingSettings
{
    public Colossal.InstaLOD.RemeshingMode mode;
    private System.Int32 m_ReconstructIgnoreBackface;
    public System.Int32 resolution;
    public System.Int32 maxTriangles;
    public System.Single hardAngleThreshold;
    public System.Single weldDistance;
    public System.Int32 gutterSize;
    private System.Int32 m_OptimizeLockBoundaries;
    private System.Int32 m_UseGPU;

    public System.Boolean reconstructIgnoreBackface { get; set; }
    public System.Boolean optimizeLockBoundaries { get; set; }
    public System.Boolean useGPU { get; set; }

    public static Colossal.InstaLOD.RemeshingSettings Default();
}
```


## Fields

- `public Colossal.InstaLOD.RemeshingMode mode`  

```csharp
public Colossal.InstaLOD.RemeshingMode mode;
```

- `private System.Int32 m_ReconstructIgnoreBackface`  

```csharp
private System.Int32 m_ReconstructIgnoreBackface;
```

- `public System.Int32 resolution`  

```csharp
public System.Int32 resolution;
```

- `public System.Int32 maxTriangles`  

```csharp
public System.Int32 maxTriangles;
```

- `public System.Single hardAngleThreshold`  

```csharp
public System.Single hardAngleThreshold;
```

- `public System.Single weldDistance`  

```csharp
public System.Single weldDistance;
```

- `public System.Int32 gutterSize`  

```csharp
public System.Int32 gutterSize;
```

- `private System.Int32 m_OptimizeLockBoundaries`  

```csharp
private System.Int32 m_OptimizeLockBoundaries;
```

- `private System.Int32 m_UseGPU`  

```csharp
private System.Int32 m_UseGPU;
```


## Properties

- `public System.Boolean reconstructIgnoreBackface { get; set }`  

```csharp
public System.Boolean reconstructIgnoreBackface { get; set; }
```

- `public System.Boolean optimizeLockBoundaries { get; set }`  

```csharp
public System.Boolean optimizeLockBoundaries { get; set; }
```

- `public System.Boolean useGPU { get; set }`  

```csharp
public System.Boolean useGPU { get; set; }
```


## Methods

- `public static Default() : Colossal.InstaLOD.RemeshingSettings`  

```csharp
public static Colossal.InstaLOD.RemeshingSettings Default();
```


