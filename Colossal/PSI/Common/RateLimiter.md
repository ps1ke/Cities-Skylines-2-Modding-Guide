# Colossal.PSI.Common.RateLimiter

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class RateLimiter
{
    private readonly System.DateTime[] m_CallHistory;
    private System.Int32 m_Start;
    private System.Int32 m_End;
    private readonly System.TimeSpan m_Interval;
    private readonly System.Int32 m_CallCap;
    private readonly System.String m_DebugName;

    public RateLimiter(System.Int32 callCap, System.TimeSpan interval, System.String debugName);

    internal System.Boolean IsExceeded();
    internal System.Void UpdateCallHistory();
    internal System.Threading.Tasks.Task WaitForRelease(System.Threading.CancellationToken cancellationToken);
}
```


## Fields

- `private readonly System.DateTime[] m_CallHistory`  

```csharp
private readonly System.DateTime[] m_CallHistory;
```

- `private System.Int32 m_Start`  

```csharp
private System.Int32 m_Start;
```

- `private System.Int32 m_End`  

```csharp
private System.Int32 m_End;
```

- `private readonly System.TimeSpan m_Interval`  

```csharp
private readonly System.TimeSpan m_Interval;
```

- `private readonly System.Int32 m_CallCap`  

```csharp
private readonly System.Int32 m_CallCap;
```

- `private readonly System.String m_DebugName`  

```csharp
private readonly System.String m_DebugName;
```


## Constructors

- `public RateLimiter(System.Int32 callCap, System.TimeSpan interval, System.String debugName = Rate limiter)`  

```csharp
public RateLimiter(System.Int32 callCap, System.TimeSpan interval, System.String debugName);
```


## Methods

- `internal IsExceeded() : System.Boolean`  

```csharp
internal System.Boolean IsExceeded();
```

- `internal UpdateCallHistory() : System.Void`  

```csharp
internal System.Void UpdateCallHistory();
```

- `internal WaitForRelease(System.Threading.CancellationToken cancellationToken) : System.Threading.Tasks.Task`  

```csharp
internal System.Threading.Tasks.Task WaitForRelease(System.Threading.CancellationToken cancellationToken);
```


## Nested types

- `Colossal.PSI.Common.RateLimiter+<WaitForRelease>d__9`  

