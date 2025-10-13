# Colossal.Logging.LogAlreadyOpenException

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** class public  

**Base:** `System.IO.IOException`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public class LogAlreadyOpenException : System.IO.IOException, System.Runtime.Serialization.ISerializable
{
    public LogAlreadyOpenException();
    public LogAlreadyOpenException(System.String message);
    public LogAlreadyOpenException(System.String message, System.Exception inner);

}
```


## Constructors

- `public LogAlreadyOpenException()`  

```csharp
public LogAlreadyOpenException();
```

- `public LogAlreadyOpenException(System.String message)`  

```csharp
public LogAlreadyOpenException(System.String message);
```

- `public LogAlreadyOpenException(System.String message, System.Exception inner)`  

```csharp
public LogAlreadyOpenException(System.String message, System.Exception inner);
```


