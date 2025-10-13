# Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class TextureStreamingRequest
{
    private System.Collections.Generic.List<Unity.IO.LowLevel.Unsafe.ReadHandle> m_ReadHandles;
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle> m_ReadAndDecompressionHandles;
    private Unity.Collections.NativeArray<Unity.IO.LowLevel.Unsafe.ReadCommand> m_Cmds;
    private UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> m_Request;
    private static const System.Int32 MAX_NB_LAYERS;
    private static const System.Int32 MAX_NB_READS;
    private static const System.Int32 MAX_NB_READ_COMMANDS;

    public TextureStreamingRequest();

    public System.Void Add(Unity.IO.LowLevel.Unsafe.ReadHandle readHandle);
    public System.Void Add(Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle handle);
    public System.Boolean CompleteIfDone();
    public System.Void Dispose();
    public Unity.Collections.NativeSlice<Unity.IO.LowLevel.Unsafe.ReadCommand> GetCmdsSlice();
    public UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters GetRequestParameters();
    public Unity.Collections.NativeSlice<Unity.IO.LowLevel.Unsafe.ReadCommand> GetSingleCmdsSlice(System.Int32 nbReads);
    public System.Void SetRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> request);
    public System.Void Update();
}
```


## Fields

- `private System.Collections.Generic.List<Unity.IO.LowLevel.Unsafe.ReadHandle> m_ReadHandles`  

```csharp
private System.Collections.Generic.List<Unity.IO.LowLevel.Unsafe.ReadHandle> m_ReadHandles;
```

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle> m_ReadAndDecompressionHandles`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle> m_ReadAndDecompressionHandles;
```

- `private Unity.Collections.NativeArray<Unity.IO.LowLevel.Unsafe.ReadCommand> m_Cmds`  

```csharp
private Unity.Collections.NativeArray<Unity.IO.LowLevel.Unsafe.ReadCommand> m_Cmds;
```

- `private UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> m_Request`  

```csharp
private UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> m_Request;
```

- `private static const System.Int32 MAX_NB_LAYERS`  

```csharp
private static const System.Int32 MAX_NB_LAYERS;
```

- `private static const System.Int32 MAX_NB_READS`  

```csharp
private static const System.Int32 MAX_NB_READS;
```

- `private static const System.Int32 MAX_NB_READ_COMMANDS`  

```csharp
private static const System.Int32 MAX_NB_READ_COMMANDS;
```


## Constructors

- `public TextureStreamingRequest()`  

```csharp
public TextureStreamingRequest();
```


## Methods

- `public Add(Unity.IO.LowLevel.Unsafe.ReadHandle readHandle) : System.Void`  

```csharp
public System.Void Add(Unity.IO.LowLevel.Unsafe.ReadHandle readHandle);
```

- `public Add(Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle handle) : System.Void`  

```csharp
public System.Void Add(Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle handle);
```

- `public CompleteIfDone() : System.Boolean`  

```csharp
public System.Boolean CompleteIfDone();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetCmdsSlice() : Unity.Collections.NativeSlice<Unity.IO.LowLevel.Unsafe.ReadCommand>`  

```csharp
public Unity.Collections.NativeSlice<Unity.IO.LowLevel.Unsafe.ReadCommand> GetCmdsSlice();
```

- `public GetRequestParameters() : UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters`  

```csharp
public UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters GetRequestParameters();
```

- `public GetSingleCmdsSlice(System.Int32 nbReads) : Unity.Collections.NativeSlice<Unity.IO.LowLevel.Unsafe.ReadCommand>`  

```csharp
public Unity.Collections.NativeSlice<Unity.IO.LowLevel.Unsafe.ReadCommand> GetSingleCmdsSlice(System.Int32 nbReads);
```

- `public SetRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> request) : System.Void`  

```csharp
public System.Void SetRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> request);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


