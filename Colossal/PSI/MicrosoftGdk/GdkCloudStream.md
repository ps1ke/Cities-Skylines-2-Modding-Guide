# Colossal.PSI.MicrosoftGdk.GdkCloudStream

**Assembly:** `Colossal.PSI.MicrosoftGdk`  
**Namespace:** `Colossal.PSI.MicrosoftGdk`  

**Type:** class public  

**Base:** `System.IO.Stream`  
**Implements:** `System.IDisposable`, `System.IAsyncDisposable`  

## Code

```csharp
public class GdkCloudStream : System.IO.Stream, System.IDisposable, System.IAsyncDisposable
{
    private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformSupport;
    private readonly System.Action m_DisposeCallback;
    private System.Int64 m_Position;
    private System.Int64 m_Length;
    private System.Byte[] m_Buffer;
    private System.String m_ContainerName;
    private System.String m_BlobName;
    private System.Int32 m_Part;
    private System.Boolean m_Disposed;
    private static Colossal.Logging.ILog log;
    private static const System.Int32 kMaxBufferSize;

    public System.Boolean CanRead { get; }
    public System.Boolean CanSeek { get; }
    public System.Boolean CanWrite { get; }
    public System.Int64 Length { get; }
    public System.Int64 Position { get; set; }

    private GdkCloudStream(System.String containerName, System.String blobName, Colossal.PSI.MicrosoftGdk.GdkPlatform platformSupport, System.Action disposeCallback);

    protected virtual System.Void Dispose(System.Boolean disposing);
    public virtual System.Void Flush();
    public static Colossal.PSI.MicrosoftGdk.GdkCloudStream OpenReadWrite(System.String containerName, System.String blobName, Colossal.PSI.MicrosoftGdk.GdkPlatform platformSupport, System.Action disposeCallback);
    public virtual System.Int32 Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count);
    public virtual System.Int64 Seek(System.Int64 offset, System.IO.SeekOrigin origin);
    public virtual System.Void SetLength(System.Int64 value);
    public virtual System.Void Write(System.Byte[] array, System.Int32 offset, System.Int32 count);
}
```


## Fields

- `private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformSupport`  

```csharp
private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformSupport;
```

- `private readonly System.Action m_DisposeCallback`  

```csharp
private readonly System.Action m_DisposeCallback;
```

- `private System.Int64 m_Position`  

```csharp
private System.Int64 m_Position;
```

- `private System.Int64 m_Length`  

```csharp
private System.Int64 m_Length;
```

- `private System.Byte[] m_Buffer`  

```csharp
private System.Byte[] m_Buffer;
```

- `private System.String m_ContainerName`  

```csharp
private System.String m_ContainerName;
```

- `private System.String m_BlobName`  

```csharp
private System.String m_BlobName;
```

- `private System.Int32 m_Part`  

```csharp
private System.Int32 m_Part;
```

- `private System.Boolean m_Disposed`  

```csharp
private System.Boolean m_Disposed;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static const System.Int32 kMaxBufferSize`  

```csharp
private static const System.Int32 kMaxBufferSize;
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

- `public System.Int64 Length { get }`  

```csharp
public System.Int64 Length { get; }
```

- `public System.Int64 Position { get; set }`  

```csharp
public System.Int64 Position { get; set; }
```


## Constructors

- `private GdkCloudStream(System.String containerName, System.String blobName, Colossal.PSI.MicrosoftGdk.GdkPlatform platformSupport, System.Action disposeCallback)`  

```csharp
private GdkCloudStream(System.String containerName, System.String blobName, Colossal.PSI.MicrosoftGdk.GdkPlatform platformSupport, System.Action disposeCallback);
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

- `public static OpenReadWrite(System.String containerName, System.String blobName, Colossal.PSI.MicrosoftGdk.GdkPlatform platformSupport, System.Action disposeCallback) : Colossal.PSI.MicrosoftGdk.GdkCloudStream`  

```csharp
public static Colossal.PSI.MicrosoftGdk.GdkCloudStream OpenReadWrite(System.String containerName, System.String blobName, Colossal.PSI.MicrosoftGdk.GdkPlatform platformSupport, System.Action disposeCallback);
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

- `public virtual Write(System.Byte[] array, System.Int32 offset, System.Int32 count) : System.Void`  

```csharp
public virtual System.Void Write(System.Byte[] array, System.Int32 offset, System.Int32 count);
```


