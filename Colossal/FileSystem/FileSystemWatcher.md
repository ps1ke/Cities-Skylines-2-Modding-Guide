# Colossal.FileSystem.FileSystemWatcher

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class FileSystemWatcher
{
    private System.String m_WatchPath;
    private System.Boolean m_IncludeSubDirectories;
    private System.String m_Filter;
    private Colossal.FileSystem.Cache m_Cache;
    private System.IO.FileSystemWatcher m_Watcher;
    private System.Action<System.String> m_FileCreated;
    private System.Action<System.String> m_FileChanged;
    private System.Action<System.String> m_FileDeleted;
    private System.Action<System.String> m_DirectoryCreated;
    private System.Action<System.String> m_DirectoryDeleted;
    private System.Action<System.String> m_OnError;
    private System.Boolean <needsRestart>k__BackingField;

    public System.Boolean needsRestart { get; private set; }
    public System.Boolean isAlive { get; }

    public FileSystemWatcher(System.String watchPath, System.Boolean includeSubDirectories, System.String filter, System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted, System.Action<System.String> onError, Colossal.FileSystem.Cache cache);

    public System.Void Start();
    private System.Void StartListener();
    public System.Void Stop();
    private System.Void WatcherChangeHandler(System.Object sender, System.IO.FileSystemEventArgs e);
    private System.Void WatcherErrorHandler(System.Object sender, System.IO.ErrorEventArgs e);
    private System.Void WatcherRenamedHandler(System.Object sender, System.IO.RenamedEventArgs e);
}
```


## Fields

- `private System.String m_WatchPath`  

```csharp
private System.String m_WatchPath;
```

- `private System.Boolean m_IncludeSubDirectories`  

```csharp
private System.Boolean m_IncludeSubDirectories;
```

- `private System.String m_Filter`  

```csharp
private System.String m_Filter;
```

- `private Colossal.FileSystem.Cache m_Cache`  

```csharp
private Colossal.FileSystem.Cache m_Cache;
```

- `private System.IO.FileSystemWatcher m_Watcher`  

```csharp
private System.IO.FileSystemWatcher m_Watcher;
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

- `private System.Action<System.String> m_OnError`  

```csharp
private System.Action<System.String> m_OnError;
```

- `private System.Boolean <needsRestart>k__BackingField`  

```csharp
private System.Boolean <needsRestart>k__BackingField;
```


## Properties

- `public System.Boolean needsRestart { get; private set }`  

```csharp
public System.Boolean needsRestart { get; private set; }
```

- `public System.Boolean isAlive { get }`  

```csharp
public System.Boolean isAlive { get; }
```


## Constructors

- `public FileSystemWatcher(System.String watchPath, System.Boolean includeSubDirectories, System.String filter, System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted, System.Action<System.String> onError, Colossal.FileSystem.Cache cache)`  

```csharp
public FileSystemWatcher(System.String watchPath, System.Boolean includeSubDirectories, System.String filter, System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted, System.Action<System.String> onError, Colossal.FileSystem.Cache cache);
```


## Methods

- `public Start() : System.Void`  

```csharp
public System.Void Start();
```

- `private StartListener() : System.Void`  

```csharp
private System.Void StartListener();
```

- `public Stop() : System.Void`  

```csharp
public System.Void Stop();
```

- `private WatcherChangeHandler(System.Object sender, System.IO.FileSystemEventArgs e) : System.Void`  

```csharp
private System.Void WatcherChangeHandler(System.Object sender, System.IO.FileSystemEventArgs e);
```

- `private WatcherErrorHandler(System.Object sender, System.IO.ErrorEventArgs e) : System.Void`  

```csharp
private System.Void WatcherErrorHandler(System.Object sender, System.IO.ErrorEventArgs e);
```

- `private WatcherRenamedHandler(System.Object sender, System.IO.RenamedEventArgs e) : System.Void`  

```csharp
private System.Void WatcherRenamedHandler(System.Object sender, System.IO.RenamedEventArgs e);
```


