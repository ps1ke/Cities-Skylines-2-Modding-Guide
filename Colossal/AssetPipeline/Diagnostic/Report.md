# Colossal.AssetPipeline.Diagnostic.Report

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Diagnostic.ReportBase`  

## Code

```csharp
public class Report : Colossal.AssetPipeline.Diagnostic.ReportBase
{
    public System.TimeSpan totalTime;
    private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+Asset> m_Assets;
    private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+Prefab> m_Prefabs;
    private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+AssetData> m_AssetDatas;
    private static System.Collections.Concurrent.ConcurrentDictionary<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport> s_FileMap;

    public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+Asset> assets { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+Prefab> prefabs { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+AssetData> assetDatas { get; }
    public System.Int32 errorsCount { get; }
    public System.Boolean hasErrors { get; }
    public System.Int32 warningsCount { get; }
    public System.Boolean hasWarnings { get; }

    public Report();

    public Colossal.AssetPipeline.Diagnostic.Report+Asset AddAsset(System.String name);
    public Colossal.AssetPipeline.Diagnostic.Report+AssetData AddAssetData(System.String name, System.Type type, System.Boolean generated);
    public System.Void AddInfoToAsset(System.String name, System.Type type, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset asset);
    public Colossal.AssetPipeline.Diagnostic.Report+Prefab AddPrefab(System.String name);
    public Colossal.AssetPipeline.Diagnostic.Report+AssetData GetAssetData(System.String name, System.Type type);
    public Colossal.AssetPipeline.Diagnostic.Report+FileReport GetFileReport(Colossal.AssetPipeline.IAsset asset);
    public System.Void Log(Colossal.Logging.ILog log);
    public System.Void Log(Colossal.Logging.ILog log, Colossal.AssetPipeline.Diagnostic.Severity overrideSeverity);
    public static System.Void PrintReportBase(Colossal.IndentedStringBuilder builder, Colossal.AssetPipeline.Diagnostic.ReportBase step, Colossal.AssetPipeline.Diagnostic.Severity severity);
    public static System.Void PrintSteps(Colossal.IndentedStringBuilder builder, System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps, Colossal.AssetPipeline.Diagnostic.Severity severity);
    public virtual System.String ToString();
    public System.String ToString(Colossal.AssetPipeline.Diagnostic.Severity severity);
    private static System.Collections.Generic.ICollection<System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, System.Int32>> UniqueSteps(System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps);
}
```


## Fields

- `public System.TimeSpan totalTime`  

```csharp
public System.TimeSpan totalTime;
```

- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+Asset> m_Assets`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+Asset> m_Assets;
```

- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+Prefab> m_Prefabs`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+Prefab> m_Prefabs;
```

- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+AssetData> m_AssetDatas`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+AssetData> m_AssetDatas;
```

- `private static System.Collections.Concurrent.ConcurrentDictionary<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport> s_FileMap`  

```csharp
private static System.Collections.Concurrent.ConcurrentDictionary<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport> s_FileMap;
```


## Properties

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+Asset> assets { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+Asset> assets { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+Prefab> prefabs { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+Prefab> prefabs { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+AssetData> assetDatas { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+AssetData> assetDatas { get; }
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

- `public Report()`  

```csharp
public Report();
```


## Methods

- `public AddAsset(System.String name) : Colossal.AssetPipeline.Diagnostic.Report+Asset`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+Asset AddAsset(System.String name);
```

- `public AddAssetData(System.String name, System.Type type, System.Boolean generated = False) : Colossal.AssetPipeline.Diagnostic.Report+AssetData`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+AssetData AddAssetData(System.String name, System.Type type, System.Boolean generated);
```

- `public AddInfoToAsset(System.String name, System.Type type, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset asset) : System.Void`  

```csharp
public System.Void AddInfoToAsset(System.String name, System.Type type, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset asset);
```

- `public AddPrefab(System.String name) : Colossal.AssetPipeline.Diagnostic.Report+Prefab`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+Prefab AddPrefab(System.String name);
```

- `public GetAssetData(System.String name, System.Type type) : Colossal.AssetPipeline.Diagnostic.Report+AssetData`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+AssetData GetAssetData(System.String name, System.Type type);
```

- `public GetFileReport(Colossal.AssetPipeline.IAsset asset) : Colossal.AssetPipeline.Diagnostic.Report+FileReport`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+FileReport GetFileReport(Colossal.AssetPipeline.IAsset asset);
```

- `public Log(Colossal.Logging.ILog log) : System.Void`  

```csharp
public System.Void Log(Colossal.Logging.ILog log);
```

- `public Log(Colossal.Logging.ILog log, Colossal.AssetPipeline.Diagnostic.Severity overrideSeverity) : System.Void`  

```csharp
public System.Void Log(Colossal.Logging.ILog log, Colossal.AssetPipeline.Diagnostic.Severity overrideSeverity);
```

- `public static PrintReportBase(Colossal.IndentedStringBuilder builder, Colossal.AssetPipeline.Diagnostic.ReportBase step, Colossal.AssetPipeline.Diagnostic.Severity severity) : System.Void`  

```csharp
public static System.Void PrintReportBase(Colossal.IndentedStringBuilder builder, Colossal.AssetPipeline.Diagnostic.ReportBase step, Colossal.AssetPipeline.Diagnostic.Severity severity);
```

- `public static PrintSteps(Colossal.IndentedStringBuilder builder, System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps, Colossal.AssetPipeline.Diagnostic.Severity severity) : System.Void`  

```csharp
public static System.Void PrintSteps(Colossal.IndentedStringBuilder builder, System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps, Colossal.AssetPipeline.Diagnostic.Severity severity);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public ToString(Colossal.AssetPipeline.Diagnostic.Severity severity) : System.String`  

```csharp
public System.String ToString(Colossal.AssetPipeline.Diagnostic.Severity severity);
```

- `private static UniqueSteps(System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps) : System.Collections.Generic.ICollection<System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, System.Int32>>`  

```csharp
private static System.Collections.Generic.ICollection<System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, System.Int32>> UniqueSteps(System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps);
```


## Nested types

- `Colossal.AssetPipeline.Diagnostic.Report+IFile`  
- `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`  
- `Colossal.AssetPipeline.Diagnostic.Report+ImportStep`  
- `Colossal.AssetPipeline.Diagnostic.Report+AssetData`  
- `Colossal.AssetPipeline.Diagnostic.Report+Prefab`  
- `Colossal.AssetPipeline.Diagnostic.Report+Asset`  
- `Colossal.AssetPipeline.Diagnostic.Report+FileReport`  
- `Colossal.AssetPipeline.Diagnostic.Report+<>c__DisplayClass12_0`  
- `Colossal.AssetPipeline.Diagnostic.Report+<>c__DisplayClass13_0`  
- `Colossal.AssetPipeline.Diagnostic.Report+<>c__DisplayClass14_0`  

