# Colossal.PSI.Common.RateLimiter

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.DateTime[] m_CallHistory`  
- `private System.Int32 m_Start`  
- `private System.Int32 m_End`  
- `private readonly System.TimeSpan m_Interval`  
- `private readonly System.Int32 m_CallCap`  
- `private readonly System.String m_DebugName`  

## Constructors

- `public RateLimiter(System.Int32 callCap, System.TimeSpan interval, System.String debugName = Rate limiter)`  

## Methods

- `internal IsExceeded() : System.Boolean`  
- `internal UpdateCallHistory() : System.Void`  
- `internal WaitForRelease(System.Threading.CancellationToken cancellationToken) : System.Threading.Tasks.Task`  

## Nested types

- `Colossal.PSI.Common.RateLimiter+<WaitForRelease>d__9`  

