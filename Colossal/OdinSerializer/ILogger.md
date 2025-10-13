# Colossal.OdinSerializer.ILogger

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ILogger
{
    public abstract System.Void LogError(System.String error);
    public abstract System.Void LogException(System.Exception exception);
    public abstract System.Void LogWarning(System.String warning);
}
```


## Methods

- `public abstract LogError(System.String error) : System.Void`  

```csharp
public abstract System.Void LogError(System.String error);
```

- `public abstract LogException(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void LogException(System.Exception exception);
```

- `public abstract LogWarning(System.String warning) : System.Void`  

```csharp
public abstract System.Void LogWarning(System.String warning);
```


