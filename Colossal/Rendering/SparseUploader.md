# Colossal.Rendering.SparseUploader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct SparseUploader : System.IDisposable
{
    private System.Int32 m_BufferChunkSize;
    private UnityEngine.GraphicsBuffer m_DestinationBuffer;
    private Colossal.Rendering.BufferPool m_UploadBufferPool;
    private Unity.Collections.NativeArray<Colossal.Rendering.MappedBuffer> m_MappedBuffers;
    private System.Int64 m_CurrentFrameUploadSize;
    private System.Int64 m_MaxUploadSize;
    private System.Collections.Generic.Stack<Colossal.Rendering.SparseUploader+FrameData> m_FreeFrameData;
    private System.Collections.Generic.List<Colossal.Rendering.SparseUploader+FrameData> m_FrameData;
    private Colossal.Rendering.ThreadedSparseUploaderData* m_ThreadData;
    private UnityEngine.ComputeShader m_SparseUploaderShader;
    private System.Int32 m_CopyKernelIndex;
    private System.Int32 m_ReplaceKernelIndex;
    private System.Int32 m_SrcBufferID;
    private System.Int32 m_DstBufferID;
    private System.Int32 m_OperationsBaseID;
    private System.Int32 m_ReplaceOperationSize;
    private System.Int32 m_ReplaceSrcOffset;
    private System.Int32 m_ReplaceDstOffset;
    private static const System.Int32 k_MaxThreadGroupsPerDispatch;

    internal static System.Int32 NumFramesInFlight { internal get; }

    public SparseUploader(System.String name, UnityEngine.GraphicsBuffer destinationBuffer, System.Int32 bufferChunkSize);

    public Colossal.Rendering.ThreadedSparseUploader Begin(System.Int32 maxDataSizeInBytes, System.Int32 biggestDataUpload, System.Int32 maxOperationCount);
    public Colossal.Rendering.SparseUploaderStats ComputeStats();
    private System.Void DispatchUploads(System.Int32 numOps, UnityEngine.GraphicsBuffer graphicsBuffer);
    public System.Void Dispose();
    public System.Void EndAndCommit(Colossal.Rendering.ThreadedSparseUploader tsu);
    public System.Void FrameCleanup();
    private System.Void RecoverBuffers();
    public System.Void ReplaceBuffer(UnityEngine.GraphicsBuffer buffer, System.Boolean copyFromPrevious, System.Int32 copyStride);
    private System.Void StepFrame();
}
```


## Fields

- `private System.Int32 m_BufferChunkSize`  

```csharp
private System.Int32 m_BufferChunkSize;
```

- `private UnityEngine.GraphicsBuffer m_DestinationBuffer`  

```csharp
private UnityEngine.GraphicsBuffer m_DestinationBuffer;
```

- `private Colossal.Rendering.BufferPool m_UploadBufferPool`  

```csharp
private Colossal.Rendering.BufferPool m_UploadBufferPool;
```

- `private Unity.Collections.NativeArray<Colossal.Rendering.MappedBuffer> m_MappedBuffers`  

```csharp
private Unity.Collections.NativeArray<Colossal.Rendering.MappedBuffer> m_MappedBuffers;
```

- `private System.Int64 m_CurrentFrameUploadSize`  

```csharp
private System.Int64 m_CurrentFrameUploadSize;
```

- `private System.Int64 m_MaxUploadSize`  

```csharp
private System.Int64 m_MaxUploadSize;
```

- `private System.Collections.Generic.Stack<Colossal.Rendering.SparseUploader+FrameData> m_FreeFrameData`  

```csharp
private System.Collections.Generic.Stack<Colossal.Rendering.SparseUploader+FrameData> m_FreeFrameData;
```

- `private System.Collections.Generic.List<Colossal.Rendering.SparseUploader+FrameData> m_FrameData`  

```csharp
private System.Collections.Generic.List<Colossal.Rendering.SparseUploader+FrameData> m_FrameData;
```

- `private Colossal.Rendering.ThreadedSparseUploaderData* m_ThreadData`  

```csharp
private Colossal.Rendering.ThreadedSparseUploaderData* m_ThreadData;
```

- `private UnityEngine.ComputeShader m_SparseUploaderShader`  

```csharp
private UnityEngine.ComputeShader m_SparseUploaderShader;
```

- `private System.Int32 m_CopyKernelIndex`  

```csharp
private System.Int32 m_CopyKernelIndex;
```

- `private System.Int32 m_ReplaceKernelIndex`  

```csharp
private System.Int32 m_ReplaceKernelIndex;
```

- `private System.Int32 m_SrcBufferID`  

```csharp
private System.Int32 m_SrcBufferID;
```

- `private System.Int32 m_DstBufferID`  

```csharp
private System.Int32 m_DstBufferID;
```

- `private System.Int32 m_OperationsBaseID`  

```csharp
private System.Int32 m_OperationsBaseID;
```

- `private System.Int32 m_ReplaceOperationSize`  

```csharp
private System.Int32 m_ReplaceOperationSize;
```

- `private System.Int32 m_ReplaceSrcOffset`  

```csharp
private System.Int32 m_ReplaceSrcOffset;
```

- `private System.Int32 m_ReplaceDstOffset`  

```csharp
private System.Int32 m_ReplaceDstOffset;
```

- `private static const System.Int32 k_MaxThreadGroupsPerDispatch`  

```csharp
private static const System.Int32 k_MaxThreadGroupsPerDispatch;
```


## Properties

- `internal static System.Int32 NumFramesInFlight { internal get }`  

```csharp
internal static System.Int32 NumFramesInFlight { internal get; }
```


## Constructors

- `public SparseUploader(System.String name, UnityEngine.GraphicsBuffer destinationBuffer, System.Int32 bufferChunkSize = 16777216)`  

```csharp
public SparseUploader(System.String name, UnityEngine.GraphicsBuffer destinationBuffer, System.Int32 bufferChunkSize);
```


## Methods

- `public Begin(System.Int32 maxDataSizeInBytes, System.Int32 biggestDataUpload, System.Int32 maxOperationCount) : Colossal.Rendering.ThreadedSparseUploader`  

```csharp
public Colossal.Rendering.ThreadedSparseUploader Begin(System.Int32 maxDataSizeInBytes, System.Int32 biggestDataUpload, System.Int32 maxOperationCount);
```

- `public ComputeStats() : Colossal.Rendering.SparseUploaderStats`  

```csharp
public Colossal.Rendering.SparseUploaderStats ComputeStats();
```

- `private DispatchUploads(System.Int32 numOps, UnityEngine.GraphicsBuffer graphicsBuffer) : System.Void`  

```csharp
private System.Void DispatchUploads(System.Int32 numOps, UnityEngine.GraphicsBuffer graphicsBuffer);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public EndAndCommit(Colossal.Rendering.ThreadedSparseUploader tsu) : System.Void`  

```csharp
public System.Void EndAndCommit(Colossal.Rendering.ThreadedSparseUploader tsu);
```

- `public FrameCleanup() : System.Void`  

```csharp
public System.Void FrameCleanup();
```

- `private RecoverBuffers() : System.Void`  

```csharp
private System.Void RecoverBuffers();
```

- `public ReplaceBuffer(UnityEngine.GraphicsBuffer buffer, System.Boolean copyFromPrevious = False, System.Int32 copyStride = 0) : System.Void`  

```csharp
public System.Void ReplaceBuffer(UnityEngine.GraphicsBuffer buffer, System.Boolean copyFromPrevious, System.Int32 copyStride);
```

- `private StepFrame() : System.Void`  

```csharp
private System.Void StepFrame();
```


## Nested types

- `Colossal.Rendering.SparseUploader+FrameData`  

