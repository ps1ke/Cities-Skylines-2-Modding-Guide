# Colossal.UI.UISystem

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`, `Colossal.UI.IFontRegistry`  

## Code

```csharp
public class UISystem : System.IDisposable, Colossal.UI.IFontRegistry
{
    private Colossal.UI.UISystem+Settings m_Settings;
    private cohtml.Net.IUISystem m_NativeSystem;
    private System.Collections.Generic.List<Colossal.UI.UIView> m_Views;
    private UnityEngine.Rendering.CommandBuffer m_HdrpBuffer;
    private System.Collections.Generic.Dictionary<System.String, Colossal.UI.IFontStreamProvider> m_FontRegistry;
    private System.UInt32 <id>k__BackingField;
    private System.Boolean <enabled>k__BackingField;
    private Colossal.UI.UserImagesManager <userImagesManager>k__BackingField;
    private Colossal.UI.UISystem+OnHostLocationAdded onHostLocationAdded;
    private Colossal.UI.UISystem+OnHostLocationRemoved onHostLocationRemoved;
    private static Colossal.Logging.ILog log;
    private static readonly System.Collections.Generic.Comparer<System.ValueTuple<System.Uri, System.Int32>> kDatabasePriorityComparer;
    private static readonly System.Collections.Generic.Comparer<System.ValueTuple<System.String, System.Int32>> kPathPriorityComparer;

    internal cohtml.Net.IUISystem nativeSystem { internal get; }
    public System.UInt32 id { get; private set; }
    public System.Collections.Generic.IReadOnlyList<Colossal.UI.UIView> UIViews { get; }
    public Colossal.UI.UIView defaultUIView { get; }
    public Colossal.UI.UIView activeUIView { get; }
    public System.Boolean enabled { get; set; }
    public Colossal.UI.UserImagesManager userImagesManager { get; private set; }
    public cohtml.Net.IResourceHandler resourceHandler { get; }

    private UISystem();
    internal UISystem(Colossal.UI.UISystem+Settings settings, cohtml.Net.IUISystem nativeSystem);

    public System.Void AddDatabaseHostLocation(System.String hostName, System.Uri uri, System.Int32 priority);
    public System.Void AddHostLocation(System.String hostName, System.String path, System.Boolean shouldWatch, System.Int32 priority);
    public System.Void AddHostLocation(System.String hostName, System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.Int32>> paths, System.Boolean shouldWatch);
    public System.Void AddView(Colossal.UI.UIView view);
    public System.Void ClearCachedUnusedImages();
    public Colossal.UI.UIView CreateView(System.String url, Colossal.UI.UIView+Settings settings, UnityEngine.Camera camera);
    public System.Void DestroyView(Colossal.UI.UIView view);
    public System.Void Dispose();
    private System.Void OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext ctx, UnityEngine.Camera[] cameras);
    private System.Void OnEndFrame(UnityEngine.Rendering.ScriptableRenderContext ctx, UnityEngine.Camera[] cameras);
    private System.Void RegisterPreloadedFonts(Colossal.UI.IFontSourceHandler handler);
    public System.Void RemoveDatabaseHostLocation(System.String uri);
    public System.Void RemoveHostLocation(System.String uri);
    public System.Void RemoveHostLocation(System.String uri, System.String path);
    public System.Boolean RemoveView(Colossal.UI.UIView view);
    private System.Void SortViews();
    public System.Boolean TryGetFont(System.String fontName, Colossal.UI.IFontStreamProvider& fontStreamProvider);
    public System.Void Update();
}
```


## Fields

- `private Colossal.UI.UISystem+Settings m_Settings`  

```csharp
private Colossal.UI.UISystem+Settings m_Settings;
```

- `private cohtml.Net.IUISystem m_NativeSystem`  

```csharp
private cohtml.Net.IUISystem m_NativeSystem;
```

- `private System.Collections.Generic.List<Colossal.UI.UIView> m_Views`  

```csharp
private System.Collections.Generic.List<Colossal.UI.UIView> m_Views;
```

- `private UnityEngine.Rendering.CommandBuffer m_HdrpBuffer`  

```csharp
private UnityEngine.Rendering.CommandBuffer m_HdrpBuffer;
```

- `private System.Collections.Generic.Dictionary<System.String, Colossal.UI.IFontStreamProvider> m_FontRegistry`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Colossal.UI.IFontStreamProvider> m_FontRegistry;
```

- `private System.UInt32 <id>k__BackingField`  

```csharp
private System.UInt32 <id>k__BackingField;
```

- `private System.Boolean <enabled>k__BackingField`  

```csharp
private System.Boolean <enabled>k__BackingField;
```

- `private Colossal.UI.UserImagesManager <userImagesManager>k__BackingField`  

```csharp
private Colossal.UI.UserImagesManager <userImagesManager>k__BackingField;
```

- `private Colossal.UI.UISystem+OnHostLocationAdded onHostLocationAdded`  

```csharp
private Colossal.UI.UISystem+OnHostLocationAdded onHostLocationAdded;
```

- `private Colossal.UI.UISystem+OnHostLocationRemoved onHostLocationRemoved`  

```csharp
private Colossal.UI.UISystem+OnHostLocationRemoved onHostLocationRemoved;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static readonly System.Collections.Generic.Comparer<System.ValueTuple<System.Uri, System.Int32>> kDatabasePriorityComparer`  

```csharp
private static readonly System.Collections.Generic.Comparer<System.ValueTuple<System.Uri, System.Int32>> kDatabasePriorityComparer;
```

- `private static readonly System.Collections.Generic.Comparer<System.ValueTuple<System.String, System.Int32>> kPathPriorityComparer`  

