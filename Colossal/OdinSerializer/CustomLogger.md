# Colossal.OdinSerializer.CustomLogger

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.ILogger`  

## Code

```csharp
public class CustomLogger : Colossal.OdinSerializer.ILogger
{
    private System.Action<System.String> logWarningDelegate;
    private System.Action<System.String> logErrorDelegate;
    private System.Action<System.Exception> logExceptionDelegate;

    public CustomLogger(System.Action<System.String> logWarningDelegate, System.Action<System.String> logErrorDelegate, System.Action<System.Exception> logExceptionDelegate);

    public System.Void LogError(System.String error);
    public System.Void LogException(System.Exception exception);
    public System.Void LogWarning(System.String warning);
}
```


## Fields

- `private System.Action<System.String> logWarningDelegate`  

```csharp
private System.Action<System.String> logWarningDelegate;
```

- `private System.Action<System.String> logErrorDelegate`  

```csharp
private System.Action<System.String> logErrorDelegate;
```

- `private System.Action<System.Exception> logExceptionDelegate`  

```csharp
private System.Action<System.Exception> logExceptionDelegate;
```


## Constructors

- `public CustomLogger(System.Action<System.String> logWarningDelegate, System.Action<System.String> logErrorDelegate, System.Action<System.Exception> logExceptionDelegate)`  

```csharp
public CustomLogger(System.Action<System.String> logWarningDelegate, System.Action<System.String> logErrorDelegate, System.Action<System.Exception> logExceptionDelegate);
```


## Methods

- `public LogError(System.String error) : System.Void`  

```csharp
public System.Void LogError(System.String error);
```

- `public LogException(System.Exception exception) : System.Void`  

```csharp
public System.Void LogException(System.Exception exception);
```

- `public LogWarning(System.String warning) : System.Void`  

```csharp
public System.Void LogWarning(System.String warning);
```


