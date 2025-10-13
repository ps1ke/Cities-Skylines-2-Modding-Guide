# Colossal.Logging.ILog+StackTraceScope

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct StackTraceScope : System.IDisposable
{
    private System.Boolean m_Disposed;
    private Colossal.Logging.ILog m_Log;
    private System.Boolean m_LogStackTrace;

    public StackTraceScope(Colossal.Logging.ILog log);

    public System.Void Dispose();
}
```


## Fields

- `private System.Boolean m_Disposed`  

```csharp
private System.Boolean m_Disposed;
```

- `private Colossal.Logging.ILog m_Log`  

```csharp
private Colossal.Logging.ILog m_Log;
```

- `private System.Boolean m_LogStackTrace`  

```csharp
private System.Boolean m_LogStackTrace;
```


## Constructors

- `public StackTraceScope(Colossal.Logging.ILog log)`  

```csharp
public StackTraceScope(Colossal.Logging.ILog log);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


