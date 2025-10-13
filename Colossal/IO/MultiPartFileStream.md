# Colossal.IO.MultiPartFileStream

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.IO`  

**Type:** class public  

**Base:** `System.IO.Stream`  
**Implements:** `System.IDisposable`, `System.IAsyncDisposable`  

## Code

```csharp
public class MultiPartFileStream : System.IO.Stream, System.IDisposable, System.IAsyncDisposable
{
    private readonly System.String m_BaseFilePath;
    private readonly System.IO.FileMode m_Mode;
    private readonly System.IO.FileAccess m_Access;
    private readonly System.IO.FileShare m_Share;
    private readonly System.Int64 m_MaxPartSize;
    private System.Int64 m_Position;
    private System.Nullable<System.Int64> m_Length;
    private System.Boolean m_Disposed;
    private System.IO.FileStream m_CurrentStream;
    private readonly System.Action<System.Collections.Generic.IReadOnlyList<System.String>> m_DisposeCallback;

    public System.Boolean CanRead { get; }
    public System.Boolean CanSeek { get; }
    public System.Boolean CanWrite { get; }
    public System.Int64 Position { get; set; }
    public System.Int64 Length { get; }

    public MultiPartFileStream(System.String baseFilePath, System.IO.FileMode mode, System.IO.FileAccess access, System.IO.FileShare share, System.Int64 maxPartSize, System.Action<System.Collections.Generic.IReadOnlyList<System.String>> disposeCallback);

