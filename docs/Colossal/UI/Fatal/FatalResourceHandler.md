# Colossal.UI.Fatal.FatalResourceHandler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI.Fatal`  

**Type:** class public  

**Base:** `cohtml.Net.ResourceHandler`  
**Implements:** `cohtml.Net.IResourceHandler`, `System.IDisposable`, `Colossal.UI.IFontSourceHandler`  

## Fields

- `private System.Collections.Generic.List<Colossal.UI.IFontRegistry> m_FontRegistries`  
- `private Colossal.UI.Fatal.ErrorPage m_ErrorPage`  
- `private static readonly System.String kPreloadedFontsStr`  

## Properties

- `public System.String path { get }`  
- `public System.Boolean isPackaged { get }`  

## Constructors

- `public FatalResourceHandler(Colossal.UI.Fatal.ErrorPage page)`  

## Methods

- `private Colossal.UI.IFontSourceHandler.AddFontRegistry(Colossal.UI.IFontRegistry registry) : System.Void`  
- `private Colossal.UI.IFontSourceHandler.EnumerateFonts() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>>`  
- `private GetStreamRequest(System.String path) : cohtml.Net.ISyncStreamReader`  
- `public virtual OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response) : System.Void`  
- `public virtual OnResourceStreamRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceStreamResponse response) : System.Void`  
- `private static ParseQueryString(System.String query) : System.Collections.Specialized.NameValueCollection`  

