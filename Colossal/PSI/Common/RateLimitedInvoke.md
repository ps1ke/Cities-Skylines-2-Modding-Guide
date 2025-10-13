# Colossal.PSI.Common.RateLimitedInvoke

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class RateLimitedInvoke : System.IDisposable
{
    private readonly Colossal.PSI.Common.RateLimiter[] m_Limiters;
    private readonly Colossal.PSI.Common.LimitedActionHandling m_LimitedActionHandling;
    private readonly System.Threading.SemaphoreSlim m_Semaphore;
    private readonly System.Boolean m_RequireInternetConnection;
    private System.Int32 m_PendingActions;
    private System.Threading.CancellationTokenSource m_Cts;

    public RateLimitedInvoke(Colossal.PSI.Common.LimitedActionHandling limitedActionHandling, System.Boolean requireInternetConnection, Colossal.PSI.Common.RateLimiter[] limiters);
    public RateLimitedInvoke(Colossal.PSI.Common.LimitedActionHandling limitedActionHandling, System.Boolean requireInternetConnection, System.Threading.SemaphoreSlim semaphore, Colossal.PSI.Common.RateLimiter[] limiters);

    private System.Threading.Tasks.Task <Invoke>b__10_0(Colossal.PSI.Common.RateLimiter limiter);
    private System.Threading.Tasks.Task <Invoke>b__11_0(Colossal.PSI.Common.RateLimiter limiter);
    private System.Void <Invoke>b__11_1();
    public System.Void CancelPending();
    public System.Void Dispose();
    private System.Void HandleConnectivityChanged(System.Boolean connected);
    public System.Void Invoke(System.Action action, System.Action onCanceled);
    public System.Void Invoke(System.Action<System.Action> action, System.Action onCanceled);
    private System.Boolean IsLimiterExceeded(System.Collections.Generic.List`1[[Colossal.PSI.Common.RateLimiter, Colossal.PSI.Common, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& limiters);
    private System.Void UpdateCallHistory();
}
```


## Fields

- `private readonly Colossal.PSI.Common.RateLimiter[] m_Limiters`  

```csharp
private readonly Colossal.PSI.Common.RateLimiter[] m_Limiters;
```

- `private readonly Colossal.PSI.Common.LimitedActionHandling m_LimitedActionHandling`  

```csharp
private readonly Colossal.PSI.Common.LimitedActionHandling m_LimitedActionHandling;
```

- `private readonly System.Threading.SemaphoreSlim m_Semaphore`  

```csharp
private readonly System.Threading.SemaphoreSlim m_Semaphore;
```

- `private readonly System.Boolean m_RequireInternetConnection`  

```csharp
private readonly System.Boolean m_RequireInternetConnection;
```

- `private System.Int32 m_PendingActions`  

```csharp
private System.Int32 m_PendingActions;
```

- `private System.Threading.CancellationTokenSource m_Cts`  

```csharp
private System.Threading.CancellationTokenSource m_Cts;
```


## Constructors

- `public RateLimitedInvoke(Colossal.PSI.Common.LimitedActionHandling limitedActionHandling, System.Boolean requireInternetConnection, Colossal.PSI.Common.RateLimiter[] limiters)`  

```csharp
public RateLimitedInvoke(Colossal.PSI.Common.LimitedActionHandling limitedActionHandling, System.Boolean requireInternetConnection, Colossal.PSI.Common.RateLimiter[] limiters);
```

- `public RateLimitedInvoke(Colossal.PSI.Common.LimitedActionHandling limitedActionHandling, System.Boolean requireInternetConnection, System.Threading.SemaphoreSlim semaphore, Colossal.PSI.Common.RateLimiter[] limiters)`  

```csharp
public RateLimitedInvoke(Colossal.PSI.Common.LimitedActionHandling limitedActionHandling, System.Boolean requireInternetConnection, System.Threading.SemaphoreSlim semaphore, Colossal.PSI.Common.RateLimiter[] limiters);
```


## Methods

- `private <Invoke>b__10_0(Colossal.PSI.Common.RateLimiter limiter) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task <Invoke>b__10_0(Colossal.PSI.Common.RateLimiter limiter);
```

- `private <Invoke>b__11_0(Colossal.PSI.Common.RateLimiter limiter) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task <Invoke>b__11_0(Colossal.PSI.Common.RateLimiter limiter);
```

- `private <Invoke>b__11_1() : System.Void`  

```csharp
private System.Void <Invoke>b__11_1();
```

- `public CancelPending() : System.Void`  

```csharp
public System.Void CancelPending();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private HandleConnectivityChanged(System.Boolean connected) : System.Void`  

```csharp
private System.Void HandleConnectivityChanged(System.Boolean connected);
```

- `public Invoke(System.Action action, System.Action onCanceled = null) : System.Void`  

```csharp
public System.Void Invoke(System.Action action, System.Action onCanceled);
```

- `public Invoke(System.Action<System.Action> action, System.Action onCanceled = null) : System.Void`  

```csharp
public System.Void Invoke(System.Action<System.Action> action, System.Action onCanceled);
```

- `private IsLimiterExceeded(System.Collections.Generic.List`1[[Colossal.PSI.Common.RateLimiter, Colossal.PSI.Common, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& limiters) : System.Boolean`  

```csharp
private System.Boolean IsLimiterExceeded(System.Collections.Generic.List`1[[Colossal.PSI.Common.RateLimiter, Colossal.PSI.Common, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& limiters);
```

- `private UpdateCallHistory() : System.Void`  

```csharp
private System.Void UpdateCallHistory();
```


## Nested types

- `Colossal.PSI.Common.RateLimitedInvoke+<Invoke>d__10`  
- `Colossal.PSI.Common.RateLimitedInvoke+<Invoke>d__11`  

