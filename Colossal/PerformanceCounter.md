# Colossal.PerformanceCounter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class PerformanceCounter : System.IDisposable
{
    private System.Diagnostics.Stopwatch m_Stopwatch;
    private System.Action<System.TimeSpan> m_Callback;

    public System.TimeSpan result { get; }
    public System.TimeSpan resultAndRestart { get; }
    public System.String reportSeconds { get; }

    public PerformanceCounter();
    public PerformanceCounter(System.Action<System.TimeSpan> callback);

    public System.Void Dispose();
    public System.Void Report(System.Action<System.TimeSpan> callback);
    public static Colossal.PerformanceCounter Start(System.Action<System.TimeSpan> callback);
}
```


## Fields

- `private System.Diagnostics.Stopwatch m_Stopwatch`  

```csharp
private System.Diagnostics.Stopwatch m_Stopwatch;
```

- `private System.Action<System.TimeSpan> m_Callback`  

```csharp
private System.Action<System.TimeSpan> m_Callback;
```


## Properties

- `public System.TimeSpan result { get }`  

```csharp
public System.TimeSpan result { get; }
```

- `public System.TimeSpan resultAndRestart { get }`  

```csharp
public System.TimeSpan resultAndRestart { get; }
```

- `public System.String reportSeconds { get }`  

```csharp
public System.String reportSeconds { get; }
```


## Constructors

- `public PerformanceCounter()`  

```csharp
public PerformanceCounter();
```

- `public PerformanceCounter(System.Action<System.TimeSpan> callback)`  

```csharp
public PerformanceCounter(System.Action<System.TimeSpan> callback);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Report(System.Action<System.TimeSpan> callback) : System.Void`  

```csharp
public System.Void Report(System.Action<System.TimeSpan> callback);
```

- `public static Start(System.Action<System.TimeSpan> callback) : Colossal.PerformanceCounter`  

```csharp
public static Colossal.PerformanceCounter Start(System.Action<System.TimeSpan> callback);
```


