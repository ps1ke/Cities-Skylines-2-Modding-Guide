# Colossal.FileSystem.Cache

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Func<System.Boolean> m_AbortCheck`  
- `private System.String m_Dir`  
- `private System.Action<System.String, System.Exception> m_OnError`  
- `private System.Collections.Generic.Dictionary<System.String, System.String> m_Directories`  
- `private System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> m_Files`  

## Constructors

- `public Cache(System.String dir, System.Func<System.Boolean> abortCheck)`  

## Methods

- `private Add<T>(T item, System.Collections.Generic.Dictionary<System.String, T> list) : System.Boolean`  
- `public ErrorNotifier(System.Action<System.String, System.Exception> notifier) : System.Void`  
- `private GetChanged(System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> original, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> items) : System.Collections.Generic.List<Colossal.FileSystem.FileEntry>`  
- `private GetCreated<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items) : System.Collections.Generic.List<T>`  
- `private GetDeleted<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items) : System.Collections.Generic.List<T>`  
- `private GetFile(System.String file) : Colossal.FileSystem.FileEntry`  
- `private GetSnapshot(System.String directory, System.Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dirs, System.Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.FileSystem.FileEntry, Colossal.IO, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& files) : System.Void`  
- `private HandleChanged(System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> original, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> items, System.Action<System.String> action) : System.Boolean`  
- `private HandleCreated<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items, System.Action<System.String> action) : System.Boolean`  
- `private HandleDeleted<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items, System.Action<System.String> action) : System.Boolean`  
- `public Initialize() : System.Void`  
- `public IsDirectory(System.String dir) : System.Boolean`  
- `private Notify(System.String item, System.Action<System.String> action) : System.Void`  
- `public Refresh(Colossal.FileSystem.Change item) : System.Boolean`  
- `public RefreshFromDisk(System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted) : System.Boolean`  
- `private Remove<T>(System.String item, System.Collections.Generic.Dictionary<System.String, T> list) : System.Boolean`  
- `private Update(Colossal.FileSystem.FileEntry file, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> list) : System.Boolean`  

## Nested types

- `Colossal.FileSystem.Cache+<>c__DisplayClass13_0<T>`  
- `Colossal.FileSystem.Cache+<>c__DisplayClass14_0`  
- `Colossal.FileSystem.Cache+<>c__DisplayClass15_0<T>`  

