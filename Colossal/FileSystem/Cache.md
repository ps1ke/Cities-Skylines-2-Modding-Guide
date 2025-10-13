# Colossal.FileSystem.Cache

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Cache
{
    private System.Func<System.Boolean> m_AbortCheck;
    private System.String m_Dir;
    private System.Action<System.String, System.Exception> m_OnError;
    private System.Collections.Generic.Dictionary<System.String, System.String> m_Directories;
    private System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> m_Files;

    public Cache(System.String dir, System.Func<System.Boolean> abortCheck);

    private System.Boolean Add<T>(T item, System.Collections.Generic.Dictionary<System.String, T> list);
    public System.Void ErrorNotifier(System.Action<System.String, System.Exception> notifier);
    private System.Collections.Generic.List<Colossal.FileSystem.FileEntry> GetChanged(System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> original, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> items);
    private System.Collections.Generic.List<T> GetCreated<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items);
    private System.Collections.Generic.List<T> GetDeleted<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items);
    private Colossal.FileSystem.FileEntry GetFile(System.String file);
    private System.Void GetSnapshot(System.String directory, System.Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dirs, System.Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.FileSystem.FileEntry, Colossal.IO, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& files);
    private System.Boolean HandleChanged(System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> original, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> items, System.Action<System.String> action);
    private System.Boolean HandleCreated<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items, System.Action<System.String> action);
    private System.Boolean HandleDeleted<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items, System.Action<System.String> action);
    public System.Void Initialize();
    public System.Boolean IsDirectory(System.String dir);
    private System.Void Notify(System.String item, System.Action<System.String> action);
    public System.Boolean Refresh(Colossal.FileSystem.Change item);
    public System.Boolean RefreshFromDisk(System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted);
    private System.Boolean Remove<T>(System.String item, System.Collections.Generic.Dictionary<System.String, T> list);
    private System.Boolean Update(Colossal.FileSystem.FileEntry file, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> list);
}
```


## Fields

- `private System.Func<System.Boolean> m_AbortCheck`  

```csharp
private System.Func<System.Boolean> m_AbortCheck;
```

- `private System.String m_Dir`  

```csharp
private System.String m_Dir;
```

- `private System.Action<System.String, System.Exception> m_OnError`  

```csharp
private System.Action<System.String, System.Exception> m_OnError;
```

- `private System.Collections.Generic.Dictionary<System.String, System.String> m_Directories`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.String> m_Directories;
```

- `private System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> m_Files`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> m_Files;
```


## Constructors

- `public Cache(System.String dir, System.Func<System.Boolean> abortCheck)`  

```csharp
public Cache(System.String dir, System.Func<System.Boolean> abortCheck);
```


## Methods

- `private Add<T>(T item, System.Collections.Generic.Dictionary<System.String, T> list) : System.Boolean`  

```csharp
private System.Boolean Add<T>(T item, System.Collections.Generic.Dictionary<System.String, T> list);
```

- `public ErrorNotifier(System.Action<System.String, System.Exception> notifier) : System.Void`  

```csharp
public System.Void ErrorNotifier(System.Action<System.String, System.Exception> notifier);
```

- `private GetChanged(System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> original, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> items) : System.Collections.Generic.List<Colossal.FileSystem.FileEntry>`  

```csharp
private System.Collections.Generic.List<Colossal.FileSystem.FileEntry> GetChanged(System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> original, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> items);
```

- `private GetCreated<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items) : System.Collections.Generic.List<T>`  

```csharp
private System.Collections.Generic.List<T> GetCreated<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items);
```

- `private GetDeleted<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items) : System.Collections.Generic.List<T>`  

```csharp
private System.Collections.Generic.List<T> GetDeleted<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items);
```

- `private GetFile(System.String file) : Colossal.FileSystem.FileEntry`  

```csharp
private Colossal.FileSystem.FileEntry GetFile(System.String file);
```

- `private GetSnapshot(System.String directory, System.Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dirs, System.Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.FileSystem.FileEntry, Colossal.IO, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& files) : System.Void`  

```csharp
private System.Void GetSnapshot(System.String directory, System.Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dirs, System.Collections.Generic.Dictionary`2[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.FileSystem.FileEntry, Colossal.IO, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& files);
```

- `private HandleChanged(System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> original, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> items, System.Action<System.String> action) : System.Boolean`  

```csharp
private System.Boolean HandleChanged(System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> original, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> items, System.Action<System.String> action);
```

- `private HandleCreated<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items, System.Action<System.String> action) : System.Boolean`  

```csharp
private System.Boolean HandleCreated<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items, System.Action<System.String> action);
```

- `private HandleDeleted<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items, System.Action<System.String> action) : System.Boolean`  

```csharp
private System.Boolean HandleDeleted<T>(System.Collections.Generic.Dictionary<System.String, T> original, System.Collections.Generic.Dictionary<System.String, T> items, System.Action<System.String> action);
```

- `public Initialize() : System.Void`  

```csharp
public System.Void Initialize();
```

- `public IsDirectory(System.String dir) : System.Boolean`  

```csharp
public System.Boolean IsDirectory(System.String dir);
```

- `private Notify(System.String item, System.Action<System.String> action) : System.Void`  

```csharp
private System.Void Notify(System.String item, System.Action<System.String> action);
```

- `public Refresh(Colossal.FileSystem.Change item) : System.Boolean`  

```csharp
public System.Boolean Refresh(Colossal.FileSystem.Change item);
```

- `public RefreshFromDisk(System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted) : System.Boolean`  

```csharp
public System.Boolean RefreshFromDisk(System.Action<System.String> directoryCreated, System.Action<System.String> directoryDeleted, System.Action<System.String> fileCreated, System.Action<System.String> fileChanged, System.Action<System.String> fileDeleted);
```

- `private Remove<T>(System.String item, System.Collections.Generic.Dictionary<System.String, T> list) : System.Boolean`  

```csharp
private System.Boolean Remove<T>(System.String item, System.Collections.Generic.Dictionary<System.String, T> list);
```

- `private Update(Colossal.FileSystem.FileEntry file, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> list) : System.Boolean`  

```csharp
private System.Boolean Update(Colossal.FileSystem.FileEntry file, System.Collections.Generic.Dictionary<System.String, Colossal.FileSystem.FileEntry> list);
```


## Nested types

- `Colossal.FileSystem.Cache+<>c__DisplayClass13_0<T>`  
- `Colossal.FileSystem.Cache+<>c__DisplayClass14_0`  
- `Colossal.FileSystem.Cache+<>c__DisplayClass15_0<T>`  

