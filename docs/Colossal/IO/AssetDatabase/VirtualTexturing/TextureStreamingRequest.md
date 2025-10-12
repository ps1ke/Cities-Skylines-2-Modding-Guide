# Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.List<Unity.IO.LowLevel.Unsafe.ReadHandle> m_ReadHandles`  
- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle> m_ReadAndDecompressionHandles`  
- `private Unity.Collections.NativeArray<Unity.IO.LowLevel.Unsafe.ReadCommand> m_Cmds`  
- `private UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> m_Request`  
- `private static const System.Int32 MAX_NB_LAYERS`  
- `private static const System.Int32 MAX_NB_READS`  
- `private static const System.Int32 MAX_NB_READ_COMMANDS`  

## Constructors

- `public TextureStreamingRequest()`  

## Methods

- `public Add(Unity.IO.LowLevel.Unsafe.ReadHandle readHandle) : System.Void`  
- `public Add(Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle handle) : System.Void`  
- `public CompleteIfDone() : System.Boolean`  
- `public Dispose() : System.Void`  
- `public GetCmdsSlice() : Unity.Collections.NativeSlice<Unity.IO.LowLevel.Unsafe.ReadCommand>`  
- `public GetRequestParameters() : UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters`  
- `public GetSingleCmdsSlice(System.Int32 nbReads) : Unity.Collections.NativeSlice<Unity.IO.LowLevel.Unsafe.ReadCommand>`  
- `public SetRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> request) : System.Void`  
- `public Update() : System.Void`  

