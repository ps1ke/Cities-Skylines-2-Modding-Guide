# Colossal.OdinSerializer.DebugContext

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class DebugContext
{
    private readonly System.Object LOCK;
    private Colossal.OdinSerializer.ILogger logger;
    private Colossal.OdinSerializer.LoggingPolicy loggingPolicy;
    private Colossal.OdinSerializer.ErrorHandlingPolicy errorHandlingPolicy;

    public Colossal.OdinSerializer.ILogger Logger { get; set; }
    public Colossal.OdinSerializer.LoggingPolicy LoggingPolicy { get; set; }
    public Colossal.OdinSerializer.ErrorHandlingPolicy ErrorHandlingPolicy { get; set; }

    public DebugContext();

    public System.Void LogError(System.String message);
    public System.Void LogException(System.Exception exception);
    public System.Void LogWarning(System.String message);
    public System.Void ResetToDefault();
}
```


## Fields

- `private readonly System.Object LOCK`  

```csharp
private readonly System.Object LOCK;
```

- `private Colossal.OdinSerializer.ILogger logger`  

```csharp
private Colossal.OdinSerializer.ILogger logger;
```

- `private Colossal.OdinSerializer.LoggingPolicy loggingPolicy`  

```csharp
private Colossal.OdinSerializer.LoggingPolicy loggingPolicy;
```

- `private Colossal.OdinSerializer.ErrorHandlingPolicy errorHandlingPolicy`  

```csharp
private Colossal.OdinSerializer.ErrorHandlingPolicy errorHandlingPolicy;
```


## Properties

- `public Colossal.OdinSerializer.ILogger Logger { get; set }`  

```csharp
public Colossal.OdinSerializer.ILogger Logger { get; set; }
```

- `public Colossal.OdinSerializer.LoggingPolicy LoggingPolicy { get; set }`  

```csharp
public Colossal.OdinSerializer.LoggingPolicy LoggingPolicy { get; set; }
```

- `public Colossal.OdinSerializer.ErrorHandlingPolicy ErrorHandlingPolicy { get; set }`  

```csharp
public Colossal.OdinSerializer.ErrorHandlingPolicy ErrorHandlingPolicy { get; set; }
```


## Constructors

- `public DebugContext()`  

```csharp
public DebugContext();
```


## Methods

- `public LogError(System.String message) : System.Void`  

```csharp
public System.Void LogError(System.String message);
```

- `public LogException(System.Exception exception) : System.Void`  

```csharp
public System.Void LogException(System.Exception exception);
```

- `public LogWarning(System.String message) : System.Void`  

```csharp
public System.Void LogWarning(System.String message);
```

- `public ResetToDefault() : System.Void`  

```csharp
public System.Void ResetToDefault();
```


