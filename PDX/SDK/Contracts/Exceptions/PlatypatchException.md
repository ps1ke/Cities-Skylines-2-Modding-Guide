# PDX.SDK.Contracts.Exceptions.PlatypatchException

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Exceptions`  

**Type:** class public  

**Base:** `System.Exception`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public class PlatypatchException : System.Exception, System.Runtime.Serialization.ISerializable
{
    public PlatypatchException(System.String message);
    public PlatypatchException(System.String message, System.Exception innerException);

}
```


## Constructors

- `public PlatypatchException(System.String message)`  

```csharp
public PlatypatchException(System.String message);
```

- `public PlatypatchException(System.String message, System.Exception innerException)`  

```csharp
public PlatypatchException(System.String message, System.Exception innerException);
```


