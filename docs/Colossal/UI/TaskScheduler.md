# Colossal.UI.TaskScheduler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Threading.AutoResetEvent m_LayoutReset`  
- `private readonly System.Threading.Thread m_LayoutThread`  
- `private System.Boolean m_IsLayoutThreadRunning`  
- `private readonly System.Threading.CountdownEvent m_ThreadPoolCountdownEvent`  
- `private static System.Int32 s_ThreadCount`  

## Properties

- `public static System.UInt32 ThreadCount { get }`  

## Constructors

- `public TaskScheduler()`  

## Methods

- `private <.ctor>b__5_0() : System.Void`  
- `private <ScheduleTask>b__8_0(System.Object _) : System.Void`  
- `public Dispose() : System.Void`  
- `public ScheduleTask(cohtml.Net.WorkType type) : System.Void`  
- `public Start() : System.Void`  
- `public Stop() : System.Void`  

