# Colossal.Json.DecodeException

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `System.Exception`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class DecodeException : System.Exception, System.Runtime.Serialization.ISerializable
{
    public DecodeException(System.String message);
    public DecodeException(System.String message, System.Exception innerException);

}
```


## Constructors

- `public DecodeException(System.String message)`  

```csharp
public DecodeException(System.String message);
```

- `public DecodeException(System.String message, System.Exception innerException)`  

```csharp
public DecodeException(System.String message, System.Exception innerException);
```


