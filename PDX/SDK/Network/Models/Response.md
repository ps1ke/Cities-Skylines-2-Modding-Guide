# PDX.SDK.Network.Models.Response

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Network.Models`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Response
{
    public System.Collections.Generic.Dictionary<System.String, System.String> Headers;
    public System.Byte[] Body;
    public System.Int32 StatusCode;

    public Response();

    public static PDX.SDK.Network.Models.Response CreateErrorResponse(System.String errorBody, System.Nullable<System.Int32> statusCode);
}
```


## Fields

- `public System.Collections.Generic.Dictionary<System.String, System.String> Headers`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.String> Headers;
```

- `public System.Byte[] Body`  

```csharp
public System.Byte[] Body;
```

- `public System.Int32 StatusCode`  

```csharp
public System.Int32 StatusCode;
```


## Constructors

- `public Response()`  

```csharp
public Response();
```


## Methods

- `public static CreateErrorResponse(System.String errorBody, System.Nullable<System.Int32> statusCode = null) : PDX.SDK.Network.Models.Response`  

```csharp
public static PDX.SDK.Network.Models.Response CreateErrorResponse(System.String errorBody, System.Nullable<System.Int32> statusCode);
```


