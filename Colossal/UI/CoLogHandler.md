# Colossal.UI.CoLogHandler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.LogHandler`  
**Implements:** `cohtml.Net.ILogHandler`, `System.IDisposable`  

## Code

```csharp
public class CoLogHandler : cohtml.Net.LogHandler, cohtml.Net.ILogHandler, System.IDisposable
{
    private static Colossal.Logging.ILog m_Log;
    private static Colossal.UI.CoLogHandler s_Instance;
    private static System.Text.RegularExpressions.Regex s_FontWeightRegex;

    public static Colossal.UI.CoLogHandler Instance { get; }

    public CoLogHandler();

    public virtual System.Void Dispose();
    private cohtml.Net.Severity LessenSeverity(cohtml.Net.Severity severity, System.String message);
    private System.Boolean MuteMessage(System.String message);
    public virtual System.Void WriteLog(cohtml.Net.Severity severity, System.String message, System.UInt64 length);
}
```


## Fields

- `private static Colossal.Logging.ILog m_Log`  

```csharp
private static Colossal.Logging.ILog m_Log;
```

- `private static Colossal.UI.CoLogHandler s_Instance`  

```csharp
private static Colossal.UI.CoLogHandler s_Instance;
```

- `private static System.Text.RegularExpressions.Regex s_FontWeightRegex`  

```csharp
private static System.Text.RegularExpressions.Regex s_FontWeightRegex;
```


## Properties

- `public static Colossal.UI.CoLogHandler Instance { get }`  

```csharp
public static Colossal.UI.CoLogHandler Instance { get; }
```


## Constructors

- `public CoLogHandler()`  

```csharp
public CoLogHandler();
```


## Methods

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `private LessenSeverity(cohtml.Net.Severity severity, System.String message) : cohtml.Net.Severity`  

```csharp
private cohtml.Net.Severity LessenSeverity(cohtml.Net.Severity severity, System.String message);
```

- `private MuteMessage(System.String message) : System.Boolean`  

```csharp
private System.Boolean MuteMessage(System.String message);
```

- `public virtual WriteLog(cohtml.Net.Severity severity, System.String message, System.UInt64 length) : System.Void`  

```csharp
public virtual System.Void WriteLog(cohtml.Net.Severity severity, System.String message, System.UInt64 length);
```


