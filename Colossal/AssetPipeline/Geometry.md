# Colossal.AssetPipeline.Geometry

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ModelImporter+Model>`, `System.Collections.IEnumerable`, `System.IDisposable`  

## Code

```csharp
public class Geometry : System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ModelImporter+Model>, System.Collections.IEnumerable, System.IDisposable
{
    public System.Action<UnityEngine.GameObject> OnPostDebugOutput;
    public Colossal.AssetPipeline.Importers.ModelImporter+Model[] models;

    public System.String name { get; }
    public System.Boolean hasSkin { get; }
    public System.Boolean isValid { get; }

    public Geometry(Colossal.AssetPipeline.Importers.ModelImporter+Model[] models);

    public Colossal.Mathematics.Bounds3 CalcBounds();
    public System.Single CalcSurfaceArea();
    public System.Int32 CalcTotalIndices();
    public System.Int32 CalcTotalVertices();
    public System.Void Dispose();
    public System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Importers.ModelImporter+Model> GetEnumerator();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public UnityEngine.Mesh[] ToUnityMeshes(System.Boolean hideAndDontSave);
}
```


## Fields

- `public System.Action<UnityEngine.GameObject> OnPostDebugOutput`  

```csharp
public System.Action<UnityEngine.GameObject> OnPostDebugOutput;
```

- `public Colossal.AssetPipeline.Importers.ModelImporter+Model[] models`  

```csharp
public Colossal.AssetPipeline.Importers.ModelImporter+Model[] models;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean hasSkin { get }`  

```csharp
public System.Boolean hasSkin { get; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```


## Constructors

- `public Geometry(Colossal.AssetPipeline.Importers.ModelImporter+Model[] models)`  

```csharp
public Geometry(Colossal.AssetPipeline.Importers.ModelImporter+Model[] models);
```


## Methods

- `public CalcBounds() : Colossal.Mathematics.Bounds3`  

```csharp
public Colossal.Mathematics.Bounds3 CalcBounds();
```

- `public CalcSurfaceArea() : System.Single`  

```csharp
public System.Single CalcSurfaceArea();
```

- `public CalcTotalIndices() : System.Int32`  

```csharp
public System.Int32 CalcTotalIndices();
```

- `public CalcTotalVertices() : System.Int32`  

```csharp
public System.Int32 CalcTotalVertices();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Importers.ModelImporter+Model>`  

```csharp
public System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Importers.ModelImporter+Model> GetEnumerator();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public ToUnityMeshes(System.Boolean hideAndDontSave = True) : UnityEngine.Mesh[]`  

```csharp
public UnityEngine.Mesh[] ToUnityMeshes(System.Boolean hideAndDontSave);
```