    private System.Int64 CalculateTotalLength();
    private System.Void CloseCurrentStream();
    protected virtual System.Void Dispose(System.Boolean disposing);
    private System.Void EnsureCurrentStream(System.Boolean forWriting);
    public virtual System.Void Flush();
    public static System.Collections.Generic.IReadOnlyList<System.String> GetAllFilePaths(System.String baseFilePath);
    public static System.Int64 GetLength(System.String baseFilePath);
    private System.String GetPartName(System.Int32 index);
    private static System.String GetPartName(System.String baseName, System.Int32 index);
    public static Colossal.IO.MultiPartFileStream OpenRead(System.String path, System.Int64 maxPartSize);
    public static Colossal.IO.MultiPartFileStream OpenReadWrite(System.String path, System.Int64 maxPartSize, System.Action<System.Collections.Generic.IReadOnlyList<System.String>> disposeCallback);
    public virtual System.Int32 Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count);
    public virtual System.Int64 Seek(System.Int64 offset, System.IO.SeekOrigin origin);
    public virtual System.Void SetLength(System.Int64 value);
    public virtual System.Void Write(System.Byte[] buffer, System.Int32 offset, System.Int32 count);
}
```


## Fields

- `private readonly System.String m_BaseFilePath`  

```csharp
private readonly System.String m_BaseFilePath;
```

- `private readonly System.IO.FileMode m_Mode`  

```csharp
private readonly System.IO.FileMode m_Mode;
```

- `private readonly System.IO.FileAccess m_Access`  

```csharp
private readonly System.IO.FileAccess m_Access;
```

- `private readonly System.IO.FileShare m_Share`  

```csharp
private readonly System.IO.FileShare m_Share;
```

- `private readonly System.Int64 m_MaxPartSize`  

```csharp
private readonly System.Int64 m_MaxPartSize;
```

- `private System.Int64 m_Position`  

```csharp
private System.Int64 m_Position;
```

- `private System.Nullable<System.Int64> m_Length`  

```csharp
private System.Nullable<System.Int64> m_Length;
```

- `private System.Boolean m_Disposed`  

```csharp
private System.Boolean m_Disposed;
```

- `private System.IO.FileStream m_CurrentStream`  

```csharp
private System.IO.FileStream m_CurrentStream;
```

- `private readonly System.Action<System.Collections.Generic.IReadOnlyList<System.String>> m_DisposeCallback`  

```csharp
private readonly System.Action<System.Collections.Generic.IReadOnlyList<System.String>> m_DisposeCallback;
```


## Properties

- `public System.Boolean CanRead { get }`  

```csharp
public System.Boolean CanRead { get; }
```

- `public System.Boolean CanSeek { get }`  

```csharp
public System.Boolean CanSeek { get; }
```

- `public System.Boolean CanWrite { get }`  

```csharp
public System.Boolean CanWrite { get; }
```

- `public System.Int64 Position { get; set }`  

```csharp
public System.Int64 Position { get; set; }
```

- `public System.Int64 Length { get }`  

```csharp
public System.Int64 Length { get; }
```


## Constructors

- `public MultiPartFileStream(System.String baseFilePath, System.IO.FileMode mode, System.IO.FileAccess access, System.IO.FileShare share, System.Int64 maxPartSize, System.Action<System.Collections.Generic.IReadOnlyList<System.String>> disposeCallback)`  

```csharp
public MultiPartFileStream(System.String baseFilePath, System.IO.FileMode mode, System.IO.FileAccess access, System.IO.FileShare share, System.Int64 maxPartSize, System.Action<System.Collections.Generic.IReadOnlyList<System.String>> disposeCallback);
```


## Methods

- `private CalculateTotalLength() : System.Int64`  

```csharp
private System.Int64 CalculateTotalLength();
```

- `private CloseCurrentStream() : System.Void`  

```csharp
private System.Void CloseCurrentStream();
```

- `protected virtual Dispose(System.Boolean disposing) : System.Void`  

```csharp
protected virtual System.Void Dispose(System.Boolean disposing);
```

- `private EnsureCurrentStream(System.Boolean forWriting) : System.Void`  

```csharp
private System.Void EnsureCurrentStream(System.Boolean forWriting);
```

- `public virtual Flush() : System.Void`  

```csharp
public virtual System.Void Flush();
```

- `public static GetAllFilePaths(System.String baseFilePath) : System.Collections.Generic.IReadOnlyList<System.String>`  

```csharp
public static System.Collections.Generic.IReadOnlyList<System.String> GetAllFilePaths(System.String baseFilePath);
```

- `public static GetLength(System.String baseFilePath) : System.Int64`  

```csharp
public static System.Int64 GetLength(System.String baseFilePath);
```

- `private GetPartName(System.Int32 index) : System.String`  

```csharp
private System.String GetPartName(System.Int32 index);
```

- `private static GetPartName(System.String baseName, System.Int32 index) : System.String`  

```csharp
private static System.String GetPartName(System.String baseName, System.Int32 index);
```

- `public static OpenRead(System.String path, System.Int64 maxPartSize) : Colossal.IO.MultiPartFileStream`  

```csharp
public static Colossal.IO.MultiPartFileStream OpenRead(System.String path, System.Int64 maxPartSize);
```

- `public static OpenReadWrite(System.String path, System.Int64 maxPartSize, System.Action<System.Collections.Generic.IReadOnlyList<System.String>> disposeCallback = null) : Colossal.IO.MultiPartFileStream`  

```csharp
public static Colossal.IO.MultiPartFileStream OpenReadWrite(System.String path, System.Int64 maxPartSize, System.Action<System.Collections.Generic.IReadOnlyList<System.String>> disposeCallback);
```

- `public virtual Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count) : System.Int32`  

```csharp
public virtual System.Int32 Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count);
```

- `public virtual Seek(System.Int64 offset, System.IO.SeekOrigin origin) : System.Int64`  

```csharp
public virtual System.Int64 Seek(System.Int64 offset, System.IO.SeekOrigin origin);
```

- `public virtual SetLength(System.Int64 value) : System.Void`  

```csharp
public virtual System.Void SetLength(System.Int64 value);
```

- `public virtual Write(System.Byte[] buffer, System.Int32 offset, System.Int32 count) : System.Void`  

```csharp
public virtual System.Void Write(System.Byte[] buffer, System.Int32 offset, System.Int32 count);
```


