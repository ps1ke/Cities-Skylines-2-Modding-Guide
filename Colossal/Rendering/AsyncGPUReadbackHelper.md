# Colossal.Rendering.AsyncGPUReadbackHelper

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct AsyncGPUReadbackHelper
{
    private System.Boolean m_IsPending;
    private System.Int32 m_RequestFrameLatency;
    private UnityEngine.Rendering.AsyncGPUReadbackRequest m_Request;

    public System.Int32 requestFrameLatency { get; }
    public System.Boolean isPending { get; }
    public System.Boolean done { get; }
    public System.Boolean hasError { get; }
    public System.Int32 layerCount { get; }
    public System.Int32 layerDataSize { get; }
    public System.Int32 width { get; }
    public System.Int32 height { get; }
    public System.Int32 depth { get; }

    public Unity.Collections.NativeArray<T> GetData<T>(System.Int32 layer);
    public System.Void IncrementFrame();
    public System.Void Request(UnityEngine.ComputeBuffer src, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
    public System.Void Request(UnityEngine.ComputeBuffer src, System.Int32 size, System.Int32 offset, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
    public System.Void Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
    public System.Void Request(UnityEngine.Texture src, System.Int32 mipIndex, UnityEngine.Experimental.Rendering.GraphicsFormat dstFormat, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
    public System.Void Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Int32 x, System.Int32 width, System.Int32 y, System.Int32 height, System.Int32 z, System.Int32 depth, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
    public System.Void Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Int32 x, System.Int32 width, System.Int32 y, System.Int32 height, System.Int32 z, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat dstFormat, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
    public System.Void Update();
    public System.Void WaitForCompletion();
}
```


## Fields

- `private System.Boolean m_IsPending`  

```csharp
private System.Boolean m_IsPending;
```

- `private System.Int32 m_RequestFrameLatency`  

```csharp
private System.Int32 m_RequestFrameLatency;
```

- `private UnityEngine.Rendering.AsyncGPUReadbackRequest m_Request`  

```csharp
private UnityEngine.Rendering.AsyncGPUReadbackRequest m_Request;
```


## Properties

- `public System.Int32 requestFrameLatency { get }`  

```csharp
public System.Int32 requestFrameLatency { get; }
```

- `public System.Boolean isPending { get }`  

```csharp
public System.Boolean isPending { get; }
```

- `public System.Boolean done { get }`  

```csharp
public System.Boolean done { get; }
```

- `public System.Boolean hasError { get }`  

```csharp
public System.Boolean hasError { get; }
```

- `public System.Int32 layerCount { get }`  

```csharp
public System.Int32 layerCount { get; }
```

- `public System.Int32 layerDataSize { get }`  

```csharp
public System.Int32 layerDataSize { get; }
```

- `public System.Int32 width { get }`  

```csharp
public System.Int32 width { get; }
```

- `public System.Int32 height { get }`  

```csharp
public System.Int32 height { get; }
```

- `public System.Int32 depth { get }`  

```csharp
public System.Int32 depth { get; }
```


## Methods

- `public GetData<T>(System.Int32 layer = 0) : Unity.Collections.NativeArray<T>`  

```csharp
public Unity.Collections.NativeArray<T> GetData<T>(System.Int32 layer);
```

- `public IncrementFrame() : System.Void`  

```csharp
public System.Void IncrementFrame();
```

- `public Request(UnityEngine.ComputeBuffer src, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  

```csharp
public System.Void Request(UnityEngine.ComputeBuffer src, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
```

- `public Request(UnityEngine.ComputeBuffer src, System.Int32 size, System.Int32 offset, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  

```csharp
public System.Void Request(UnityEngine.ComputeBuffer src, System.Int32 size, System.Int32 offset, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
```

- `public Request(UnityEngine.Texture src, System.Int32 mipIndex = 0, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  

```csharp
public System.Void Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
```

- `public Request(UnityEngine.Texture src, System.Int32 mipIndex, UnityEngine.Experimental.Rendering.GraphicsFormat dstFormat, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  

```csharp
public System.Void Request(UnityEngine.Texture src, System.Int32 mipIndex, UnityEngine.Experimental.Rendering.GraphicsFormat dstFormat, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
```

- `public Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Int32 x, System.Int32 width, System.Int32 y, System.Int32 height, System.Int32 z, System.Int32 depth, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  

```csharp
public System.Void Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Int32 x, System.Int32 width, System.Int32 y, System.Int32 height, System.Int32 z, System.Int32 depth, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
```

- `public Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Int32 x, System.Int32 width, System.Int32 y, System.Int32 height, System.Int32 z, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat dstFormat, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback = null) : System.Void`  

```csharp
public System.Void Request(UnityEngine.Texture src, System.Int32 mipIndex, System.Int32 x, System.Int32 width, System.Int32 y, System.Int32 height, System.Int32 z, System.Int32 depth, UnityEngine.Experimental.Rendering.GraphicsFormat dstFormat, System.Action<UnityEngine.Rendering.AsyncGPUReadbackRequest> callback);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `public WaitForCompletion() : System.Void`  

```csharp
public System.Void WaitForCompletion();
```


