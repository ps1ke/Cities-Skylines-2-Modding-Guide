# Colossal.IO.MultiPartFileStream

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.IO`  

**Type:** class public  

**Base:** `System.IO.Stream`  
**Implements:** `System.IDisposable`, `System.IAsyncDisposable`  

## Fields

- `private readonly System.String m_BaseFilePath`  
- `private readonly System.IO.FileMode m_Mode`  
- `private readonly System.IO.FileAccess m_Access`  
- `private readonly System.IO.FileShare m_Share`  
- `private readonly System.Int64 m_MaxPartSize`  
- `private System.Int64 m_Position`  
- `private System.Nullable<System.Int64> m_Length`  
- `private System.Boolean m_Disposed`  
- `private System.IO.FileStream m_CurrentStream`  
- `private readonly System.Action<System.Collections.Generic.IReadOnlyList<System.String>> m_DisposeCallback`  

## Properties

- `public System.Boolean CanRead { get }`  
- `public System.Boolean CanSeek { get }`  
- `public System.Boolean CanWrite { get }`  
- `public System.Int64 Position { get; set }`  
- `public System.Int64 Length { get }`  

## Constructors

- `public MultiPartFileStream(System.String baseFilePath, System.IO.FileMode mode, System.IO.FileAccess access, System.IO.FileShare share, System.Int64 maxPartSize, System.Action<System.Collections.Generic.IReadOnlyList<System.String>> disposeCallback)`  

## Methods

- `private CalculateTotalLength() : System.Int64`  
- `private CloseCurrentStream() : System.Void`  
- `protected virtual Dispose(System.Boolean disposing) : System.Void`  
- `private EnsureCurrentStream(System.Boolean forWriting) : System.Void`  
- `public virtual Flush() : System.Void`  
- `public static GetAllFilePaths(System.String baseFilePath) : System.Collections.Generic.IReadOnlyList<System.String>`  
- `public static GetLength(System.String baseFilePath) : System.Int64`  
- `private GetPartName(System.Int32 index) : System.String`  
- `private static GetPartName(System.String baseName, System.Int32 index) : System.String`  
- `public static OpenRead(System.String path, System.Int64 maxPartSize) : Colossal.IO.MultiPartFileStream`  
- `public static OpenReadWrite(System.String path, System.Int64 maxPartSize, System.Action<System.Collections.Generic.IReadOnlyList<System.String>> disposeCallback = null) : Colossal.IO.MultiPartFileStream`  
- `public virtual Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count) : System.Int32`  
- `public virtual Seek(System.Int64 offset, System.IO.SeekOrigin origin) : System.Int64`  
- `public virtual SetLength(System.Int64 value) : System.Void`  
- `public virtual Write(System.Byte[] buffer, System.Int32 offset, System.Int32 count) : System.Void`  

