# Colossal.UI.UISystem

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`, `Colossal.UI.IFontRegistry`  

## Fields

- `private Colossal.UI.UISystem+Settings m_Settings`  
- `private cohtml.Net.IUISystem m_NativeSystem`  
- `private System.Collections.Generic.List<Colossal.UI.UIView> m_Views`  
- `private UnityEngine.Rendering.CommandBuffer m_HdrpBuffer`  
- `private System.Collections.Generic.Dictionary<System.String, Colossal.UI.IFontStreamProvider> m_FontRegistry`  
- `private System.UInt32 <id>k__BackingField`  
- `private System.Boolean <enabled>k__BackingField`  
- `private Colossal.UI.UserImagesManager <userImagesManager>k__BackingField`  
- `private Colossal.UI.UISystem+OnHostLocationAdded onHostLocationAdded`  
- `private Colossal.UI.UISystem+OnHostLocationRemoved onHostLocationRemoved`  
- `private static Colossal.Logging.ILog log`  
- `private static readonly System.Collections.Generic.Comparer<System.ValueTuple<System.Uri, System.Int32>> kDatabasePriorityComparer`  
- `private static readonly System.Collections.Generic.Comparer<System.ValueTuple<System.String, System.Int32>> kPathPriorityComparer`  

## Properties

- `internal cohtml.Net.IUISystem nativeSystem { internal get }`  
- `public System.UInt32 id { get; private set }`  
- `public System.Collections.Generic.IReadOnlyList<Colossal.UI.UIView> UIViews { get }`  
- `public Colossal.UI.UIView defaultUIView { get }`  
- `public Colossal.UI.UIView activeUIView { get }`  
- `public System.Boolean enabled { get; set }`  
- `public Colossal.UI.UserImagesManager userImagesManager { get; private set }`  
- `public cohtml.Net.IResourceHandler resourceHandler { get }`  

## Constructors

- `private UISystem()`  
- `internal UISystem(Colossal.UI.UISystem+Settings settings, cohtml.Net.IUISystem nativeSystem)`  

## Methods

- `public AddDatabaseHostLocation(System.String hostName, System.Uri uri, System.Int32 priority = 0) : System.Void`  
- `public AddHostLocation(System.String hostName, System.String path, System.Boolean shouldWatch = True, System.Int32 priority = 0) : System.Void`  
- `public AddHostLocation(System.String hostName, System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.Int32>> paths, System.Boolean shouldWatch = True) : System.Void`  
- `public AddView(Colossal.UI.UIView view) : System.Void`  
- `public ClearCachedUnusedImages() : System.Void`  
- `public CreateView(System.String url, Colossal.UI.UIView+Settings settings, UnityEngine.Camera camera = null) : Colossal.UI.UIView`  
- `public DestroyView(Colossal.UI.UIView view) : System.Void`  
- `public Dispose() : System.Void`  
- `private OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext ctx, UnityEngine.Camera[] cameras) : System.Void`  
- `private OnEndFrame(UnityEngine.Rendering.ScriptableRenderContext ctx, UnityEngine.Camera[] cameras) : System.Void`  
- `private RegisterPreloadedFonts(Colossal.UI.IFontSourceHandler handler) : System.Void`  
- `public RemoveDatabaseHostLocation(System.String uri) : System.Void`  
- `public RemoveHostLocation(System.String uri) : System.Void`  
- `public RemoveHostLocation(System.String uri, System.String path) : System.Void`  
- `public RemoveView(Colossal.UI.UIView view) : System.Boolean`  
- `private SortViews() : System.Void`  
- `public TryGetFont(System.String fontName, Colossal.UI.IFontStreamProvider& fontStreamProvider) : System.Boolean`  
- `public Update() : System.Void`  

## Events

- `onHostLocationAdded` : `Colossal.UI.UISystem+OnHostLocationAdded`  
- `onHostLocationRemoved` : `Colossal.UI.UISystem+OnHostLocationRemoved`  

## Nested types

- `Colossal.UI.UISystem+Settings`  
- `Colossal.UI.UISystem+OnHostLocationAdded`  
- `Colossal.UI.UISystem+OnHostLocationRemoved`  
- `Colossal.UI.UISystem+<>c`  
- `Colossal.UI.UISystem+<>c__DisplayClass41_0`  
- `Colossal.UI.UISystem+<>c__DisplayClass43_0`  
- `Colossal.UI.UISystem+<>c__DisplayClass44_0`  
- `Colossal.UI.UISystem+<>c__DisplayClass46_0`  

