# Colossal.AssetPipeline.Diagnostic.ReportBase

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class ReportBase
{
    private readonly System.Collections.Concurrent.ConcurrentQueue<System.String> m_Errors;
    private readonly System.Collections.Concurrent.ConcurrentQueue<System.String> m_Warnings;
    private readonly System.Collections.Concurrent.ConcurrentQueue<System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity>> m_Messages;
    private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> m_ImportSteps;

    public System.Collections.Generic.IReadOnlyCollection<System.String> errors { get; }
    public System.Collections.Generic.IReadOnlyCollection<System.String> warnings { get; }
    public System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity>> messages { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps { get; }
    public System.Int32 errorsCount { get; }
    public System.Boolean hasErrors { get; }
    public System.Int32 warningsCount { get; }
    public System.Boolean hasWarnings { get; }

    protected ReportBase();

    public System.Void AddError(System.String message);
    public Colossal.AssetPipeline.Diagnostic.Report+ImportStep AddImportStep(System.String name);
    public Colossal.AssetPipeline.Diagnostic.Report+ImportStep AddImportStep(System.String name, Colossal.PerformanceCounter perf);
    public System.Void AddImportStep(Colossal.AssetPipeline.Diagnostic.Report+ImportStep step);
    public System.Void AddMessage(System.String message, Colossal.AssetPipeline.Diagnostic.Severity severity);
    public System.Void AddMessage(System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity> message);
    public System.Void AddWarning(System.String message);
}
```


## Fields

- `private readonly System.Collections.Concurrent.ConcurrentQueue<System.String> m_Errors`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<System.String> m_Errors;
```

- `private readonly System.Collections.Concurrent.ConcurrentQueue<System.String> m_Warnings`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<System.String> m_Warnings;
```

- `private readonly System.Collections.Concurrent.ConcurrentQueue<System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity>> m_Messages`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity>> m_Messages;
```

- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> m_ImportSteps`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> m_ImportSteps;
```


## Properties

- `public System.Collections.Generic.IReadOnlyCollection<System.String> errors { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<System.String> errors { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<System.String> warnings { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<System.String> warnings { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity>> messages { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity>> messages { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps { get; }
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

- `protected ReportBase()`  

```csharp
protected ReportBase();
```


## Methods

- `public AddError(System.String message) : System.Void`  

```csharp
public System.Void AddError(System.String message);
```

- `public AddImportStep(System.String name) : Colossal.AssetPipeline.Diagnostic.Report+ImportStep`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+ImportStep AddImportStep(System.String name);
```

- `public AddImportStep(System.String name, Colossal.PerformanceCounter perf) : Colossal.AssetPipeline.Diagnostic.Report+ImportStep`  

```csharp
public Colossal.AssetPipeline.Diagnostic.Report+ImportStep AddImportStep(System.String name, Colossal.PerformanceCounter perf);
```

- `public AddImportStep(Colossal.AssetPipeline.Diagnostic.Report+ImportStep step) : System.Void`  

```csharp
public System.Void AddImportStep(Colossal.AssetPipeline.Diagnostic.Report+ImportStep step);
```

- `public AddMessage(System.String message, Colossal.AssetPipeline.Diagnostic.Severity severity = Normal) : System.Void`  

```csharp
public System.Void AddMessage(System.String message, Colossal.AssetPipeline.Diagnostic.Severity severity);
```

- `public AddMessage(System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity> message) : System.Void`  

```csharp
public System.Void AddMessage(System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity> message);
```

- `public AddWarning(System.String message) : System.Void`  

```csharp
public System.Void AddWarning(System.String message);
```


