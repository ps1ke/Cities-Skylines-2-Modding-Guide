# Colossal.UI.UILiveReload

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.ILiveReload`, `System.IDisposable`  

## Fields

- `private Colossal.UI.UIView m_Target`  
- `private System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.Watcher> m_Watchers`  
- `private System.String m_MainPath`  
- `private System.String m_DevServerActivePath`  
- `private System.String m_DevUrl`  
- `private System.Boolean m_BindingsRegistered`  
- `private System.Boolean m_DevMode`  
- `private System.Boolean m_WebsocketConnected`  
- `private Colossal.UI.UILiveReload+ReloadType m_Reloading`  
- `private System.Single m_Delay`  
- `private System.String m_CurrentUrl`  
- `private static Colossal.Logging.ILog log`  
- `private static const System.String kDevServerActive`  
- `private static const System.Single kPageReloadDelay`  
- `private static const System.Single kMediaReloadDelay`  
- `private static const System.Single kWebsocketConnectDelay`  

## Constructors

- `public UILiveReload(Colossal.UI.UIView target)`  

## Methods

- `private Create(System.String url) : System.Void`  
- `public Dispose() : System.Void`  
- `private IsDevServerActive() : System.Boolean`  
- `private IsPageFileExtension(System.String extension) : System.Boolean`  
- `private OnChanged(System.String path) : System.Void`  
- `private OnCreated(System.String path) : System.Void`  
- `private OnHostLocationAdded(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch) : System.Void`  
- `private OnHostLocationRemoved(System.String uri, System.String path) : System.Void`  
- `private OnReadyForBindings() : System.Void`  
- `private OnWebpackClose() : System.Void`  
- `private OnWebpackOk() : System.Void`  
- `public StartWatch(System.String url) : System.Void`  
- `private TryDeleteDevServerActiveFile() : System.Void`  
- `public Update() : System.Void`  
- `private UpdateURL(System.String url) : System.Void`  

## Nested types

- `Colossal.UI.UILiveReload+ReloadType`  
- `Colossal.UI.UILiveReload+<>c`  

