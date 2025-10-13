# Colossal.UI.Fatal.FatalResourceHandler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI.Fatal`  

**Type:** class public  

**Base:** `cohtml.Net.ResourceHandler`  
**Implements:** `cohtml.Net.IResourceHandler`, `System.IDisposable`, `Colossal.UI.IFontSourceHandler`  

## Code

```csharp
public class FatalResourceHandler : cohtml.Net.ResourceHandler, cohtml.Net.IResourceHandler, System.IDisposable, Colossal.UI.IFontSourceHandler
{
    private System.Collections.Generic.List<Colossal.UI.IFontRegistry> m_FontRegistries;
    private Colossal.UI.Fatal.ErrorPage m_ErrorPage;
    private static readonly System.String kPreloadedFontsStr;

    public System.String path { get; }
    public System.Boolean isPackaged { get; }

    public FatalResourceHandler(Colossal.UI.Fatal.ErrorPage page);

    private System.Void Colossal.UI.IFontSourceHandler.AddFontRegistry(Colossal.UI.IFontRegistry registry);
    private System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>> Colossal.UI.IFontSourceHandler.EnumerateFonts();
    private cohtml.Net.ISyncStreamReader GetStreamRequest(System.String path);
    public virtual System.Void OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response);
    public virtual System.Void OnResourceStreamRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceStreamResponse response);
    private static System.Collections.Specialized.NameValueCollection ParseQueryString(System.String query);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.UI.IFontRegistry> m_FontRegistries`  

```csharp
private System.Collections.Generic.List<Colossal.UI.IFontRegistry> m_FontRegistries;
```

- `private Colossal.UI.Fatal.ErrorPage m_ErrorPage`  

```csharp
private Colossal.UI.Fatal.ErrorPage m_ErrorPage;
```

- `private static readonly System.String kPreloadedFontsStr`  

```csharp
private static readonly System.String kPreloadedFontsStr;
```


## Properties

- `public System.String path { get }`  

```csharp
public System.String path { get; }
```

- `public System.Boolean isPackaged { get }`  

```csharp
public System.Boolean isPackaged { get; }
```


## Constructors

- `public FatalResourceHandler(Colossal.UI.Fatal.ErrorPage page)`  

```csharp
public FatalResourceHandler(Colossal.UI.Fatal.ErrorPage page);
```


## Methods

- `private Colossal.UI.IFontSourceHandler.AddFontRegistry(Colossal.UI.IFontRegistry registry) : System.Void`  

```csharp
private System.Void Colossal.UI.IFontSourceHandler.AddFontRegistry(Colossal.UI.IFontRegistry registry);
```

- `private Colossal.UI.IFontSourceHandler.EnumerateFonts() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>>`  

```csharp
private System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>> Colossal.UI.IFontSourceHandler.EnumerateFonts();
```

- `private GetStreamRequest(System.String path) : cohtml.Net.ISyncStreamReader`  

```csharp
private cohtml.Net.ISyncStreamReader GetStreamRequest(System.String path);
```

- `public virtual OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response) : System.Void`  

```csharp
public virtual System.Void OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response);
```

- `public virtual OnResourceStreamRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceStreamResponse response) : System.Void`  

```csharp
public virtual System.Void OnResourceStreamRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceStreamResponse response);
```

- `private static ParseQueryString(System.String query) : System.Collections.Specialized.NameValueCollection`  

```csharp
private static System.Collections.Specialized.NameValueCollection ParseQueryString(System.String query);
```


