# Colossal.FileSystem.FileSystemWatcher

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.String m_WatchPath`  
- `private System.Boolean m_IncludeSubDirectories`  
- `private System.String m_Filter`  
- `private Colossal.FileSystem.Cache m_Cache`  
- `private System.IO.FileSystemWatcher m_Watcher`  
- `private System.Action<System.String> m_FileCreated`  
- `private System.Action<System.String> m_FileChanged`  
- `private System.Action<System.String> m_FileDeleted`  
- `private System.Action<System.String> m_DirectoryCreated`  
- `private System.Action<System.String> m_DirectoryDeleted`  
- `private System.Action<System.String> m_OnError`  
- `private System.Boolean <needsRestart>k__BackingField`  

## Properties

- `public System.Boolean needsRestart { get; private set }`  
- `public System.Boolean isAlive { get }`  

## Constructors

- `public FileSystemWatcher(System.String watchPath, System.Boolean includeSubDirectories, System.String filter, System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted, System.Action<System.String> onError, Colossal.FileSystem.Cache cache)`  

## Methods

- `public Start() : System.Void`  
- `private StartListener() : System.Void`  
- `public Stop() : System.Void`  
- `private WatcherChangeHandler(System.Object sender, System.IO.FileSystemEventArgs e) : System.Void`  
- `private WatcherErrorHandler(System.Object sender, System.IO.ErrorEventArgs e) : System.Void`  
- `private WatcherRenamedHandler(System.Object sender, System.IO.RenamedEventArgs e) : System.Void`  

