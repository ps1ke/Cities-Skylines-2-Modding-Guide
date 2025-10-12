# Colossal.FileSystem.Watcher

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.Logging.ILog log`  
- `private System.String m_Dir`  
- `private System.Boolean m_IncludeSubDirectories`  
- `private System.String m_Filter`  
- `private System.Boolean m_Exit`  
- `private Colossal.FileSystem.WatcherCapabilities m_Settings`  
- `private Colossal.FileSystem.Cache m_Cache`  
- `private Colossal.FileSystem.FileSystemWatcher m_FileSystemWatcher`  
- `private System.Action<System.String> m_FileCreated`  
- `private System.Action<System.String> m_FileChanged`  
- `private System.Action<System.String> m_FileDeleted`  
- `private System.Action<System.String> m_DirectoryCreated`  
- `private System.Action<System.String> m_DirectoryDeleted`  
- `private System.Action<System.String, System.Exception> m_OnError`  
- `private System.Threading.Thread m_Thread`  
- `private System.DateTime m_NextCatchup`  

## Properties

- `public Colossal.FileSystem.WatcherCapabilities settings { get }`  

## Constructors

- `public Watcher(System.String dir, System.Boolean includeSubDirectories, System.String filter, System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted)`  

## Methods

- `private <.ctor>b__18_0() : System.Boolean`  
- `private ClearCatchup() : System.Void`  
- `public Dispose() : System.Void`  
- `public ErrorNotifier(System.Action<System.String, System.Exception> notifier) : System.Void`  
- `public ForceRefresh() : System.Void`  
- `private GetTimeSince(System.DateTime time) : System.Int32`  
- `private Initialize() : System.Void`  
- `private NeedsToCatchUp() : System.Boolean`  
- `private Poll() : System.Void`  
- `private SetNextCatchup() : System.Void`  
- `public StartWatching(System.String filter = null) : System.Void`  
- `public StopWatching() : System.Void`  
- `private WaitingToCatchUp() : System.Boolean`  

## Nested types

- `Colossal.FileSystem.Watcher+<>c__DisplayClass19_0`  

