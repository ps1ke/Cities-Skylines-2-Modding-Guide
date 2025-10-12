# Colossal.IO.AssetDatabase.VirtualTexturing.VTProceduralCPU

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator`  

## Fields

- `private System.Collections.Generic.List<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStack> m_Stacks`  
- `private System.Collections.Generic.List<Unity.Collections.NativeArray<UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters>>> m_FetchedRequests`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig m_VirtualTexturingConfig`  

## Constructors

- `public VTProceduralCPU(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig)`  

## Methods

- `public BindMaterial(UnityEngine.Material material, System.Int32 stackGlobalIndex) : System.Void`  
- `public BindStacksGlobally() : System.Void`  
- `public BindStacksGlobally(System.Int32 stackGlobalIndex) : System.Void`  
- `public CreateStack(System.Int32 stackConfigIndex) : System.Void`  
- `public Destroy() : System.Void`  
- `private DestroyStacks() : System.Void`  
- `private FillNormalRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 stackGlobalIndex, System.Int32 nbLayers, System.Int32 tileSize, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest) : System.Void`  
- `public InvalidateRegion(System.Int32 stackGlobalIndex, UnityEngine.Rect rect) : System.Void`  
- `public RequestRegion(System.Int32 stackGlobalIndex, UnityEngine.Rect rect, System.Int32 minMip, System.Int32 nbMips) : System.Void`  
- `public UpdateStacks(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase) : System.Void`  

