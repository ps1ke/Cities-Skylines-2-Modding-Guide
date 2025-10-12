# Colossal.Rendering.AsyncGPUReadbackHelper

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private System.Boolean m_IsPending`  
- `private System.Int32 m_RequestFrameLatency`  
- `private UnityEngine.Rendering.AsyncGPUReadbackRequest m_Request`  

## Properties

- `public System.Int32 requestFrameLatency { get }`  
- `public System.Boolean isPending { get }`  
- `public System.Boolean done { get }`  
- `public System.Boolean hasError { get }`  
- `public System.Int32 layerCount { get }`  
- `public System.Int32 layerDataSize { get }`  
- `public System.Int32 width { get }`  
- `public System.Int32 height { get }`  
- `public System.Int32 depth { get }`  

## Methods

- `public GetData<T>(System.Int32 layer = 0) : Unity.Collections.NativeArray<T>`  
- `public IncrementFrame() : System.Void`  
- `public Request(UnityEngine.ComputeBuffer src, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  
- `public Request(UnityEngine.ComputeBuffer src, System.Int32 size, System.Int32 offset, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  
- `public Request(UnityEngine.Texture src, System.Int32 mipIndex = 0, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  
- `public Request(UnityEngine.Texture src, System.Int32 mipIndex, UnityEngine.Experimental.Rendering.GraphicsFormat dstFormat, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  
- `public Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Int32 x, System.Int32 width, System.Int32 y, System.Int32 height, System.Int32 z, System.Int32 depth, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  
- `public Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Int32 x, System.Int32 width, System.Int32 y, System.Int32 height, System.Int32 z, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat dstFormat, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  
- `public Update() : System.Void`  
- `public WaitForCompletion() : System.Void`  

