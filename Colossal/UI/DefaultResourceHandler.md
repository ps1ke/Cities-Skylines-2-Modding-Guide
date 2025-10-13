# Colossal.UI.DefaultResourceHandler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.ResourceHandler`  
**Implements:** `cohtml.Net.IResourceHandler`, `System.IDisposable`, `Colossal.UI.IFontSourceHandler`  

## Code

```csharp
public class DefaultResourceHandler : cohtml.Net.ResourceHandler, cohtml.Net.IResourceHandler, System.IDisposable, Colossal.UI.IFontSourceHandler
{
    private Colossal.UI.UserImagesManager <userImagesManager>k__BackingField;
    private System.Collections.Generic.List<Colossal.UI.DefaultResourceHandler+RequestData> m_PendingRequests;
    private System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.String, System.Int32>>> m_HostLocationsMap;
    private System.Collections.Generic.List<Colossal.UI.IFontRegistry> m_FontRegistries;
    private UnityEngine.MonoBehaviour <coroutineHost>k__BackingField;
    private readonly System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.Uri, System.Int32>>> <DatabaseHostLocationsMap>k__BackingField;
    protected static Colossal.Logging.ILog log;
    public static const System.String kCouiScheme;
    public static const System.String kCouiProtocol;
    private static const System.String kLiveScheme;
    public static const System.String kLiveProtocol;
    private static const System.String ResourceHandler;
    private static const System.String SharedImagesPath;
    public static const System.String kPreloadedHost;
    public static const System.String kUriSchemeData;
    private static const System.String kFontsStr;
    private static const System.String kPreloadedFontsStr;

    public Colossal.UI.UserImagesManager userImagesManager { get; set; }
    public UnityEngine.MonoBehaviour coroutineHost { get; set; }
    internal System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.String, System.Int32>>> HostLocationsMap { internal get; internal set; }
    internal System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.Uri, System.Int32>>> DatabaseHostLocationsMap { internal get; }

    public DefaultResourceHandler();

    protected System.Void AbortAllPendingRequests();
    protected System.Void AddPendingRequest(Colossal.UI.DefaultResourceHandler+RequestData requestData);
    protected System.Void CheckForFailedRequest(Colossal.UI.DefaultResourceHandler+RequestData requestData);
    private System.Void Colossal.UI.IFontSourceHandler.AddFontRegistry(Colossal.UI.IFontRegistry registry);
    private System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>> Colossal.UI.IFontSourceHandler.EnumerateFonts();
    public virtual System.Void Dispose();
    private cohtml.Net.ISyncStreamReader GetFontRequest(System.String path);
    public virtual System.Void OnAbortResourceRequest(System.UInt32 id);
    public virtual System.Void OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response);
    public virtual System.Void OnResourceStreamRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceStreamResponse response);
    protected System.Void RemovePendingRequest(Colossal.UI.DefaultResourceHandler+RequestData requestToDelete);
    protected System.Void RequestAssetFromAssetDatabase(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData);
    protected System.Void RequestAssetFromLive(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData);
    private System.Collections.IEnumerator RequestAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData, System.String path);
    protected System.Collections.IEnumerator RequestResourceAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData);
    private System.Collections.IEnumerator RequestResourceStreamAsync(Colossal.UI.DefaultResourceHandler+ResourceStreamRequestData requestData);
    private System.Collections.IEnumerator RequestStreamAsync(Colossal.UI.DefaultResourceHandler+ResourceStreamRequestData requestData, System.String path);
    protected System.Void RespondWithSuccess(Colossal.UI.DefaultResourceHandler+RequestData requestData);
    protected System.Collections.IEnumerator TryPreloadedResourceRequestAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData);
}
```


## Fields

- `private Colossal.UI.UserImagesManager <userImagesManager>k__BackingField`  

```csharp
private Colossal.UI.UserImagesManager <userImagesManager>k__BackingField;
```

- `private System.Collections.Generic.List<Colossal.UI.DefaultResourceHandler+RequestData> m_PendingRequests`  

```csharp
private System.Collections.Generic.List<Colossal.UI.DefaultResourceHandler+RequestData> m_PendingRequests;
```

- `private System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.String, System.Int32>>> m_HostLocationsMap`  

```csharp
private System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.String, System.Int32>>> m_HostLocationsMap;
```

- `private System.Collections.Generic.List<Colossal.UI.IFontRegistry> m_FontRegistries`  

```csharp
private System.Collections.Generic.List<Colossal.UI.IFontRegistry> m_FontRegistries;
```

- `private UnityEngine.MonoBehaviour <coroutineHost>k__BackingField`  

```csharp
private UnityEngine.MonoBehaviour <coroutineHost>k__BackingField;
```

- `private readonly System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.Uri, System.Int32>>> <DatabaseHostLocationsMap>k__BackingField`  

```csharp
private readonly System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.Uri, System.Int32>>> <DatabaseHostLocationsMap>k__BackingField;
```

- `protected static Colossal.Logging.ILog log`  

```csharp
protected static Colossal.Logging.ILog log;
```

- `public static const System.String kCouiScheme`  

```csharp
public static const System.String kCouiScheme;
```

- `public static const System.String kCouiProtocol`  

```csharp
public static const System.String kCouiProtocol;
```

- `private static const System.String kLiveScheme`  

```csharp
private static const System.String kLiveScheme;
```

- `public static const System.String kLiveProtocol`  

```csharp
public static const System.String kLiveProtocol;
```

- `private static const System.String ResourceHandler`  

```csharp
private static const System.String ResourceHandler;
```

- `private static const System.String SharedImagesPath`  

```csharp
private static const System.String SharedImagesPath;
```

- `public static const System.String kPreloadedHost`  

```csharp
public static const System.String kPreloadedHost;
```

