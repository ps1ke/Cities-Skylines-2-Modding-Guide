# Colossal.TaskProgress

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IProgress<Colossal.ProgressTracker>`  

## Code

```csharp
public class TaskProgress : System.IProgress<Colossal.ProgressTracker>
{
    private readonly System.Action<Colossal.ProgressTracker> m_Handler;
    private readonly System.Diagnostics.Stopwatch m_Stopwatch;
    private System.Int64 <updateFrequency>k__BackingField;
    private System.String m_SubTaskName;
    private Colossal.ProgressTracker+Group m_SubTaskGroup;
    public static const System.Int64 kUpdateFrequencyMs;

    public System.Int64 updateFrequency { get; set; }
    public System.String subTaskName { get; set; }
    public Colossal.ProgressTracker+Group subTaskGroup { get; set; }

    public TaskProgress(System.Action<Colossal.ProgressTracker> handler);

    public Colossal.TaskProgress GetSubProgress(System.String taskName, Colossal.ProgressTracker+Group progressGroup);
    public System.Void Report(Colossal.ProgressTracker value);
}
```


## Fields

- `private readonly System.Action<Colossal.ProgressTracker> m_Handler`  

```csharp
private readonly System.Action<Colossal.ProgressTracker> m_Handler;
```

- `private readonly System.Diagnostics.Stopwatch m_Stopwatch`  

```csharp
private readonly System.Diagnostics.Stopwatch m_Stopwatch;
```

- `private System.Int64 <updateFrequency>k__BackingField`  

```csharp
private System.Int64 <updateFrequency>k__BackingField;
```

- `private System.String m_SubTaskName`  

```csharp
private System.String m_SubTaskName;
```

- `private Colossal.ProgressTracker+Group m_SubTaskGroup`  

```csharp
private Colossal.ProgressTracker+Group m_SubTaskGroup;
```

- `public static const System.Int64 kUpdateFrequencyMs`  

```csharp
public static const System.Int64 kUpdateFrequencyMs;
```


## Properties

- `public System.Int64 updateFrequency { get; set }`  

```csharp
public System.Int64 updateFrequency { get; set; }
```

- `public System.String subTaskName { get; set }`  

```csharp
public System.String subTaskName { get; set; }
```

- `public Colossal.ProgressTracker+Group subTaskGroup { get; set }`  

```csharp
public Colossal.ProgressTracker+Group subTaskGroup { get; set; }
```


## Constructors

- `public TaskProgress(System.Action<Colossal.ProgressTracker> handler)`  

```csharp
public TaskProgress(System.Action<Colossal.ProgressTracker> handler);
```


## Methods

- `public GetSubProgress(System.String taskName = Dummy, Colossal.ProgressTracker+Group progressGroup = None) : Colossal.TaskProgress`  

```csharp
public Colossal.TaskProgress GetSubProgress(System.String taskName, Colossal.ProgressTracker+Group progressGroup);
```

- `public Report(Colossal.ProgressTracker value) : System.Void`  

```csharp
public System.Void Report(Colossal.ProgressTracker value);
```


