# Colossal.OdinSerializer.SerializationAbortException

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Exception`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public class SerializationAbortException : System.Exception, System.Runtime.Serialization.ISerializable
{
    public SerializationAbortException(System.String message);
    public SerializationAbortException(System.String message, System.Exception innerException);

}
```


## Constructors

- `public SerializationAbortException(System.String message)`  

```csharp
public SerializationAbortException(System.String message);
```

- `public SerializationAbortException(System.String message, System.Exception innerException)`  

```csharp
public SerializationAbortException(System.String message, System.Exception innerException);
```


