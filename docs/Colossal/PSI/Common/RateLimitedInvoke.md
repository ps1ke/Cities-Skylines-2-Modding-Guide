# Colossal.PSI.Common.RateLimitedInvoke

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private readonly Colossal.PSI.Common.RateLimiter[] m_Limiters`  
- `private readonly Colossal.PSI.Common.LimitedActionHandling m_LimitedActionHandling`  
- `private readonly System.Threading.SemaphoreSlim m_Semaphore`  
- `private readonly System.Boolean m_RequireInternetConnection`  
- `private System.Int32 m_PendingActions`  
- `private System.Threading.CancellationTokenSource m_Cts`  

## Constructors

- `public RateLimitedInvoke(Colossal.PSI.Common.LimitedActionHandling limitedActionHandling, System.Boolean requireInternetConnection, Colossal.PSI.Common.RateLimiter[] limiters)`  
- `public RateLimitedInvoke(Colossal.PSI.Common.LimitedActionHandling limitedActionHandling, System.Boolean requireInternetConnection, System.Threading.SemaphoreSlim semaphore, Colossal.PSI.Common.RateLimiter[] limiters)`  

## Methods

- `private <Invoke>b__10_0(Colossal.PSI.Common.RateLimiter limiter) : System.Threading.Tasks.Task`  
- `private <Invoke>b__11_0(Colossal.PSI.Common.RateLimiter limiter) : System.Threading.Tasks.Task`  
- `private <Invoke>b__11_1() : System.Void`  
- `public CancelPending() : System.Void`  
- `public Dispose() : System.Void`  
- `private HandleConnectivityChanged(System.Boolean connected) : System.Void`  
- `public Invoke(System.Action action, System.Action onCanceled = null) : System.Void`  
- `public Invoke(System.Action<System.Action> action, System.Action onCanceled = null) : System.Void`  
- `private IsLimiterExceeded(System.Collections.Generic.List`1[[Colossal.PSI.Common.RateLimiter, Colossal.PSI.Common, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& limiters) : System.Boolean`  
- `private UpdateCallHistory() : System.Void`  

## Nested types

- `Colossal.PSI.Common.RateLimitedInvoke+<Invoke>d__10`  
- `Colossal.PSI.Common.RateLimitedInvoke+<Invoke>d__11`  

