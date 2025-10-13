# Colossal.UI.TaskScheduler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class TaskScheduler
{
    private readonly System.Threading.AutoResetEvent m_LayoutReset;
    private readonly System.Threading.Thread m_LayoutThread;
    private System.Boolean m_IsLayoutThreadRunning;
    private readonly System.Threading.CountdownEvent m_ThreadPoolCountdownEvent;
    private static System.Int32 s_ThreadCount;

    public static System.UInt32 ThreadCount { get; }

    public TaskScheduler();

    private System.Void <.ctor>b__5_0();
    private System.Void <ScheduleTask>b__8_0(System.Object _);
    public System.Void Dispose();
    public System.Void ScheduleTask(cohtml.Net.WorkType type);
    public System.Void Start();
    public System.Void Stop();
}
```


## Fields

- `private readonly System.Threading.AutoResetEvent m_LayoutReset`  

```csharp
private readonly System.Threading.AutoResetEvent m_LayoutReset;
```

- `private readonly System.Threading.Thread m_LayoutThread`  

```csharp
private readonly System.Threading.Thread m_LayoutThread;
```

- `private System.Boolean m_IsLayoutThreadRunning`  

```csharp
private System.Boolean m_IsLayoutThreadRunning;
```

- `private readonly System.Threading.CountdownEvent m_ThreadPoolCountdownEvent`  

```csharp
private readonly System.Threading.CountdownEvent m_ThreadPoolCountdownEvent;
```

- `private static System.Int32 s_ThreadCount`  

```csharp
private static System.Int32 s_ThreadCount;
```


## Properties

- `public static System.UInt32 ThreadCount { get }`  

```csharp
public static System.UInt32 ThreadCount { get; }
```


## Constructors

- `public TaskScheduler()`  

```csharp
public TaskScheduler();
```


## Methods

- `private <.ctor>b__5_0() : System.Void`  

```csharp
private System.Void <.ctor>b__5_0();
```

- `private <ScheduleTask>b__8_0(System.Object _) : System.Void`  

```csharp
private System.Void <ScheduleTask>b__8_0(System.Object _);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ScheduleTask(cohtml.Net.WorkType type) : System.Void`  

```csharp
public System.Void ScheduleTask(cohtml.Net.WorkType type);
```

- `public Start() : System.Void`  

```csharp
public System.Void Start();
```

- `public Stop() : System.Void`  

```csharp
public System.Void Stop();
```