```csharp
private static readonly System.Collections.Generic.Comparer<System.ValueTuple<System.String, System.Int32>> kPathPriorityComparer;
```


## Properties

- `internal cohtml.Net.IUISystem nativeSystem { internal get }`  

```csharp
internal cohtml.Net.IUISystem nativeSystem { internal get; }
```

- `public System.UInt32 id { get; private set }`  

```csharp
public System.UInt32 id { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyList<Colossal.UI.UIView> UIViews { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.UI.UIView> UIViews { get; }
```

- `public Colossal.UI.UIView defaultUIView { get }`  

```csharp
public Colossal.UI.UIView defaultUIView { get; }
```

- `public Colossal.UI.UIView activeUIView { get }`  

```csharp
public Colossal.UI.UIView activeUIView { get; }
```

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public Colossal.UI.UserImagesManager userImagesManager { get; private set }`  

```csharp
public Colossal.UI.UserImagesManager userImagesManager { get; private set; }
```

- `public cohtml.Net.IResourceHandler resourceHandler { get }`  

```csharp
public cohtml.Net.IResourceHandler resourceHandler { get; }
```


## Constructors

- `private UISystem()`  

```csharp
private UISystem();
```

- `internal UISystem(Colossal.UI.UISystem+Settings settings, cohtml.Net.IUISystem nativeSystem)`  

```csharp
internal UISystem(Colossal.UI.UISystem+Settings settings, cohtml.Net.IUISystem nativeSystem);
```


## Methods

- `public AddDatabaseHostLocation(System.String hostName, System.Uri uri, System.Int32 priority = 0) : System.Void`  

```csharp
public System.Void AddDatabaseHostLocation(System.String hostName, System.Uri uri, System.Int32 priority);
```

- `public AddHostLocation(System.String hostName, System.String path, System.Boolean shouldWatch = True, System.Int32 priority = 0) : System.Void`  

```csharp
public System.Void AddHostLocation(System.String hostName, System.String path, System.Boolean shouldWatch, System.Int32 priority);
```

- `public AddHostLocation(System.String hostName, System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.Int32>> paths, System.Boolean shouldWatch = True) : System.Void`  

```csharp
public System.Void AddHostLocation(System.String hostName, System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.Int32>> paths, System.Boolean shouldWatch);
```

- `public AddView(Colossal.UI.UIView view) : System.Void`  

```csharp
public System.Void AddView(Colossal.UI.UIView view);
```

- `public ClearCachedUnusedImages() : System.Void`  

```csharp
public System.Void ClearCachedUnusedImages();
```

- `public CreateView(System.String url, Colossal.UI.UIView+Settings settings, UnityEngine.Camera camera = null) : Colossal.UI.UIView`  

```csharp
public Colossal.UI.UIView CreateView(System.String url, Colossal.UI.UIView+Settings settings, UnityEngine.Camera camera);
```

- `public DestroyView(Colossal.UI.UIView view) : System.Void`  

```csharp
public System.Void DestroyView(Colossal.UI.UIView view);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext ctx, UnityEngine.Camera[] cameras) : System.Void`  

```csharp
private System.Void OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext ctx, UnityEngine.Camera[] cameras);
```

- `private OnEndFrame(UnityEngine.Rendering.ScriptableRenderContext ctx, UnityEngine.Camera[] cameras) : System.Void`  

```csharp
private System.Void OnEndFrame(UnityEngine.Rendering.ScriptableRenderContext ctx, UnityEngine.Camera[] cameras);
```

- `private RegisterPreloadedFonts(Colossal.UI.IFontSourceHandler handler) : System.Void`  

```csharp
private System.Void RegisterPreloadedFonts(Colossal.UI.IFontSourceHandler handler);
```

- `public RemoveDatabaseHostLocation(System.String uri) : System.Void`  

```csharp
public System.Void RemoveDatabaseHostLocation(System.String uri);
```

- `public RemoveHostLocation(System.String uri) : System.Void`  

```csharp
public System.Void RemoveHostLocation(System.String uri);
```

- `public RemoveHostLocation(System.String uri, System.String path) : System.Void`  

```csharp
public System.Void RemoveHostLocation(System.String uri, System.String path);
```

- `public RemoveView(Colossal.UI.UIView view) : System.Boolean`  

```csharp
public System.Boolean RemoveView(Colossal.UI.UIView view);
```

- `private SortViews() : System.Void`  

```csharp
private System.Void SortViews();
```

- `public TryGetFont(System.String fontName, Colossal.UI.IFontStreamProvider& fontStreamProvider) : System.Boolean`  

```csharp
public System.Boolean TryGetFont(System.String fontName, Colossal.UI.IFontStreamProvider& fontStreamProvider);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


## Events

- `onHostLocationAdded` : `Colossal.UI.UISystem+OnHostLocationAdded`  

```csharp
public event Colossal.UI.UISystem+OnHostLocationAdded onHostLocationAdded;
```

- `onHostLocationRemoved` : `Colossal.UI.UISystem+OnHostLocationRemoved`  

```csharp
public event Colossal.UI.UISystem+OnHostLocationRemoved onHostLocationRemoved;
```


## Nested types

- `Colossal.UI.UISystem+Settings`  
- `Colossal.UI.UISystem+OnHostLocationAdded`  
- `Colossal.UI.UISystem+OnHostLocationRemoved`  
- `Colossal.UI.UISystem+<>c`  
- `Colossal.UI.UISystem+<>c__DisplayClass41_0`  
- `Colossal.UI.UISystem+<>c__DisplayClass43_0`  
- `Colossal.UI.UISystem+<>c__DisplayClass44_0`  
- `Colossal.UI.UISystem+<>c__DisplayClass46_0`  

