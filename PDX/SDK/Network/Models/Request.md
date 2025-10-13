# PDX.SDK.Network.Models.Request

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Network.Models`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Request
{
    public System.Collections.Generic.List<PDX.SDK.Network.Models.Header> Headers;
    public System.Byte[] Body;
    public PDX.SDK.Contracts.Internal.FlowData FlowData;
    public System.Int32 Timeout;

    public Request();

    public System.Void SetBody(System.Byte[] body);
    public System.Void SetBody(System.String body, System.Text.Encoding encoding);
}
```


## Fields

- `public System.Collections.Generic.List<PDX.SDK.Network.Models.Header> Headers`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Network.Models.Header> Headers;
```

- `public System.Byte[] Body`  

```csharp
public System.Byte[] Body;
```

- `public PDX.SDK.Contracts.Internal.FlowData FlowData`  

```csharp
public PDX.SDK.Contracts.Internal.FlowData FlowData;
```

- `public System.Int32 Timeout`  

```csharp
public System.Int32 Timeout;
```


## Constructors

- `public Request()`  

```csharp
public Request();
```


## Methods

- `public SetBody(System.Byte[] body) : System.Void`  

```csharp
public System.Void SetBody(System.Byte[] body);
```

- `public SetBody(System.String body, System.Text.Encoding encoding = null) : System.Void`  

```csharp
public System.Void SetBody(System.String body, System.Text.Encoding encoding);
```


