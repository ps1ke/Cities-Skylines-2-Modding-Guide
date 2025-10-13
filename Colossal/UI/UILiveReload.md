# Colossal.UI.UILiveReload

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.ILiveReload`, `System.IDisposable`  

## Code

```csharp
public class UILiveReload : Colossal.UI.ILiveReload, System.IDisposable
{
    private Colossal.UI.UIView m_Target;
    private System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.Watcher> m_Watchers;
    private System.String m_MainPath;
    private System.String m_DevServerActivePath;
    private System.String m_DevUrl;
    private System.Boolean m_BindingsRegistered;
    private System.Boolean m_DevMode;
    private System.Boolean m_WebsocketConnected;
    private Colossal.UI.UILiveReload+ReloadType m_Reloading;
    private System.Single m_Delay;
    private System.String m_CurrentUrl;
    private static Colossal.Logging.ILog log;
    private static const System.String kDevServerActive;
    private static const System.Single kPageReloadDelay;
    private static const System.Single kMediaReloadDelay;
    private static const System.Single kWebsocketConnectDelay;

    public UILiveReload(Colossal.UI.UIView target);

    private System.Void Create(System.String url);
    public System.Void Dispose();
    private System.Boolean IsDevServerActive();
    private System.Boolean IsPageFileExtension(System.String extension);
    private System.Void OnChanged(System.String path);
    private System.Void OnCreated(System.String path);
    private System.Void OnHostLocationAdded(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch);
    private System.Void OnHostLocationRemoved(System.String uri, System.String path);
    private System.Void OnReadyForBindings();
    private System.Void OnWebpackClose();
    private System.Void OnWebpackOk();
    public System.Void StartWatch(System.String url);
    private System.Void TryDeleteDevServerActiveFile();
    public System.Void Update();
    private System.Void UpdateURL(System.String url);
}
```


## Fields

- `private Colossal.UI.UIView m_Target`  

```csharp
private Colossal.UI.UIView m_Target;
```

- `private System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.Watcher> m_Watchers`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.Watcher> m_Watchers;
```

- `private System.String m_MainPath`  

```csharp
private System.String m_MainPath;
```

- `private System.String m_DevServerActivePath`  

```csharp
private System.String m_DevServerActivePath;
```

- `private System.String m_DevUrl`  

```csharp
private System.String m_DevUrl;
```

- `private System.Boolean m_BindingsRegistered`  

```csharp
private System.Boolean m_BindingsRegistered;
```

- `private System.Boolean m_DevMode`  

```csharp
private System.Boolean m_DevMode;
```

- `private System.Boolean m_WebsocketConnected`  

```csharp
private System.Boolean m_WebsocketConnected;
```

- `private Colossal.UI.UILiveReload+ReloadType m_Reloading`  

```csharp
private Colossal.UI.UILiveReload+ReloadType m_Reloading;
```

- `private System.Single m_Delay`  

```csharp
private System.Single m_Delay;
```

- `private System.String m_CurrentUrl`  

```csharp
private System.String m_CurrentUrl;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static const System.String kDevServerActive`  

```csharp
private static const System.String kDevServerActive;
```

- `private static const System.Single kPageReloadDelay`  

```csharp
private static const System.Single kPageReloadDelay;
```

- `private static const System.Single kMediaReloadDelay`  

```csharp
private static const System.Single kMediaReloadDelay;
```

- `private static const System.Single kWebsocketConnectDelay`  

```csharp
private static const System.Single kWebsocketConnectDelay;
```


## Constructors

- `public UILiveReload(Colossal.UI.UIView target)`  

```csharp
public UILiveReload(Colossal.UI.UIView target);
```


## Methods

- `private Create(System.String url) : System.Void`  

```csharp
private System.Void Create(System.String url);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private IsDevServerActive() : System.Boolean`  

```csharp
private System.Boolean IsDevServerActive();
```

- `private IsPageFileExtension(System.String extension) : System.Boolean`  

```csharp
private System.Boolean IsPageFileExtension(System.String extension);
```

- `private OnChanged(System.String path) : System.Void`  

```csharp
private System.Void OnChanged(System.String path);
```

- `private OnCreated(System.String path) : System.Void`  

```csharp
private System.Void OnCreated(System.String path);
```

- `private OnHostLocationAdded(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch) : System.Void`  

```csharp
private System.Void OnHostLocationAdded(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch);
```

- `private OnHostLocationRemoved(System.String uri, System.String path) : System.Void`  

```csharp
private System.Void OnHostLocationRemoved(System.String uri, System.String path);
```

- `private OnReadyForBindings() : System.Void`  

```csharp
private System.Void OnReadyForBindings();
```

- `private OnWebpackClose() : System.Void`  

```csharp
private System.Void OnWebpackClose();
```

- `private OnWebpackOk() : System.Void`  

```csharp
private System.Void OnWebpackOk();
```

- `public StartWatch(System.String url) : System.Void`  

```csharp
public System.Void StartWatch(System.String url);
```

- `private TryDeleteDevServerActiveFile() : System.Void`  

```csharp
private System.Void TryDeleteDevServerActiveFile();
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `private UpdateURL(System.String url) : System.Void`  

```csharp
private System.Void UpdateURL(System.String url);
```


## Nested types

- `Colossal.UI.UILiveReload+ReloadType`  
- `Colossal.UI.UILiveReload+<>c`  

