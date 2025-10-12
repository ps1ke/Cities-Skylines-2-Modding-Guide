# Colossal.IO.AssetDatabase.SubStream

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.IO.Stream`  
**Implements:** `System.IDisposable`, `System.IAsyncDisposable`  

## Fields

- `private readonly System.Int64 m_StartInSuperStream`  
- `private System.Int64 m_PositionInSuperStream`  
- `private readonly System.Int64 m_EndInSuperStream`  
- `private readonly System.IO.Stream m_SuperStream`  
- `private System.Boolean m_CanRead`  
- `private System.Boolean m_CanSeek`  
- `private System.Boolean m_IsDisposed`  
- `private System.Boolean m_LeaveOpen`  

## Properties

- `public System.Int64 Length { get }`  
- `public System.Int64 Position { get; set }`  
- `public System.Boolean CanRead { get }`  
- `public System.Boolean CanSeek { get }`  
- `public System.Boolean CanWrite { get }`  

## Constructors

- `public SubStream(System.IO.Stream superStream, System.Int64 startPosition, System.Int64 size, System.Boolean leaveOpen = False)`  

## Methods

- `protected virtual Dispose(System.Boolean disposing) : System.Void`  
- `public virtual Flush() : System.Void`  
- `public virtual Read(System.Byte[] buffer, System.Int32 offset, System.Int32 count) : System.Int32`  
- `public SaveToFile(System.String path) : System.Void`  
- `public virtual Seek(System.Int64 offset, System.IO.SeekOrigin origin) : System.Int64`  
- `public virtual SetLength(System.Int64 value) : System.Void`  
- `private ThrowIfCantRead() : System.Void`  
- `private ThrowIfCantSeek() : System.Void`  
- `private ThrowIfDisposed() : System.Void`  
- `public virtual Write(System.Byte[] buffer, System.Int32 offset, System.Int32 count) : System.Void`  

