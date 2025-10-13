# PDX.ModsUI.Services.ILogService

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.Services`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ILogService
{
    public PDX.SDK.Contracts.Enums.LogLevel LogLevel { get; set; }

    public abstract System.Void Debug(System.String message, System.String source, System.String callerFilePath);
    public abstract System.Void Error(System.Exception error, System.String source, System.String callerFilePath, System.String callerMemberName, System.Int32 callerLineNumber);
    public abstract System.Void Error(System.String message, System.String source, System.String callerFilePath, System.String callerMemberName, System.Int32 callerLineNumber);
    public abstract System.Void Info(System.String message, System.String source, System.String callerFilePath);
    public abstract System.Void Warning(System.String message, System.String source, System.String callerFilePath);
    public abstract System.Void WriteLogEntry(System.String message, PDX.SDK.Contracts.Enums.LogLevel logLevel, System.String source, System.String callerFilePath);
}
```


## Properties

- `public PDX.SDK.Contracts.Enums.LogLevel LogLevel { get; set }`  

```csharp
public PDX.SDK.Contracts.Enums.LogLevel LogLevel { get; set; }
```


## Methods

- `public abstract Debug(System.String message, System.String source = null, System.String callerFilePath = null) : System.Void`  

```csharp
public abstract System.Void Debug(System.String message, System.String source, System.String callerFilePath);
```

- `public abstract Error(System.Exception error, System.String source = null, System.String callerFilePath = null, System.String callerMemberName = null, System.Int32 callerLineNumber = -1) : System.Void`  

```csharp
public abstract System.Void Error(System.Exception error, System.String source, System.String callerFilePath, System.String callerMemberName, System.Int32 callerLineNumber);
```

- `public abstract Error(System.String message, System.String source = null, System.String callerFilePath = null, System.String callerMemberName = null, System.Int32 callerLineNumber = -1) : System.Void`  

```csharp
public abstract System.Void Error(System.String message, System.String source, System.String callerFilePath, System.String callerMemberName, System.Int32 callerLineNumber);
```

- `public abstract Info(System.String message, System.String source = null, System.String callerFilePath = null) : System.Void`  

```csharp
public abstract System.Void Info(System.String message, System.String source, System.String callerFilePath);
```

- `public abstract Warning(System.String message, System.String source = null, System.String callerFilePath = null) : System.Void`  

```csharp
public abstract System.Void Warning(System.String message, System.String source, System.String callerFilePath);
```

- `public abstract WriteLogEntry(System.String message, PDX.SDK.Contracts.Enums.LogLevel logLevel, System.String source = null, System.String callerFilePath = null) : System.Void`  

```csharp
public abstract System.Void WriteLogEntry(System.String message, PDX.SDK.Contracts.Enums.LogLevel logLevel, System.String source, System.String callerFilePath);
```


