# Colossal.FileSystem.Watcher

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class Watcher : System.IDisposable
{
    private Colossal.Logging.ILog log;
    private System.String m_Dir;
    private System.Boolean m_IncludeSubDirectories;
    private System.String m_Filter;
    private System.Boolean m_Exit;
    private Colossal.FileSystem.WatcherCapabilities m_Settings;
    private Colossal.FileSystem.Cache m_Cache;
    private Colossal.FileSystem.FileSystemWatcher m_FileSystemWatcher;
    private System.Action<System.String> m_FileCreated;
    private System.Action<System.String> m_FileChanged;
    private System.Action<System.String> m_FileDeleted;
    private System.Action<System.String> m_DirectoryCreated;
    private System.Action<System.String> m_DirectoryDeleted;
    private System.Action<System.String, System.Exception> m_OnError;
    private System.Threading.Thread m_Thread;
    private System.DateTime m_NextCatchup;

    public Colossal.FileSystem.WatcherCapabilities settings { get; }

    public Watcher(System.String dir, System.Boolean includeSubDirectories, System.String filter, System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted);

    private System.Boolean <.ctor>b__18_0();
    private System.Void ClearCatchup();
    public System.Void Dispose();
    public System.Void ErrorNotifier(System.Action<System.String, System.Exception> notifier);
    public System.Void ForceRefresh();
    private System.Int32 GetTimeSince(System.DateTime time);
    private System.Void Initialize();
    private System.Boolean NeedsToCatchUp();
    private System.Void Poll();
    private System.Void SetNextCatchup();
    public System.Void StartWatching(System.String filter);
    public System.Void StopWatching();
    private System.Boolean WaitingToCatchUp();
}
```


## Fields

- `private Colossal.Logging.ILog log`  

```csharp
private Colossal.Logging.ILog log;
```

- `private System.String m_Dir`  

```csharp
private System.String m_Dir;
```

- `private System.Boolean m_IncludeSubDirectories`  

```csharp
private System.Boolean m_IncludeSubDirectories;
```

- `private System.String m_Filter`  

```csharp
private System.String m_Filter;
```

- `private System.Boolean m_Exit`  

```csharp
private System.Boolean m_Exit;
```

- `private Colossal.FileSystem.WatcherCapabilities m_Settings`  

```csharp
private Colossal.FileSystem.WatcherCapabilities m_Settings;
```

- `private Colossal.FileSystem.Cache m_Cache`  

```csharp
private Colossal.FileSystem.Cache m_Cache;
```

- `private Colossal.FileSystem.FileSystemWatcher m_FileSystemWatcher`  

```csharp
private Colossal.FileSystem.FileSystemWatcher m_FileSystemWatcher;
```

- `private System.Action<System.String> m_FileCreated`  

```csharp
private System.Action<System.String> m_FileCreated;
```

- `private System.Action<System.String> m_FileChanged`  

```csharp
private System.Action<System.String> m_FileChanged;
```

- `private System.Action<System.String> m_FileDeleted`  

```csharp
private System.Action<System.String> m_FileDeleted;
```

- `private System.Action<System.String> m_DirectoryCreated`  

```csharp
private System.Action<System.String> m_DirectoryCreated;
```

- `private System.Action<System.String> m_DirectoryDeleted`  

```csharp
private System.Action<System.String> m_DirectoryDeleted;
```

- `private System.Action<System.String, System.Exception> m_OnError`  

```csharp
private System.Action<System.String, System.Exception> m_OnError;
```

- `private System.Threading.Thread m_Thread`  

```csharp
private System.Threading.Thread m_Thread;
```

- `private System.DateTime m_NextCatchup`  

```csharp
private System.DateTime m_NextCatchup;
```


## Properties

- `public Colossal.FileSystem.WatcherCapabilities settings { get }`  

```csharp
public Colossal.FileSystem.WatcherCapabilities settings { get; }
```


## Constructors

- `public Watcher(System.String dir, System.Boolean includeSubDirectories, System.String filter, System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted)`  

```csharp
public Watcher(System.String dir, System.Boolean includeSubDirectories, System.String filter, System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted);
```


## Methods

- `private <.ctor>b__18_0() : System.Boolean`  

```csharp
private System.Boolean <.ctor>b__18_0();
```

- `private ClearCatchup() : System.Void`  

```csharp
private System.Void ClearCatchup();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ErrorNotifier(System.Action<System.String, System.Exception> notifier) : System.Void`  

```csharp
public System.Void ErrorNotifier(System.Action<System.String, System.Exception> notifier);
```

- `public ForceRefresh() : System.Void`  

```csharp
public System.Void ForceRefresh();
```

- `private GetTimeSince(System.DateTime time) : System.Int32`  

```csharp
private System.Int32 GetTimeSince(System.DateTime time);
```

- `private Initialize() : System.Void`  

```csharp
private System.Void Initialize();
```

- `private NeedsToCatchUp() : System.Boolean`  

```csharp
private System.Boolean NeedsToCatchUp();
```

- `private Poll() : System.Void`  

```csharp
private System.Void Poll();
```

- `private SetNextCatchup() : System.Void`  

```csharp
private System.Void SetNextCatchup();
```

- `public StartWatching(System.String filter = null) : System.Void`  

```csharp
public System.Void StartWatching(System.String filter);
```

- `public StopWatching() : System.Void`  

```csharp
public System.Void StopWatching();
```

- `private WaitingToCatchUp() : System.Boolean`  

```csharp
private System.Boolean WaitingToCatchUp();
```


## Nested types

- `Colossal.FileSystem.Watcher+<>c__DisplayClass19_0`  

