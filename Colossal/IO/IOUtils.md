# Colossal.IO.IOUtils

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.IO`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class IOUtils
{
    internal static System.Void <CreatePackage>g__SetCompression|1_0(ICSharpCode.SharpZipLib.Zip.ZipOutputStream zip, ICSharpCode.SharpZipLib.Zip.ZipEntry entry, Colossal.IO.IOUtils+CompressionType compressionType);
    internal static System.Void <CreatePackage>g__WriteEntry|1_1(ICSharpCode.SharpZipLib.Zip.ZipOutputStream zip, Colossal.IO.IOUtils+CompressionType compressionType, System.String sourceFilePath, System.String filePath, System.DateTime lastWriteTime);
    public static System.Boolean CopyDirectory(System.String from, System.String to, System.Action<System.String> copyAction);
    public static System.Boolean CopyDirectory(System.String from, System.String to, System.Boolean preserveTimestamp, System.Collections.Generic.IReadOnlyCollection<System.String> excludePaths, System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> remapFolders, System.Action<System.String> copyAction);
    public static System.Void CopyStream(System.IO.Stream source, System.IO.Stream destination, System.Int32 bufferSize);
    public static System.Void CreatePackage(System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.String>> files, System.String outputPath, Colossal.IO.IOUtils+CompressionType compressionType, System.Boolean preserveTimestamp);
    public static System.Void DeleteEmptyDirectories(System.String dest);
    public static System.Void EmptyFolder(System.String path);
    public static System.Void EmptyFolder(System.String path, System.Int32 maxDaysOld);
    public static System.Boolean EnsureDirectory(System.String path);
    public static System.Void GetStorageStatus(System.String path, System.Int64& total, System.Int64& available);
    public static System.Boolean IsDrivePath(System.String path);
    public static System.Boolean IsValidFolderName(System.String newName, System.Char[] additionalIllegalChars);
    public static System.Byte[] ReadAllBytes(System.IO.Stream stream);
    public static System.String RenameFileWithoutChangingExtension(System.String originalPath, System.String newNameWithoutExtension);
}
```


## Methods

- `internal static <CreatePackage>g__SetCompression|1_0(ICSharpCode.SharpZipLib.Zip.ZipOutputStream zip, ICSharpCode.SharpZipLib.Zip.ZipEntry entry, Colossal.IO.IOUtils+CompressionType compressionType) : System.Void`  

```csharp
internal static System.Void <CreatePackage>g__SetCompression|1_0(ICSharpCode.SharpZipLib.Zip.ZipOutputStream zip, ICSharpCode.SharpZipLib.Zip.ZipEntry entry, Colossal.IO.IOUtils+CompressionType compressionType);
```

- `internal static <CreatePackage>g__WriteEntry|1_1(ICSharpCode.SharpZipLib.Zip.ZipOutputStream zip, Colossal.IO.IOUtils+CompressionType compressionType, System.String sourceFilePath, System.String filePath, System.DateTime lastWriteTime) : System.Void`  

```csharp
internal static System.Void <CreatePackage>g__WriteEntry|1_1(ICSharpCode.SharpZipLib.Zip.ZipOutputStream zip, Colossal.IO.IOUtils+CompressionType compressionType, System.String sourceFilePath, System.String filePath, System.DateTime lastWriteTime);
```

- `public static CopyDirectory(System.String from, System.String to, System.Action<System.String> copyAction) : System.Boolean`  

```csharp
public static System.Boolean CopyDirectory(System.String from, System.String to, System.Action<System.String> copyAction);
```

- `public static CopyDirectory(System.String from, System.String to, System.Boolean preserveTimestamp = False, System.Collections.Generic.IReadOnlyCollection<System.String> excludePaths = null, System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> remapFolders = null, System.Action<System.String> copyAction = null) : System.Boolean`  

```csharp
public static System.Boolean CopyDirectory(System.String from, System.String to, System.Boolean preserveTimestamp, System.Collections.Generic.IReadOnlyCollection<System.String> excludePaths, System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> remapFolders, System.Action<System.String> copyAction);
```

- `public static CopyStream(System.IO.Stream source, System.IO.Stream destination, System.Int32 bufferSize = 8192) : System.Void`  

```csharp
public static System.Void CopyStream(System.IO.Stream source, System.IO.Stream destination, System.Int32 bufferSize);
```

- `public static CreatePackage(System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.String>> files, System.String outputPath, Colossal.IO.IOUtils+CompressionType compressionType = Best, System.Boolean preserveTimestamp = False) : System.Void`  

```csharp
public static System.Void CreatePackage(System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.String>> files, System.String outputPath, Colossal.IO.IOUtils+CompressionType compressionType, System.Boolean preserveTimestamp);
```

- `public static DeleteEmptyDirectories(System.String dest) : System.Void`  

```csharp
public static System.Void DeleteEmptyDirectories(System.String dest);
```

- `public static EmptyFolder(System.String path) : System.Void`  

```csharp
public static System.Void EmptyFolder(System.String path);
```

- `public static EmptyFolder(System.String path, System.Int32 maxDaysOld) : System.Void`  

```csharp
public static System.Void EmptyFolder(System.String path, System.Int32 maxDaysOld);
```

- `public static EnsureDirectory(System.String path) : System.Boolean`  

```csharp
public static System.Boolean EnsureDirectory(System.String path);
```

- `public static GetStorageStatus(System.String path, System.Int64& total, System.Int64& available) : System.Void`  

```csharp
public static System.Void GetStorageStatus(System.String path, System.Int64& total, System.Int64& available);
```

- `public static IsDrivePath(System.String path) : System.Boolean`  

```csharp
public static System.Boolean IsDrivePath(System.String path);
```

- `public static IsValidFolderName(System.String newName, System.Char[] additionalIllegalChars = null) : System.Boolean`  

```csharp
public static System.Boolean IsValidFolderName(System.String newName, System.Char[] additionalIllegalChars);
```

- `public static ReadAllBytes(System.IO.Stream stream) : System.Byte[]`  

```csharp
public static System.Byte[] ReadAllBytes(System.IO.Stream stream);
```

- `public static RenameFileWithoutChangingExtension(System.String originalPath, System.String newNameWithoutExtension) : System.String`  

```csharp
public static System.String RenameFileWithoutChangingExtension(System.String originalPath, System.String newNameWithoutExtension);
```


## Nested types

- `Colossal.IO.IOUtils+CompressionType`  

