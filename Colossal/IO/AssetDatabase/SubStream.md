# Colossal.IO.AssetDatabase.SubStream

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.IO.Stream`  
**Implements:** `System.IDisposable`, `System.IAsyncDisposable`  

## Code

```csharp
public class SubStream : System.IO.Stream, System.IDisposable, System.IAsyncDisposable
{
    private readonly System.Int64 m_StartInSuperStream;
    private System.Int64 m_PositionInSuperStream;
    private readonly System.Int64 m_EndInSuperStream;
    private readonly System.IO.Stream m_SuperStream;
    private System.Boolean m_CanRead;
    private System.Boolean m_CanSeek;
    private System.Boolean m_IsDisposed;
    private System.Boolean m_LeaveOpen;

    public System.Int64 Length { get; }
    public System.Int64 Position { get; set; }
    public System.Boolean CanRead { get; }
    public System.Boolean CanSeek { get; }
    public System.Boolean CanWrite { get; }

    public SubStream(System.IO.Stream superStream, System.Int64 startPosition, System.Int64 size, System.Boolean leaveOpen);

    protected virtual System.Void Dispose(System.Boolean disposing);
    public virtual System.Void Flush();
    public virtual System.Int32 Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count);
    public System.Void SaveToFile(System.String path);
    public virtual System.Int64 Seek(System.Int64 offset, System.IO.SeekOrigin origin);
    public virtual System.Void SetLength(System.Int64 value);
    private System.Void ThrowIfCantRead();
    private System.Void ThrowIfCantSeek();
    private System.Void ThrowIfDisposed();
    public virtual System.Void Write(System.Byte[] buffer, System.Int32 offset, System.Int32 count);
}
```


## Fields

- `private readonly System.Int64 m_StartInSuperStream`  

```csharp
private readonly System.Int64 m_StartInSuperStream;
```

- `private System.Int64 m_PositionInSuperStream`  

```csharp
private System.Int64 m_PositionInSuperStream;
```

- `private readonly System.Int64 m_EndInSuperStream`  

```csharp
private readonly System.Int64 m_EndInSuperStream;
```

- `private readonly System.IO.Stream m_SuperStream`  

```csharp
private readonly System.IO.Stream m_SuperStream;
```

- `private System.Boolean m_CanRead`  

```csharp
private System.Boolean m_CanRead;
```

- `private System.Boolean m_CanSeek`  

```csharp
private System.Boolean m_CanSeek;
```

- `private System.Boolean m_IsDisposed`  

```csharp
private System.Boolean m_IsDisposed;
```

- `private System.Boolean m_LeaveOpen`  

```csharp
private System.Boolean m_LeaveOpen;
```


## Properties

- `public System.Int64 Length { get }`  

```csharp
public System.Int64 Length { get; }
```

- `public System.Int64 Position { get; set }`  

```csharp
public System.Int64 Position { get; set; }
```

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


## Constructors

- `public SubStream(System.IO.Stream superStream, System.Int64 startPosition, System.Int64 size, System.Boolean leaveOpen = False)`  

```csharp
public SubStream(System.IO.Stream superStream, System.Int64 startPosition, System.Int64 size, System.Boolean leaveOpen);
```


## Methods

- `protected virtual Dispose(System.Boolean disposing) : System.Void`  

```csharp
protected virtual System.Void Dispose(System.Boolean disposing);
```

- `public virtual Flush() : System.Void`  

```csharp
public virtual System.Void Flush();
```

- `public virtual Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count) : System.Int32`  

```csharp
public virtual System.Int32 Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count);
```

- `public SaveToFile(System.String path) : System.Void`  

```csharp
public System.Void SaveToFile(System.String path);
```

- `public virtual Seek(System.Int64 offset, System.IO.SeekOrigin origin) : System.Int64`  

```csharp
public virtual System.Int64 Seek(System.Int64 offset, System.IO.SeekOrigin origin);
```

- `public virtual SetLength(System.Int64 value) : System.Void`  

```csharp
public virtual System.Void SetLength(System.Int64 value);
```

- `private ThrowIfCantRead() : System.Void`  

```csharp
private System.Void ThrowIfCantRead();
```

- `private ThrowIfCantSeek() : System.Void`  

```csharp
private System.Void ThrowIfCantSeek();
```

- `private ThrowIfDisposed() : System.Void`  

```csharp
private System.Void ThrowIfDisposed();
```

- `public virtual Write(System.Byte[] buffer, System.Int32 offset, System.Int32 count) : System.Void`  

```csharp
public virtual System.Void Write(System.Byte[] buffer, System.Int32 offset, System.Int32 count);
```


