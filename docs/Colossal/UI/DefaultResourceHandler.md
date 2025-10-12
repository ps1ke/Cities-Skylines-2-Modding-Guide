# Colossal.UI.DefaultResourceHandler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.ResourceHandler`  
**Implements:** `cohtml.Net.IResourceHandler`, `System.IDisposable`, `Colossal.UI.IFontSourceHandler`  

## Fields

- `private Colossal.UI.UserImagesManager <userImagesManager>k__BackingField`  
- `private System.Collections.Generic.List<Colossal.UI.DefaultResourceHandler+RequestData> m_PendingRequests`  
- `private System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.String, System.Int32>>> m_HostLocationsMap`  
- `private System.Collections.Generic.List<Colossal.UI.IFontRegistry> m_FontRegistries`  
- `private UnityEngine.MonoBehaviour <coroutineHost>k__BackingField`  
- `private readonly System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.Uri, System.Int32>>> <DatabaseHostLocationsMap>k__BackingField`  
- `protected static Colossal.Logging.ILog log`  
- `public static const System.String kCouiScheme`  
- `public static const System.String kCouiProtocol`  
- `private static const System.String kLiveScheme`  
- `public static const System.String kLiveProtocol`  
- `private static const System.String ResourceHandler`  
- `private static const System.String SharedImagesPath`  
- `public static const System.String kPreloadedHost`  
- `public static const System.String kUriSchemeData`  
- `private static const System.String kFontsStr`  
- `private static const System.String kPreloadedFontsStr`  

## Properties

- `public Colossal.UI.UserImagesManager userImagesManager { get; set }`  
- `public UnityEngine.MonoBehaviour coroutineHost { get; set }`  
- `internal System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.String, System.Int32>>> HostLocationsMap { internal get; internal set }`  
- `internal System.Collections.Generic.IDictionary<System.String, System.Collections.Generic.List<System.ValueTuple<System.Uri, System.Int32>>> DatabaseHostLocationsMap { internal get }`  

## Constructors

- `public DefaultResourceHandler()`  

## Methods

- `protected AbortAllPendingRequests() : System.Void`  
- `protected AddPendingRequest(Colossal.UI.DefaultResourceHandler+RequestData requestData) : System.Void`  
- `protected CheckForFailedRequest(Colossal.UI.DefaultResourceHandler+RequestData requestData) : System.Void`  
- `private Colossal.UI.IFontSourceHandler.AddFontRegistry(Colossal.UI.IFontRegistry registry) : System.Void`  
- `private Colossal.UI.IFontSourceHandler.EnumerateFonts() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>>`  
- `public virtual Dispose() : System.Void`  
- `private GetFontRequest(System.String path) : cohtml.Net.ISyncStreamReader`  
- `public virtual OnAbortResourceRequest(System.UInt32 id) : System.Void`  
- `public virtual OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response) : System.Void`  
- `public virtual OnResourceStreamRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceStreamResponse response) : System.Void`  
- `protected RemovePendingRequest(Colossal.UI.DefaultResourceHandler+RequestData requestToDelete) : System.Void`  
- `protected RequestAssetFromAssetDatabase(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData) : System.Void`  
- `protected RequestAssetFromLive(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData) : System.Void`  
- `private RequestAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData, System.String path) : System.Collections.IEnumerator`  
- `protected RequestResourceAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData) : System.Collections.IEnumerator`  
- `private RequestResourceStreamAsync(Colossal.UI.DefaultResourceHandler+ResourceStreamRequestData requestData) : System.Collections.IEnumerator`  
- `private RequestStreamAsync(Colossal.UI.DefaultResourceHandler+ResourceStreamRequestData requestData, System.String path) : System.Collections.IEnumerator`  
- `protected RespondWithSuccess(Colossal.UI.DefaultResourceHandler+RequestData requestData) : System.Void`  
- `protected TryPreloadedResourceRequestAsync(Colossal.UI.DefaultResourceHandler+ResourceRequestData requestData) : System.Collections.IEnumerator`  

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

