# PDX.SDK.Contracts.Util.IDiskIO

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Util`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IDiskIO
{
    public abstract System.Boolean CopyDirectory(System.String sourceDir, System.String targetDir, System.Boolean recursive, System.Boolean failIfExists);
    public abstract System.Boolean CopyFile(System.String sourceFile, System.String targetFile, System.Boolean failIfExists);
    public abstract System.Void CreateDirectory(System.String path);
    public abstract System.IO.Stream CreateFileStream(System.String path, System.IO.FileMode fileMode, System.IO.FileAccess fileAccess, System.IO.FileShare fileShare);
    public abstract System.Void Delete(System.String path);
    public abstract System.Void DeleteDirectory(System.String path, System.Boolean recursive);
    public abstract System.Collections.Generic.List<System.String> FindSubdirectoriesRecursive(System.String root, System.String path);
    public abstract System.String GetDirectoryName(System.String path);
    public abstract System.Int32 GetFileAttributes(System.String path);
    public abstract System.Collections.Generic.List<System.String> ListDirectories(System.String path);
    public abstract System.Collections.Generic.List<System.String> ListFiles(System.String path);
    public abstract System.Collections.Generic.List<System.String> ListFilesRecursive(System.String path, System.String searchPattern);
    public abstract System.Void Move(System.String sourcePath, System.String targetPath);
    public abstract System.Boolean PathExists(System.String path);
}
```


## Methods

- `public abstract CopyDirectory(System.String sourceDir, System.String targetDir, System.Boolean recursive = True, System.Boolean failIfExists = False) : System.Boolean`  

```csharp
public abstract System.Boolean CopyDirectory(System.String sourceDir, System.String targetDir, System.Boolean recursive, System.Boolean failIfExists);
```

- `public abstract CopyFile(System.String sourceFile, System.String targetFile, System.Boolean failIfExists = False) : System.Boolean`  

```csharp
public abstract System.Boolean CopyFile(System.String sourceFile, System.String targetFile, System.Boolean failIfExists);
```

- `public abstract CreateDirectory(System.String path) : System.Void`  

```csharp
public abstract System.Void CreateDirectory(System.String path);
```

- `public abstract CreateFileStream(System.String path, System.IO.FileMode fileMode, System.IO.FileAccess fileAccess, System.IO.FileShare fileShare) : System.IO.Stream`  

```csharp
public abstract System.IO.Stream CreateFileStream(System.String path, System.IO.FileMode fileMode, System.IO.FileAccess fileAccess, System.IO.FileShare fileShare);
```

- `public abstract Delete(System.String path) : System.Void`  

```csharp
public abstract System.Void Delete(System.String path);
```

- `public abstract DeleteDirectory(System.String path, System.Boolean recursive) : System.Void`  

```csharp
public abstract System.Void DeleteDirectory(System.String path, System.Boolean recursive);
```

- `public abstract FindSubdirectoriesRecursive(System.String root, System.String path) : System.Collections.Generic.List<System.String>`  

```csharp
public abstract System.Collections.Generic.List<System.String> FindSubdirectoriesRecursive(System.String root, System.String path);
```

- `public abstract GetDirectoryName(System.String path) : System.String`  

```csharp
public abstract System.String GetDirectoryName(System.String path);
```

- `public abstract GetFileAttributes(System.String path) : System.Int32`  

```csharp
public abstract System.Int32 GetFileAttributes(System.String path);
```

- `public abstract ListDirectories(System.String path) : System.Collections.Generic.List<System.String>`  

```csharp
public abstract System.Collections.Generic.List<System.String> ListDirectories(System.String path);
```

- `public abstract ListFiles(System.String path) : System.Collections.Generic.List<System.String>`  

```csharp
public abstract System.Collections.Generic.List<System.String> ListFiles(System.String path);
```

- `public abstract ListFilesRecursive(System.String path, System.String searchPattern = *) : System.Collections.Generic.List<System.String>`  

```csharp
public abstract System.Collections.Generic.List<System.String> ListFilesRecursive(System.String path, System.String searchPattern);
```

- `public abstract Move(System.String sourcePath, System.String targetPath) : System.Void`  

```csharp
public abstract System.Void Move(System.String sourcePath, System.String targetPath);
```

- `public abstract PathExists(System.String path) : System.Boolean`  

```csharp
public abstract System.Boolean PathExists(System.String path);
```


