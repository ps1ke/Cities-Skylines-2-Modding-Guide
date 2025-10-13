# PDX.SDK.Network.DotNet.HTTPDotNet

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Network.DotNet`  

**Type:** class public  

**Base:** `PDX.SDK.Network.HTTP`  

## Code

```csharp
public class HTTPDotNet : PDX.SDK.Network.HTTP
{
    protected System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> ongoingTransfers;
    private System.TimeSpan timeoutREST;
    private System.TimeSpan timeoutFileDownload;
    private System.TimeSpan timeoutFileUpload;
    private System.Net.Http.HttpClient client;
    private readonly PDX.SDK.Contracts.Logging.ILogger _logger;
    protected static System.Object ongoingTransfersLock;

    public HTTPDotNet(PDX.SDK.Contracts.Logging.ILogger logger);

    public virtual System.Void AddDefaultHeader(System.String name, System.String value);
    private System.Void AddOngoingTransfer(PDX.SDK.Contracts.Network.ITransferStatus transferStatus, PDX.SDK.Contracts.Internal.FlowData flowData);
    public virtual System.Void ClearDefaultHeaders();
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> DELETE(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> Download(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler, System.Threading.CancellationToken cancellationToken);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> GET(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public virtual System.Int32 GetTimeoutFileDownload();
    public virtual System.Int32 GetTimeoutFileUpload();
    public virtual System.Int32 GetTimeoutREST();
    public virtual System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> GetTransfers();
    protected System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
    protected System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> ParseResponse(System.Net.Http.HttpResponseMessage msg, PDX.SDK.Contracts.Internal.FlowData flowData);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PATCH(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    protected System.Net.Http.HttpRequestMessage PdxToNetRequest(System.String url, PDX.SDK.Network.Models.Request pdxRequest, System.Net.Http.HttpMethod restVerb, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> POST(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PUT(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public virtual System.Void RemoveOngoingTransfer(PDX.SDK.Contracts.Enums.ETransferType transferType, PDX.SDK.Contracts.Enums.ETransferServiceType transferServiceType, System.String transferId);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> REST(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public virtual System.Void SetPDXHeaders(System.String namespace, System.String gameVersion, System.String sdkVersion, System.String platform);
    public virtual System.Void SetTimeoutFileDownload(System.Int32 timeout);
    public virtual System.Void SetTimeoutFileUpload(System.Int32 timeout);
    public virtual System.Void SetTimeoutREST(System.Int32 timeout);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> Upload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler, System.Threading.CancellationToken cancellationToken);
}
```


## Fields

- `protected System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> ongoingTransfers`  

```csharp
protected System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> ongoingTransfers;
```

- `private System.TimeSpan timeoutREST`  

```csharp
private System.TimeSpan timeoutREST;
```

- `private System.TimeSpan timeoutFileDownload`  

```csharp
private System.TimeSpan timeoutFileDownload;
```

- `private System.TimeSpan timeoutFileUpload`  

```csharp
private System.TimeSpan timeoutFileUpload;
```

- `private System.Net.Http.HttpClient client`  

```csharp
private System.Net.Http.HttpClient client;
```

- `private readonly PDX.SDK.Contracts.Logging.ILogger _logger`  

```csharp
private readonly PDX.SDK.Contracts.Logging.ILogger _logger;
```

- `protected static System.Object ongoingTransfersLock`  

```csharp
protected static System.Object ongoingTransfersLock;
```


## Constructors

- `public HTTPDotNet(PDX.SDK.Contracts.Logging.ILogger logger)`  

```csharp
public HTTPDotNet(PDX.SDK.Contracts.Logging.ILogger logger);
```


## Methods

- `public virtual AddDefaultHeader(System.String name, System.String value) : System.Void`  

```csharp
public virtual System.Void AddDefaultHeader(System.String name, System.String value);
```

- `private AddOngoingTransfer(PDX.SDK.Contracts.Network.ITransferStatus transferStatus, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Void`  

```csharp
private System.Void AddOngoingTransfer(PDX.SDK.Contracts.Network.ITransferStatus transferStatus, PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `public virtual ClearDefaultHeaders() : System.Void`  

```csharp
public virtual System.Void ClearDefaultHeaders();
```

- `public virtual DELETE(System.String url, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> DELETE(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public virtual Download(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> Download(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler, System.Threading.CancellationToken cancellationToken);
```

- `public virtual GET(System.String url, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> GET(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public virtual GetTimeoutFileDownload() : System.Int32`  

```csharp
public virtual System.Int32 GetTimeoutFileDownload();
```

- `public virtual GetTimeoutFileUpload() : System.Int32`  

```csharp
public virtual System.Int32 GetTimeoutFileUpload();
```

- `public virtual GetTimeoutREST() : System.Int32`  

```csharp
public virtual System.Int32 GetTimeoutREST();
```

- `public virtual GetTransfers() : System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus>`  

```csharp
public virtual System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> GetTransfers();
```

- `protected Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel = L0_Info, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Void`  

```csharp
protected System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `protected ParseResponse(System.Net.Http.HttpResponseMessage msg, PDX.SDK.Contracts.Internal.FlowData flowData) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
protected System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> ParseResponse(System.Net.Http.HttpResponseMessage msg, PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `public virtual PATCH(System.String url, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PATCH(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `protected PdxToNetRequest(System.String url, PDX.SDK.Network.Models.Request pdxRequest, System.Net.Http.HttpMethod restVerb, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler = null) : System.Net.Http.HttpRequestMessage`  

```csharp
protected System.Net.Http.HttpRequestMessage PdxToNetRequest(System.String url, PDX.SDK.Network.Models.Request pdxRequest, System.Net.Http.HttpMethod restVerb, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler);
```

- `public virtual POST(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> POST(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public virtual PUT(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PUT(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public virtual RemoveOngoingTransfer(PDX.SDK.Contracts.Enums.ETransferType transferType, PDX.SDK.Contracts.Enums.ETransferServiceType transferServiceType, System.String transferId) : System.Void`  

```csharp
public virtual System.Void RemoveOngoingTransfer(PDX.SDK.Contracts.Enums.ETransferType transferType, PDX.SDK.Contracts.Enums.ETransferServiceType transferServiceType, System.String transferId);
```

- `public virtual REST(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> REST(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `public virtual SetPDXHeaders(System.String namespace, System.String gameVersion, System.String sdkVersion, System.String platform) : System.Void`  

```csharp
public virtual System.Void SetPDXHeaders(System.String namespace, System.String gameVersion, System.String sdkVersion, System.String platform);
```

- `public virtual SetTimeoutFileDownload(System.Int32 timeout) : System.Void`  

```csharp
public virtual System.Void SetTimeoutFileDownload(System.Int32 timeout);
```

- `public virtual SetTimeoutFileUpload(System.Int32 timeout) : System.Void`  

```csharp
public virtual System.Void SetTimeoutFileUpload(System.Int32 timeout);
```

- `public virtual SetTimeoutREST(System.Int32 timeout) : System.Void`  

```csharp
public virtual System.Void SetTimeoutREST(System.Int32 timeout);
```

- `public virtual Upload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> Upload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler, System.Threading.CancellationToken cancellationToken);
```


## Nested types

- `PDX.SDK.Network.DotNet.HTTPDotNet+<>c__DisplayClass10_0`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<>c__DisplayClass11_0`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<>c__DisplayClass17_0`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<>c__DisplayClass18_0`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<DELETE>d__15`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<Download>d__17`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<GET>d__12`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<PATCH>d__16`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<POST>d__14`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<PUT>d__13`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<ParseResponse>d__9`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<REST>d__11`  
- `PDX.SDK.Network.DotNet.HTTPDotNet+<Upload>d__18`  

