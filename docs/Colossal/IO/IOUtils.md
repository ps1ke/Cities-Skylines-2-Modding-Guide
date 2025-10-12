# Colossal.IO.IOUtils

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.IO`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Methods

- `internal static <CreatePackage>g__SetCompression|1_0(ICSharpCode.SharpZipLib.Zip.ZipOutputStream zip, ICSharpCode.SharpZipLib.Zip.ZipEntry entry, Colossal.IO.IOUtils+CompressionType compressionType) : System.Void`  
- `internal static <CreatePackage>g__WriteEntry|1_1(ICSharpCode.SharpZipLib.Zip.ZipOutputStream zip, Colossal.IO.IOUtils+CompressionType compressionType, System.String sourceFilePath, System.String filePath, System.DateTime lastWriteTime) : System.Void`  
- `public static CopyDirectory(System.String from, System.String to, System.Action<System.String> copyAction) : System.Boolean`  
- `public static CopyDirectory(System.String from, System.String to, System.Boolean preserveTimestamp = False, System.Collections.Generic.IReadOnlyCollection<System.String> excludePaths = null, System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> remapFolders = null, System.Action<System.String> copyAction = null) : System.Boolean`  
- `public static CopyStream(System.IO.Stream source, System.IO.Stream destination, System.Int32 bufferSize = 8192) : System.Void`  
- `public static CreatePackage(System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.String>> files, System.String outputPath, Colossal.IO.IOUtils+CompressionType compressionType = Best, System.Boolean preserveTimestamp = False) : System.Void`  
- `public static DeleteEmptyDirectories(System.String dest) : System.Void`  
- `public static EmptyFolder(System.String path) : System.Void`  
- `public static EmptyFolder(System.String path, System.Int32 maxDaysOld) : System.Void`  
- `public static EnsureDirectory(System.String path) : System.Boolean`  
- `public static GetStorageStatus(System.String path, System.Int64& total, System.Int64& available) : System.Void`  
- `public static IsDrivePath(System.String path) : System.Boolean`  
- `public static IsValidFolderName(System.String newName, System.Char[] additionalIllegalChars = null) : System.Boolean`  
- `public static ReadAllBytes(System.IO.Stream stream) : System.Byte[]`  
- `public static RenameFileWithoutChangingExtension(System.String originalPath, System.String newNameWithoutExtension) : System.String`  

## Nested types

- `Colossal.IO.IOUtils+CompressionType`  

