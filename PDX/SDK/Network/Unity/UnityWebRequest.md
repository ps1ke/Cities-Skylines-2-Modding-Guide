# PDX.SDK.Network.Unity.UnityWebRequest

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Network.Unity`  

**Type:** class public  

**Base:** `PDX.SDK.Network.HTTP`  

## Code

```csharp
public class UnityWebRequest : PDX.SDK.Network.HTTP
{
    private System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> ongoingTransfers;
    private System.TimeSpan timeoutREST;
    private System.TimeSpan timeoutFileDownload;
    private System.TimeSpan timeoutFileUpload;
    private System.Collections.Generic.List<PDX.SDK.Network.Models.Header> DefaultRequestHeaders;
    private readonly System.Threading.SynchronizationContext _unityMainThreadSyncCtx;
    private PDX.SDK.Contracts.Logging.ILogger _logger;
    private static System.Object ongoingTransfersLock;

    public UnityWebRequest(System.Threading.SynchronizationContext unityMainThreadSynchronizationContext, PDX.SDK.Contracts.Logging.ILogger logger);

    private System.Void <GenerateRequest>g__LogI|14_0(System.String msg, PDX.SDK.Contracts.Enums.LogLevel level, PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass14_0& );
    public virtual System.Void AddDefaultHeader(System.String name, System.String value);
    private System.Void AddOngoingTransfer(PDX.SDK.Contracts.Network.ITransferStatus transferStatus, PDX.SDK.Contracts.Internal.FlowData flowData);
    public virtual System.Void ClearDefaultHeaders();
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> DELETE(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> Download(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler, System.Threading.CancellationToken cancellationToken);
    private static UnityEngine.Networking.DownloadHandler GenerateDownloadHandler(PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler);
    private UnityEngine.Networking.UnityWebRequest GenerateRequest(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request pdxRequest, UnityEngine.Networking.DownloadHandler downloadHandler, UnityEngine.Networking.UploadHandler uploadHandler);
    private static UnityEngine.Networking.UploadHandler GenerateUploadFileHandler(System.String fileAbsoluteFilePath);
    private static UnityEngine.Networking.UploadHandler GenerateUploadHandler(PDX.SDK.Network.Models.Request request);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> GET(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    private System.String GetPdxPlatformString();
    public virtual System.Int32 GetTimeoutFileDownload();
    public virtual System.Int32 GetTimeoutFileUpload();
    public virtual System.Int32 GetTimeoutREST();
    public virtual System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> GetTransfers();
    private System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> InnerDownload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler, System.Threading.CancellationToken cancellationToken);
    private System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> InnerRest(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
    private System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> InnerUpload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler, System.Threading.CancellationToken cancellationToken);
    private System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
    private PDX.SDK.Network.Models.Response ParseResponse(UnityEngine.Networking.UnityWebRequest uwr, PDX.SDK.Contracts.Internal.FlowData flowData);
    private PDX.SDK.Network.Models.Response ParseUnityResponse(UnityEngine.Networking.UnityWebRequestAsyncOperation sendingProgress, UnityEngine.Networking.UnityWebRequest unityRequest, PDX.SDK.Contracts.Internal.FlowData flowData, PDX.SDK.Contracts.Util.IChunkHandler chunkHandler);
    public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PATCH(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
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

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> ongoingTransfers`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> ongoingTransfers;
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

- `private System.Collections.Generic.List<PDX.SDK.Network.Models.Header> DefaultRequestHeaders`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Network.Models.Header> DefaultRequestHeaders;
```

- `private readonly System.Threading.SynchronizationContext _unityMainThreadSyncCtx`  

```csharp
private readonly System.Threading.SynchronizationContext _unityMainThreadSyncCtx;
```

- `private PDX.SDK.Contracts.Logging.ILogger _logger`  

```csharp
private PDX.SDK.Contracts.Logging.ILogger _logger;
```

- `private static System.Object ongoingTransfersLock`  

```csharp
private static System.Object ongoingTransfersLock;
```


## Constructors

- `public UnityWebRequest(System.Threading.SynchronizationContext unityMainThreadSynchronizationContext, PDX.SDK.Contracts.Logging.ILogger logger)`  

```csharp
public UnityWebRequest(System.Threading.SynchronizationContext unityMainThreadSynchronizationContext, PDX.SDK.Contracts.Logging.ILogger logger);
```


## Methods

- `private <GenerateRequest>g__LogI|14_0(System.String msg, PDX.SDK.Contracts.Enums.LogLevel level, PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass14_0& ) : System.Void`  

```csharp
private System.Void <GenerateRequest>g__LogI|14_0(System.String msg, PDX.SDK.Contracts.Enums.LogLevel level, PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass14_0& );
```

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

- `private static GenerateDownloadHandler(PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler) : UnityEngine.Networking.DownloadHandler`  

```csharp
private static UnityEngine.Networking.DownloadHandler GenerateDownloadHandler(PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler);
```

- `private GenerateRequest(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request pdxRequest, UnityEngine.Networking.DownloadHandler downloadHandler = null, UnityEngine.Networking.UploadHandler uploadHandler = null) : UnityEngine.Networking.UnityWebRequest`  

```csharp
private UnityEngine.Networking.UnityWebRequest GenerateRequest(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request pdxRequest, UnityEngine.Networking.DownloadHandler downloadHandler, UnityEngine.Networking.UploadHandler uploadHandler);
```

- `private static GenerateUploadFileHandler(System.String fileAbsoluteFilePath) : UnityEngine.Networking.UploadHandler`  

```csharp
private static UnityEngine.Networking.UploadHandler GenerateUploadFileHandler(System.String fileAbsoluteFilePath);
```

- `private static GenerateUploadHandler(PDX.SDK.Network.Models.Request request) : UnityEngine.Networking.UploadHandler`  

```csharp
private static UnityEngine.Networking.UploadHandler GenerateUploadHandler(PDX.SDK.Network.Models.Request request);
```

- `public virtual GET(System.String url, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> GET(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `private GetPdxPlatformString() : System.String`  

```csharp
private System.String GetPdxPlatformString();
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

- `private InnerDownload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
private System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> InnerDownload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler downloadChunkHandler, System.Threading.CancellationToken cancellationToken);
```

- `private InnerRest(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
private System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> InnerRest(System.String url, PDX.SDK.Network.Enums.RESTMethod method, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
```

- `private InnerUpload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
private System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> InnerUpload(System.String url, PDX.SDK.Network.Models.Request request, PDX.SDK.Contracts.Util.IChunkHandler uploadChunkHandler, System.Threading.CancellationToken cancellationToken);
```

- `private Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel = L0_Info, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Void`  

```csharp
private System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `private ParseResponse(UnityEngine.Networking.UnityWebRequest uwr, PDX.SDK.Contracts.Internal.FlowData flowData) : PDX.SDK.Network.Models.Response`  

```csharp
private PDX.SDK.Network.Models.Response ParseResponse(UnityEngine.Networking.UnityWebRequest uwr, PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `private ParseUnityResponse(UnityEngine.Networking.UnityWebRequestAsyncOperation sendingProgress, UnityEngine.Networking.UnityWebRequest unityRequest, PDX.SDK.Contracts.Internal.FlowData flowData, PDX.SDK.Contracts.Util.IChunkHandler chunkHandler = null) : PDX.SDK.Network.Models.Response`  

```csharp
private PDX.SDK.Network.Models.Response ParseUnityResponse(UnityEngine.Networking.UnityWebRequestAsyncOperation sendingProgress, UnityEngine.Networking.UnityWebRequest unityRequest, PDX.SDK.Contracts.Internal.FlowData flowData, PDX.SDK.Contracts.Util.IChunkHandler chunkHandler);
```

- `public virtual PATCH(System.String url, PDX.SDK.Network.Models.Request request = null, System.Threading.CancellationToken cancellationToken = null) : System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response>`  

```csharp
public virtual System.Threading.Tasks.Task<PDX.SDK.Network.Models.Response> PATCH(System.String url, PDX.SDK.Network.Models.Request request, System.Threading.CancellationToken cancellationToken);
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

- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass10_0`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass11_0`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass14_0`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass19_0`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass19_1`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass25_0`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass25_1`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass26_0`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass26_1`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<>c__DisplayClass9_0`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<DELETE>d__23`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<GET>d__20`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<InnerDownload>d__25`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<InnerRest>d__19`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<InnerUpload>d__26`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<PATCH>d__24`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<POST>d__22`  
- `PDX.SDK.Network.Unity.UnityWebRequest+<PUT>d__21`  

