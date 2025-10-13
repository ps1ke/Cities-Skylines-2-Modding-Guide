# Colossal.IO.AssetDatabase.VirtualTexturing.VTProceduralCPU

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator`  

## Code

```csharp
public class VTProceduralCPU : Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator
{
    private System.Collections.Generic.List<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStack> m_Stacks;
    private System.Collections.Generic.List<Unity.Collections.NativeArray<UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters>>> m_FetchedRequests;
    private Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig m_VirtualTexturingConfig;

    public VTProceduralCPU(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig);

    public System.Void BindMaterial(UnityEngine.Material material, System.Int32 stackGlobalIndex);
    public System.Void BindStacksGlobally();
    public System.Void BindStacksGlobally(System.Int32 stackGlobalIndex);
    public System.Void CreateStack(System.Int32 stackConfigIndex);
    public System.Void Destroy();
    private System.Void DestroyStacks();
    private System.Void FillNormalRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 stackGlobalIndex, System.Int32 nbLayers, System.Int32 tileSize, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
    public System.Void InvalidateRegion(System.Int32 stackGlobalIndex, UnityEngine.Rect rect);
    public System.Void RequestRegion(System.Int32 stackGlobalIndex, UnityEngine.Rect rect, System.Int32 minMip, System.Int32 nbMips);
    public System.Void UpdateStacks(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase);
}
```


## Fields

- `private System.Collections.Generic.List<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStack> m_Stacks`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStack> m_Stacks;
```

- `private System.Collections.Generic.List<Unity.Collections.NativeArray<UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters>>> m_FetchedRequests`  

```csharp
private System.Collections.Generic.List<Unity.Collections.NativeArray<UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters>>> m_FetchedRequests;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig m_VirtualTexturingConfig`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig m_VirtualTexturingConfig;
```


## Constructors

- `public VTProceduralCPU(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig)`  

```csharp
public VTProceduralCPU(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig);
```


## Methods

- `public BindMaterial(UnityEngine.Material material, System.Int32 stackGlobalIndex) : System.Void`  

```csharp
public System.Void BindMaterial(UnityEngine.Material material, System.Int32 stackGlobalIndex);
```

- `public BindStacksGlobally() : System.Void`  

```csharp
public System.Void BindStacksGlobally();
```

- `public BindStacksGlobally(System.Int32 stackGlobalIndex) : System.Void`  

```csharp
public System.Void BindStacksGlobally(System.Int32 stackGlobalIndex);
```

- `public CreateStack(System.Int32 stackConfigIndex) : System.Void`  

```csharp
public System.Void CreateStack(System.Int32 stackConfigIndex);
```

- `public Destroy() : System.Void`  

```csharp
public System.Void Destroy();
```

- `private DestroyStacks() : System.Void`  

```csharp
private System.Void DestroyStacks();
```

- `private FillNormalRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 stackGlobalIndex, System.Int32 nbLayers, System.Int32 tileSize, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest) : System.Void`  

```csharp
private System.Void FillNormalRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 stackGlobalIndex, System.Int32 nbLayers, System.Int32 tileSize, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
```

- `public InvalidateRegion(System.Int32 stackGlobalIndex, UnityEngine.Rect rect) : System.Void`  

```csharp
public System.Void InvalidateRegion(System.Int32 stackGlobalIndex, UnityEngine.Rect rect);
```

- `public RequestRegion(System.Int32 stackGlobalIndex, UnityEngine.Rect rect, System.Int32 minMip, System.Int32 nbMips) : System.Void`  

```csharp
public System.Void RequestRegion(System.Int32 stackGlobalIndex, UnityEngine.Rect rect, System.Int32 minMip, System.Int32 nbMips);
```

- `public UpdateStacks(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase) : System.Void`  

```csharp
public System.Void UpdateStacks(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase vtDatabase);
```


