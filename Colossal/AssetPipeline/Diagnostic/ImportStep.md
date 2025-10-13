# Colossal.AssetPipeline.Diagnostic.Report+ImportStep

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Diagnostic.ReportBase`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class ImportStep : Colossal.AssetPipeline.Diagnostic.ReportBase, System.IDisposable
{
    public readonly System.String name;
    public System.TimeSpan time;
    private Colossal.PerformanceCounter perf;

    public ImportStep(System.String name, Colossal.PerformanceCounter perf);

    public System.Void Dispose();
    public virtual System.String ToString();
}
```


## Fields

- `public readonly System.String name`  

```csharp
public readonly System.String name;
```

- `public System.TimeSpan time`  

```csharp
public System.TimeSpan time;
```

- `private Colossal.PerformanceCounter perf`  

```csharp
private Colossal.PerformanceCounter perf;
```


## Constructors

- `public ImportStep(System.String name, Colossal.PerformanceCounter perf = null)`  

```csharp
public ImportStep(System.String name, Colossal.PerformanceCounter perf);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


