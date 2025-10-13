# Colossal.AssetPipeline.Diagnostic.Report+Asset

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Diagnostic.ReportBase`  

## Code

```csharp
public class Asset : Colossal.AssetPipeline.Diagnostic.ReportBase
{
    public readonly System.String name;
    private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+FileReport> m_Files;

    public System.Int32 errorsCount { get; }
    public System.Boolean hasErrors { get; }
    public System.Int32 warningsCount { get; }
    public System.Boolean hasWarnings { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+FileReport> files { get; }

    public Asset(System.String name);

    public Colossal.AssetPipeline.Diagnostic.Report+FileReport AddFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset);
    public Colossal.AssetPipeline.Diagnostic.Report+FileReport AddFile(Colossal.AssetPipeline.IAsset asset);
}
```


## Fields

- `public readonly System.String name`  

```csharp
public readonly System.String name;
```

- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+FileReport> m_Files`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+FileReport> m_Files;
```


## Properties

- `public System.Int32 errorsCount { get }`  

```csharp
public System.Int32 errorsCount { get; }
```

- `public System.Boolean hasErrors { get }`  

```csharp
public System.Boolean hasErrors { get; }
```

- `public System.Int32 warningsCount { get }`  

```csharp
public System.Int32 warningsCount { get; }
```

- `public System.Boolean hasWarnings { get }`  

```csharp
public System.Boolean hasWarnings { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+FileReport> files { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+FileReport> files { get; }
```


## Constructors

- `public Asset(System.String name)`  

```csharp
public Asset(System.String name);
```


## Methods

- `public AddFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset) : Colossal.AssetPipeline.Diagnostic.Report+FileReport`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+FileReport AddFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset);
```

- `public AddFile(Colossal.AssetPipeline.IAsset asset) : Colossal.AssetPipeline.Diagnostic.Report+FileReport`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+FileReport AddFile(Colossal.AssetPipeline.IAsset asset);
```


