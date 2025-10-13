# PDX.ModsUI.Services.LogService

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.Services`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.ModsUI.Services.ILogService`  

## Code

```csharp
public class LogService : PDX.ModsUI.Services.ILogService
{
    private PDX.SDK.Contracts.Enums.LogLevel <LogLevel>k__BackingField;
    protected readonly System.Collections.Generic.Dictionary<PDX.SDK.Contracts.Enums.LogLevel, System.String> LogLevelNames;

    public PDX.SDK.Contracts.Enums.LogLevel LogLevel { get; set; }

    public LogService();
    public LogService(PDX.SDK.Contracts.Enums.LogLevel level);

    public virtual System.Void Debug(System.String message, System.String source, System.String callerFilePath);
    public virtual System.Void Error(System.String message, System.String source, System.String callerFilePath, System.String callerMemberName, System.Int32 callerLineNumber);
    public virtual System.Void Error(System.Exception error, System.String source, System.String callerFilePath, System.String callerMemberName, System.Int32 callerLineNumber);
    public virtual System.Void Info(System.String message, System.String source, System.String callerFilePath);
    public virtual System.Void Warning(System.String message, System.String source, System.String callerFilePath);
    public virtual System.Void WriteLogEntry(System.String message, PDX.SDK.Contracts.Enums.LogLevel logLevel, System.String source, System.String callerFilePath);
}
```


## Fields

- `private PDX.SDK.Contracts.Enums.LogLevel <LogLevel>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Enums.LogLevel <LogLevel>k__BackingField;
```

- `protected readonly System.Collections.Generic.Dictionary<PDX.SDK.Contracts.Enums.LogLevel, System.String> LogLevelNames`  

```csharp
protected readonly System.Collections.Generic.Dictionary<PDX.SDK.Contracts.Enums.LogLevel, System.String> LogLevelNames;
```


## Properties

- `public PDX.SDK.Contracts.Enums.LogLevel LogLevel { get; set }`  

```csharp
public PDX.SDK.Contracts.Enums.LogLevel LogLevel { get; set; }
```


## Constructors

- `public LogService()`  

```csharp
public LogService();
```

- `public LogService(PDX.SDK.Contracts.Enums.LogLevel level)`  

```csharp
public LogService(PDX.SDK.Contracts.Enums.LogLevel level);
```


## Methods

- `public virtual Debug(System.String message, System.String source = null, System.String callerFilePath = null) : System.Void`  

```csharp
public virtual System.Void Debug(System.String message, System.String source, System.String callerFilePath);
```

- `public virtual Error(System.String message, System.String source = null, System.String callerFilePath = null, System.String callerMemberName = null, System.Int32 callerLineNumber = -1) : System.Void`  

```csharp
public virtual System.Void Error(System.String message, System.String source, System.String callerFilePath, System.String callerMemberName, System.Int32 callerLineNumber);
```

- `public virtual Error(System.Exception error, System.String source = null, System.String callerFilePath = null, System.String callerMemberName = null, System.Int32 callerLineNumber = -1) : System.Void`  

```csharp
public virtual System.Void Error(System.Exception error, System.String source, System.String callerFilePath, System.String callerMemberName, System.Int32 callerLineNumber);
```

- `public virtual Info(System.String message, System.String source = null, System.String callerFilePath = null) : System.Void`  

```csharp
public virtual System.Void Info(System.String message, System.String source, System.String callerFilePath);
```

- `public virtual Warning(System.String message, System.String source = null, System.String callerFilePath = null) : System.Void`  

```csharp
public virtual System.Void Warning(System.String message, System.String source, System.String callerFilePath);
```

- `public virtual WriteLogEntry(System.String message, PDX.SDK.Contracts.Enums.LogLevel logLevel, System.String source = null, System.String callerFilePath = null) : System.Void`  

```csharp
public virtual System.Void WriteLogEntry(System.String message, PDX.SDK.Contracts.Enums.LogLevel logLevel, System.String source, System.String callerFilePath);
```


