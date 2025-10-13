# Colossal.AssetPipeline.Diagnostic.ReportFile

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `System.IEquatable<Colossal.AssetPipeline.Diagnostic.ReportFile>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct ReportFile : Colossal.AssetPipeline.Diagnostic.Report+IFile, System.IEquatable<Colossal.AssetPipeline.Diagnostic.ReportFile>
{
    public readonly Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset;
    public readonly System.Int64 size;

    private System.String Colossal.AssetPipeline.Diagnostic.Report.IFile.path { private get; }
    private System.Int64 Colossal.AssetPipeline.Diagnostic.Report.IFile.size { private get; }

    public ReportFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset);

    public System.Boolean Equals(Colossal.AssetPipeline.Diagnostic.ReportFile other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public virtual System.String ToString();
}
```


## Fields

- `public readonly Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset`  

```csharp
public readonly Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset;
```

- `public readonly System.Int64 size`  

```csharp
public readonly System.Int64 size;
```


## Properties

- `private System.String Colossal.AssetPipeline.Diagnostic.Report.IFile.path { private get }`  

```csharp
private System.String Colossal.AssetPipeline.Diagnostic.Report.IFile.path { private get; }
```

- `private System.Int64 Colossal.AssetPipeline.Diagnostic.Report.IFile.size { private get }`  

```csharp
private System.Int64 Colossal.AssetPipeline.Diagnostic.Report.IFile.size { private get; }
```


## Constructors

- `public ReportFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset)`  

```csharp
public ReportFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset);
```


## Methods

- `public Equals(Colossal.AssetPipeline.Diagnostic.ReportFile other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.AssetPipeline.Diagnostic.ReportFile other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


