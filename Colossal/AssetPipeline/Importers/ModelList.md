# Colossal.AssetPipeline.Importers.ModelImporter+ModelList

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ModelImporter+Model>`, `System.Collections.IEnumerable`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public class ModelList : System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ModelImporter+Model>, System.Collections.IEnumerable
{
    public Colossal.AssetPipeline.Importers.ModelImporter+Model[] models;

    public Colossal.AssetPipeline.Importers.ModelImporter+Model Item { get; }
    public Colossal.AssetPipeline.IAsset sourceAsset { get; set; }
    public System.Boolean isValid { get; }
    public System.Int32 Count { get; }

    public ModelList();

    public System.Void Dispose();
    public System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Importers.ModelImporter+Model> GetEnumerator();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
}
```


## Fields

- `public Colossal.AssetPipeline.Importers.ModelImporter+Model[] models`  

```csharp
public Colossal.AssetPipeline.Importers.ModelImporter+Model[] models;
```


## Properties

- `public Colossal.AssetPipeline.Importers.ModelImporter+Model Item { get }`  

```csharp
public Colossal.AssetPipeline.Importers.ModelImporter+Model Item { get; }
```

- `public Colossal.AssetPipeline.IAsset sourceAsset { get; set }`  

```csharp
public Colossal.AssetPipeline.IAsset sourceAsset { get; set; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```


## Constructors

- `public ModelList()`  

```csharp
public ModelList();
```


## Methods

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


## Nested types

- `Colossal.AssetPipeline.Importers.ModelImporter+ModelList+<>c`  

