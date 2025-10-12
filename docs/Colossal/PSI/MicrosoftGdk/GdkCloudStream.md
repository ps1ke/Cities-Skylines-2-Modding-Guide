# Colossal.PSI.MicrosoftGdk.GdkCloudStream

**Assembly:** `Colossal.PSI.MicrosoftGdk`  
**Namespace:** `Colossal.PSI.MicrosoftGdk`  

**Type:** class public  

**Base:** `System.IO.Stream`  
**Implements:** `System.IDisposable`, `System.IAsyncDisposable`  

## Fields

- `private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformSupport`  
- `private readonly System.Action m_DisposeCallback`  
- `private System.Int64 m_Position`  
- `private System.Int64 m_Length`  
- `private System.Byte[] m_Buffer`  
- `private System.String m_ContainerName`  
- `private System.String m_BlobName`  
- `private System.Int32 m_Part`  
- `private System.Boolean m_Disposed`  
- `private static Colossal.Logging.ILog log`  
- `private static const System.Int32 kMaxBufferSize`  

## Properties

- `public System.Boolean CanRead { get }`  
- `public System.Boolean CanSeek { get }`  
- `public System.Boolean CanWrite { get }`  
- `public System.Int64 Length { get }`  
- `public System.Int64 Position { get; set }`  

## Constructors

- `private GdkCloudStream(System.String containerName, System.String blobName, Colossal.PSI.MicrosoftGdk.GdkPlatform platformSupport, System.Action disposeCallback)`  

## Methods

- `protected virtual Dispose(System.Boolean disposing) : System.Void`  
- `public virtual Flush() : System.Void`  
- `public static OpenReadWrite(System.String containerName, System.String blobName, Colossal.PSI.MicrosoftGdk.GdkPlatform platformSupport, System.Action disposeCallback) : Colossal.PSI.MicrosoftGdk.GdkCloudStream`  
- `public virtual Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count) : System.Int32`  
- `public virtual Seek(System.Int64 offset, System.IO.SeekOrigin origin) : System.Int64`  
- `public virtual SetLength(System.Int64 value) : System.Void`  
- `public virtual Write(System.Byte[] array, System.Int32 offset, System.Int32 count) : System.Void`  

