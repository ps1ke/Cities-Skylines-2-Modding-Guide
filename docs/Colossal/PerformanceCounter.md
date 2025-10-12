# Colossal.PerformanceCounter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.Diagnostics.Stopwatch m_Stopwatch`  
- `private System.Action<System.TimeSpan> m_Callback`  

## Properties

- `public System.TimeSpan result { get }`  
- `public System.TimeSpan resultAndRestart { get }`  
- `public System.String reportSeconds { get }`  

## Constructors

- `public PerformanceCounter()`  
- `public PerformanceCounter(System.Action<System.TimeSpan> callback)`  

## Methods

- `public Dispose() : System.Void`  
- `public Report(System.Action<System.TimeSpan> callback) : System.Void`  
- `public static Start(System.Action<System.TimeSpan> callback) : Colossal.PerformanceCounter`  

