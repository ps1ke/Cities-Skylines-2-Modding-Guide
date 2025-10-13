# Colossal.Logging.LogInvalidException

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** class public  

**Base:** `System.IO.IOException`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public class LogInvalidException : System.IO.IOException, System.Runtime.Serialization.ISerializable
{
    public LogInvalidException();
    public LogInvalidException(System.String message);
    public LogInvalidException(System.String message, System.Exception inner);

}
```


## Constructors

- `public LogInvalidException()`  

```csharp
public LogInvalidException();
```

- `public LogInvalidException(System.String message)`  

```csharp
public LogInvalidException(System.String message);
```

- `public LogInvalidException(System.String message, System.Exception inner)`  

```csharp
public LogInvalidException(System.String message, System.Exception inner);
```


