# Colossal.Rendering.SparseUploader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.Int32 m_BufferChunkSize`  
- `private UnityEngine.GraphicsBuffer m_DestinationBuffer`  
- `private Colossal.Rendering.BufferPool m_UploadBufferPool`  
- `private Unity.Collections.NativeArray<Colossal.Rendering.MappedBuffer> m_MappedBuffers`  
- `private System.Int64 m_CurrentFrameUploadSize`  
- `private System.Int64 m_MaxUploadSize`  
- `private System.Collections.Generic.Stack<Colossal.Rendering.SparseUploader+FrameData> m_FreeFrameData`  
- `private System.Collections.Generic.List<Colossal.Rendering.SparseUploader+FrameData> m_FrameData`  
- `private Colossal.Rendering.ThreadedSparseUploaderData* m_ThreadData`  
- `private UnityEngine.ComputeShader m_SparseUploaderShader`  
- `private System.Int32 m_CopyKernelIndex`  
- `private System.Int32 m_ReplaceKernelIndex`  
- `private System.Int32 m_SrcBufferID`  
- `private System.Int32 m_DstBufferID`  
- `private System.Int32 m_OperationsBaseID`  
- `private System.Int32 m_ReplaceOperationSize`  
- `private System.Int32 m_ReplaceSrcOffset`  
- `private System.Int32 m_ReplaceDstOffset`  
- `private static const System.Int32 k_MaxThreadGroupsPerDispatch`  

## Properties

- `internal static System.Int32 NumFramesInFlight { internal get }`  

## Constructors

- `public SparseUploader(System.String name, UnityEngine.GraphicsBuffer destinationBuffer, System.Int32 bufferChunkSize = 16777216)`  

## Methods

- `public Begin(System.Int32 maxDataSizeInBytes, System.Int32 biggestDataUpload, System.Int32 maxOperationCount) : Colossal.Rendering.ThreadedSparseUploader`  
- `public ComputeStats() : Colossal.Rendering.SparseUploaderStats`  
- `private DispatchUploads(System.Int32 numOps, UnityEngine.GraphicsBuffer graphicsBuffer) : System.Void`  
- `public Dispose() : System.Void`  
- `public EndAndCommit(Colossal.Rendering.ThreadedSparseUploader tsu) : System.Void`  
- `public FrameCleanup() : System.Void`  
- `private RecoverBuffers() : System.Void`  
- `public ReplaceBuffer(UnityEngine.GraphicsBuffer buffer, System.Boolean copyFromPrevious = False, System.Int32 copyStride = 0) : System.Void`  
- `private StepFrame() : System.Void`  

## Nested types

- `Colossal.Rendering.SparseUploader+FrameData`  

