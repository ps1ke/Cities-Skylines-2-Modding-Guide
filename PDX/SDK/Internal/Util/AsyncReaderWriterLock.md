# PDX.SDK.Internal.Util.AsyncReaderWriterLock

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Util`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed class AsyncReaderWriterLock : System.IDisposable
{
    private readonly System.Threading.SemaphoreSlim _readSemaphore;
    private readonly System.Threading.SemaphoreSlim _writeSemaphore;
    private System.Int32 _readerCount;

    public AsyncReaderWriterLock();

    public System.Threading.Tasks.Task AcquireReaderLock(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task AcquireWriterLock(System.Threading.CancellationToken token);
    public System.Void Dispose();
    public System.Void ReleaseReaderLock();
    public System.Void ReleaseWriterLock();
    private System.Threading.Tasks.Task SafeAcquireReadSemaphore(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<PDX.SDK.Internal.Enums.AquireLockStatus> TryAcquireReaderLock(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<PDX.SDK.Internal.Enums.AquireLockStatus> TryAcquireWriterLock(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.Boolean> TrySafeAcquireReadSemaphore(System.Threading.CancellationToken token);
}
```


## Fields

- `private readonly System.Threading.SemaphoreSlim _readSemaphore`  

```csharp
private readonly System.Threading.SemaphoreSlim _readSemaphore;
```

- `private readonly System.Threading.SemaphoreSlim _writeSemaphore`  

```csharp
private readonly System.Threading.SemaphoreSlim _writeSemaphore;
```

- `private System.Int32 _readerCount`  

```csharp
private System.Int32 _readerCount;
```


## Constructors

- `public AsyncReaderWriterLock()`  

```csharp
public AsyncReaderWriterLock();
```


## Methods

- `public AcquireReaderLock(System.Threading.CancellationToken token = null) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task AcquireReaderLock(System.Threading.CancellationToken token);
```

- `public AcquireWriterLock(System.Threading.CancellationToken token = null) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task AcquireWriterLock(System.Threading.CancellationToken token);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ReleaseReaderLock() : System.Void`  

```csharp
public System.Void ReleaseReaderLock();
```

- `public ReleaseWriterLock() : System.Void`  

```csharp
public System.Void ReleaseWriterLock();
```

- `private SafeAcquireReadSemaphore(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task SafeAcquireReadSemaphore(System.Threading.CancellationToken token);
```

- `public TryAcquireReaderLock(System.Threading.CancellationToken token = null) : System.Threading.Tasks.Task<PDX.SDK.Internal.Enums.AquireLockStatus>`  

```csharp
public System.Threading.Tasks.Task<PDX.SDK.Internal.Enums.AquireLockStatus> TryAcquireReaderLock(System.Threading.CancellationToken token);
```

- `public TryAcquireWriterLock(System.Threading.CancellationToken token = null) : System.Threading.Tasks.Task<PDX.SDK.Internal.Enums.AquireLockStatus>`  

```csharp
public System.Threading.Tasks.Task<PDX.SDK.Internal.Enums.AquireLockStatus> TryAcquireWriterLock(System.Threading.CancellationToken token);
```

- `private TrySafeAcquireReadSemaphore(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> TrySafeAcquireReadSemaphore(System.Threading.CancellationToken token);
```


## Nested types

- `PDX.SDK.Internal.Util.AsyncReaderWriterLock+<AcquireReaderLock>d__7`  
- `PDX.SDK.Internal.Util.AsyncReaderWriterLock+<AcquireWriterLock>d__4`  
- `PDX.SDK.Internal.Util.AsyncReaderWriterLock+<SafeAcquireReadSemaphore>d__9`  
- `PDX.SDK.Internal.Util.AsyncReaderWriterLock+<TryAcquireReaderLock>d__6`  
- `PDX.SDK.Internal.Util.AsyncReaderWriterLock+<TryAcquireWriterLock>d__3`  
- `PDX.SDK.Internal.Util.AsyncReaderWriterLock+<TrySafeAcquireReadSemaphore>d__10`  

