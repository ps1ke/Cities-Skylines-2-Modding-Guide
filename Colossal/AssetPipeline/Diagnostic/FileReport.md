# Colossal.AssetPipeline.Diagnostic.Report+FileReport

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Diagnostic.ReportBase`  
**Implements:** `System.IEquatable<Colossal.AssetPipeline.Diagnostic.Report+FileReport>`  

## Code

```csharp
public class FileReport : Colossal.AssetPipeline.Diagnostic.ReportBase, System.IEquatable<Colossal.AssetPipeline.Diagnostic.Report+FileReport>
{
    private Colossal.AssetPipeline.Diagnostic.ReportFile <file>k__BackingField;
    public System.Int32 originalSize;
    public System.Int32 encodedSize;
    public System.Int32 compressedSize;

    public Colossal.AssetPipeline.Diagnostic.ReportFile file { get; private set; }

    public FileReport(Colossal.AssetPipeline.Diagnostic.ReportFile file);

    public System.Boolean Equals(Colossal.AssetPipeline.Diagnostic.Report+FileReport other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private Colossal.AssetPipeline.Diagnostic.ReportFile <file>k__BackingField`  

```csharp
private Colossal.AssetPipeline.Diagnostic.ReportFile <file>k__BackingField;
```

- `public System.Int32 originalSize`  

```csharp
public System.Int32 originalSize;
```

- `public System.Int32 encodedSize`  

```csharp
public System.Int32 encodedSize;
```

- `public System.Int32 compressedSize`  

```csharp
public System.Int32 compressedSize;
```


## Properties

- `public Colossal.AssetPipeline.Diagnostic.ReportFile file { get; private set }`  

```csharp
public Colossal.AssetPipeline.Diagnostic.ReportFile file { get; private set; }
```


## Constructors

- `public FileReport(Colossal.AssetPipeline.Diagnostic.ReportFile file)`  

```csharp
public FileReport(Colossal.AssetPipeline.Diagnostic.ReportFile file);
```


## Methods

- `public Equals(Colossal.AssetPipeline.Diagnostic.Report+FileReport other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.AssetPipeline.Diagnostic.Report+FileReport other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