- `public static const System.String kUriSchemeData`  

```csharp
public static const System.String kUriSchemeData;
```

- `private static const System.String kFontsStr`  

```csharp
private static const System.String kFontsStr;
```

- `private static const System.String kPreloadedFontsStr`  

```csharp
private static const System.String kPreloadedFontsStr;
```


## Properties

- `public Colossal.UI.UserImagesManager userImagesManager { get; set }`  

```csharp
public Colossal.UI.UserImagesManager userImagesManager { get; set; }
```

- `public UnityEngine.MonoBehaviour coroutineHost { get; set }`  

```csharp
public UnityEngine.MonoBehaviour coroutineHost { get; set; }
```

- `internal System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.String, System.Int32>>> HostLocationsMap { internal get; internal set }`  

```csharp
internal System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.String, System.Int32>>> HostLocationsMap { internal get; internal set; }
```

- `internal System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.Uri, System.Int32>>> DatabaseHostLocationsMap { internal get }`  

```csharp
internal System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.Uri, System.Int32>>> DatabaseHostLocationsMap { internal get; }
```


## Constructors

- `public DefaultResourceHandler()`  

```csharp
public DefaultResourceHandler();
```


## Methods

- `protected AbortAllPendingRequests() : System.Void`  

```csharp
protected System.Void AbortAllPendingRequests();
```

- `protected AddPendingRequest(Colossal.UI.DefaultResourceHandler+RequestData requestData) : System.Void`  

```csharp
protected System.Void AddPendingRequest(Colossal.UI.DefaultResourceHandler+RequestData requestData);
```

- `protected CheckForFailedRequest(Colossal.UI.DefaultResourceHandler+RequestData requestData) : System.Void`  

```csharp
protected System.Void CheckForFailedRequest(Colossal.UI.DefaultResourceHandler+RequestData requestData);
```

- `private Colossal.UI.IFontSourceHandler.AddFontRegistry(Colossal.UI.IFontRegistry registry) : System.Void`  

```csharp
private System.Void Colossal.UI.IFontSourceHandler.AddFontRegistry(Colossal.UI.IFontRegistry registry);
```

- `private Colossal.UI.IFontSourceHandler.EnumerateFonts() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>>`  

```csharp
private System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>> Colossal.UI.IFontSourceHandler.EnumerateFonts();
```

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `private GetFontRequest(System.String path) : cohtml.Net.ISyncStreamReader`  

```csharp
private cohtml.Net.ISyncStreamReader GetFontRequest(System.String path);
```

- `public virtual OnAbortResourceRequest(System.UInt32 id) : System.Void`  

```csharp
public virtual System.Void OnAbortResourceRequest(System.UInt32 id);
```

- `public virtual OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response) : System.Void`  

```csharp
public virtual System.Void OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response);
```

- `public virtual OnResourceStreamRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceStreamResponse response) : System.Void`  

```csharp
public virtual System.Void OnResourceStreamRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceStreamResponse response);
```

- `protected RemovePendingRequest(Colossal.UI.DefaultResourceHandler+RequestData requestToDelete) : System.Void`  

```csharp
protected System.Void RemovePendingRequest(Colossal.UI.DefaultResourceHandler+RequestData requestToDelete);
```

- `protected RequestAssetFromAssetDatabase(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData) : System.Void`  

```csharp
protected System.Void RequestAssetFromAssetDatabase(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData);
```

- `protected RequestAssetFromLive(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData) : System.Void`  

```csharp
protected System.Void RequestAssetFromLive(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData);
```

- `private RequestAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData, System.String path) : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator RequestAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData, System.String path);
```

- `protected RequestResourceAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData) : System.Collections.IEnumerator`  

```csharp
protected System.Collections.IEnumerator RequestResourceAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData);
```

- `private RequestResourceStreamAsync(Colossal.UI.DefaultResourceHandler+ResourceStreamRequestData requestData) : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator RequestResourceStreamAsync(Colossal.UI.DefaultResourceHandler+ResourceStreamRequestData requestData);
```

- `private RequestStreamAsync(Colossal.UI.DefaultResourceHandler+ResourceStreamRequestData requestData, System.String path) : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator RequestStreamAsync(Colossal.UI.DefaultResourceHandler+ResourceStreamRequestData requestData, System.String path);
```

- `protected RespondWithSuccess(Colossal.UI.DefaultResourceHandler+RequestData requestData) : System.Void`  

```csharp
protected System.Void RespondWithSuccess(Colossal.UI.DefaultResourceHandler+RequestData requestData);
```

- `protected TryPreloadedResourceRequestAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData) : System.Collections.IEnumerator`  

```csharp
protected System.Collections.IEnumerator TryPreloadedResourceRequestAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData);
```


## Nested types

- `Colossal.UI.DefaultResourceHandler+RequestData`  
- `Colossal.UI.DefaultResourceHandler+ResourceRequestData`  
- `Colossal.UI.DefaultResourceHandler+ResourceStreamRequestData`  
- `Colossal.UI.DefaultResourceHandler+<>c__DisplayClass32_0`  
- `Colossal.UI.DefaultResourceHandler+<Colossal-UI-IFontSourceHandler-EnumerateFonts>d__19`  
- `Colossal.UI.DefaultResourceHandler+<RequestAsync>d__39`  
- `Colossal.UI.DefaultResourceHandler+<RequestResourceAsync>d__36`  
- `Colossal.UI.DefaultResourceHandler+<RequestResourceStreamAsync>d__37`  
- `Colossal.UI.DefaultResourceHandler+<RequestStreamAsync>d__41`  
- `Colossal.UI.DefaultResourceHandler+<TryPreloadedResourceRequestAsync>d__38`  

