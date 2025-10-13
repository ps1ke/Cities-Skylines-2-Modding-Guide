# PDX.SDK.Network.HTTP

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Network`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class HTTP
{
    public static const System.Int32 DefaultErrorCode;

    protected HTTP();

    public abstract System.Void AddDefaultHeader(System.String name, System.String value);
    public abstract System.Void ClearDefaultHeaders();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> DELETE(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> Download(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler, System.Threading.CancellationToken cancellationToken);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> GET(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public abstract System.Int32 GetTimeoutFileDownload();
    public abstract System.Int32 GetTimeoutFileUpload();
    public abstract System.Int32 GetTimeoutREST();
    public abstract System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> GetTransfers();
    protected static PDX.SDK.Network.Models.Response MatchErrorToResponse(System.Boolean isUnityRequestDone, System.Boolean isUnityNetworkError, System.Boolean isUnityHttpError, System.UInt64 downloadedBytes, System.String unityErrorMessage, System.Exception otherException, System.Nullable<System.Int32> statusCode);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PATCH(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> POST(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PUT(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public abstract System.Void RemoveOngoingTransfer(PDX.SDK.Contracts.Enums.ETransferType transferType, PDX.SDK.Contracts.Enums.ETransferServiceType transferServiceType, System.String transferId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> REST(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public abstract System.Void SetPDXHeaders(System.String namespace, System.String gameVersion, System.String sdkVersion, System.String platform);
    public abstract System.Void SetTimeoutFileDownload(System.Int32 timeout);
    public abstract System.Void SetTimeoutFileUpload(System.Int32 timeout);
    public abstract System.Void SetTimeoutREST(System.Int32 timeout);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> Upload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler, System.Threading.CancellationToken cancellationToken);
}
```


## Fields

- `public static const System.Int32 DefaultErrorCode`  

```csharp
public static const System.Int32 DefaultErrorCode;
```


## Constructors

- `protected HTTP()`  

```csharp
protected HTTP();
```


## Methods

- `public abstract AddDefaultHeader(System.String name, System.String value) : System.Void`  

```csharp
public abstract System.Void AddDefaultHeader(System.String name, System.String value);
```

- `public abstract ClearDefaultHeaders() : System.Void`  

```csharp
public abstract System.Void ClearDefaultHeaders();
```

- `public abstract DELETE(System.String url, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> DELETE(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public abstract Download(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> Download(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler, System.Threading.CancellationToken cancellationToken);
```

- `public abstract GET(System.String url, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> GET(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public abstract GetTimeoutFileDownload() : System.Int32`  

```csharp
public abstract System.Int32 GetTimeoutFileDownload();
```

- `public abstract GetTimeoutFileUpload() : System.Int32`  

```csharp
public abstract System.Int32 GetTimeoutFileUpload();
```

- `public abstract GetTimeoutREST() : System.Int32`  

```csharp
public abstract System.Int32 GetTimeoutREST();
```

- `public abstract GetTransfers() : System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus>`  

```csharp
public abstract System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> GetTransfers();
```

- `protected static MatchErrorToResponse(System.Boolean isUnityRequestDone = True, System.Boolean isUnityNetworkError = False, System.Boolean isUnityHttpError = False, System.UInt64 downloadedBytes = 0, System.String unityErrorMessage = null, System.Exception otherException = null, System.Nullable<System.Int32> statusCode = null) : PDX.SDK.Network.Models.Response`  

```csharp
protected static PDX.SDK.Network.Models.Response MatchErrorToResponse(System.Boolean isUnityRequestDone, System.Boolean isUnityNetworkError, System.Boolean isUnityHttpError, System.UInt64 downloadedBytes, System.String unityErrorMessage, System.Exception otherException, System.Nullable<System.Int32> statusCode);
```

- `public abstract PATCH(System.String url, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PATCH(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public abstract POST(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> POST(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public abstract PUT(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PUT(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public abstract RemoveOngoingTransfer(PDX.SDK.Contracts.Enums.ETransferType transferType, PDX.SDK.Contracts.Enums.ETransferServiceType transferServiceType, System.String transferId) : System.Void`  

```csharp
public abstract System.Void RemoveOngoingTransfer(PDX.SDK.Contracts.Enums.ETransferType transferType, PDX.SDK.Contracts.Enums.ETransferServiceType transferServiceType, System.String transferId);
```

- `public abstract REST(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> REST(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public abstract SetPDXHeaders(System.String namespace, System.String gameVersion, System.String sdkVersion, System.String platform) : System.Void`  

```csharp
public abstract System.Void SetPDXHeaders(System.String namespace, System.String gameVersion, System.String sdkVersion, System.String platform);
```

- `public abstract SetTimeoutFileDownload(System.Int32 timeout) : System.Void`  

```csharp
public abstract System.Void SetTimeoutFileDownload(System.Int32 timeout);
```

- `public abstract SetTimeoutFileUpload(System.Int32 timeout) : System.Void`  

```csharp
public abstract System.Void SetTimeoutFileUpload(System.Int32 timeout);
```

- `public abstract SetTimeoutREST(System.Int32 timeout) : System.Void`  

```csharp
public abstract System.Void SetTimeoutREST(System.Int32 timeout);
```

- `public abstract Upload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> Upload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler, System.Threading.CancellationToken cancellationToken);
```


