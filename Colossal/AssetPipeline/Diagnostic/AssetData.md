# Colossal.AssetPipeline.Diagnostic.Report+AssetData

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Diagnostic.ReportBase`  

## Code

```csharp
public class AssetData : Colossal.AssetPipeline.Diagnostic.ReportBase
{
    public readonly System.String name;
    private Colossal.AssetPipeline.Diagnostic.ReportAssetData <assetData>k__BackingField;
    public readonly System.Type type;
    public readonly System.Boolean generated;
    public System.Int32 referenceCount;
    private readonly System.Collections.Generic.List<Colossal.AssetPipeline.Diagnostic.Report+FileReport> m_Files;

    public Colossal.AssetPipeline.Diagnostic.ReportAssetData assetData { get; set; }
    public System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.Diagnostic.Report+FileReport> files { get; }
    public System.Int32 errorsCount { get; }
    public System.Boolean hasErrors { get; }
    public System.Int32 warningsCount { get; }
    public System.Boolean hasWarnings { get; }

    public AssetData(System.String name, System.Type type, System.Boolean generated);

    public System.Void AddFile(Colossal.AssetPipeline.IAsset asset);
    public System.Void AddFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset);
    public System.Void AddFiles(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assets);
    public System.Void AddFiles(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.IAsset> assets);
    public System.Void AssignAssetData(Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset asset);
    public virtual System.String ToString();
}
```


## Fields

- `public readonly System.String name`  

```csharp
public readonly System.String name;
```

- `private Colossal.AssetPipeline.Diagnostic.ReportAssetData <assetData>k__BackingField`  

```csharp
private Colossal.AssetPipeline.Diagnostic.ReportAssetData <assetData>k__BackingField;
```

- `public readonly System.Type type`  

```csharp
public readonly System.Type type;
```

- `public readonly System.Boolean generated`  

```csharp
public readonly System.Boolean generated;
```

- `public System.Int32 referenceCount`  

```csharp
public System.Int32 referenceCount;
```

- `private readonly System.Collections.Generic.List<Colossal.AssetPipeline.Diagnostic.Report+FileReport> m_Files`  

```csharp
private readonly System.Collections.Generic.List<Colossal.AssetPipeline.Diagnostic.Report+FileReport> m_Files;
```


## Properties

- `public Colossal.AssetPipeline.Diagnostic.ReportAssetData assetData { get; set }`  

```csharp
public Colossal.AssetPipeline.Diagnostic.ReportAssetData assetData { get; set; }
```

- `public System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.Diagnostic.Report+FileReport> files { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.Diagnostic.Report+FileReport> files { get; }
```

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


## Constructors

- `public AssetData(System.String name, System.Type type, System.Boolean generated)`  

```csharp
public AssetData(System.String name, System.Type type, System.Boolean generated);
```


## Methods

- `public AddFile(Colossal.AssetPipeline.IAsset asset) : System.Void`  

```csharp
public System.Void AddFile(Colossal.AssetPipeline.IAsset asset);
```

- `public AddFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset) : System.Void`  

```csharp
public System.Void AddFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset);
```

- `public AddFiles(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assets) : System.Void`  

```csharp
public System.Void AddFiles(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assets);
```

- `public AddFiles(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.IAsset> assets) : System.Void`  

```csharp
public System.Void AddFiles(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.IAsset> assets);
```

- `public AssignAssetData(Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset asset) : System.Void`  

```csharp
public System.Void AssignAssetData(Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset asset);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


