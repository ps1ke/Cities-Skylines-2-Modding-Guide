# Colossal.Rendering.VTTextureRequester

**Assembly:** `Game`  
**Namespace:** `Colossal.Rendering`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class VTTextureRequester : System.IDisposable
{
    private Unity.Collections.NativeList<System.Int32>[] m_TexturesIndices;
    private Unity.Collections.NativeList<System.Int32>[] m_StackGlobalIndices;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>[] m_TextureBounds;
    private Unity.Collections.NativeList<System.Single>[] m_TexturesMaxPixels;
    private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem;
    private System.Int32 m_RequestedThisFrame;

    public System.Int32 stacksCount { get; }
    public System.Int32 registeredCount { get; }
    public System.Int32 requestCount { get; }
    public Unity.Collections.NativeList<System.Single>[] TexturesMaxPixels { get; }

    public VTTextureRequester(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem);

    public System.Void Clear();
    public System.Void Dispose();
    public System.Int32 GetTextureIndex(System.Int32 stackIndex, System.Int32 texturesIndex);
    public System.Int32 RegisterTexture(System.Int32 stackConfigIndex, System.Int32 stackGlobalIndex, System.Int32 vtIndex, Colossal.Mathematics.Bounds2 bounds);
    public System.Void UpdateMaxPixel(System.Int32 stackIndex, System.Int32 texturesIndex, System.Single maxPixel);
    public System.Void UpdateTexturesVTRequests();
}
```


## Fields

- `private Unity.Collections.NativeList<System.Int32>[] m_TexturesIndices`  

```csharp
private Unity.Collections.NativeList<System.Int32>[] m_TexturesIndices;
```

- `private Unity.Collections.NativeList<System.Int32>[] m_StackGlobalIndices`  

```csharp
private Unity.Collections.NativeList<System.Int32>[] m_StackGlobalIndices;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>[] m_TextureBounds`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>[] m_TextureBounds;
```

- `private Unity.Collections.NativeList<System.Single>[] m_TexturesMaxPixels`  

```csharp
private Unity.Collections.NativeList<System.Single>[] m_TexturesMaxPixels;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem;
```

- `private System.Int32 m_RequestedThisFrame`  

```csharp
private System.Int32 m_RequestedThisFrame;
```


## Properties

- `public System.Int32 stacksCount { get }`  

```csharp
public System.Int32 stacksCount { get; }
```

- `public System.Int32 registeredCount { get }`  

```csharp
public System.Int32 registeredCount { get; }
```

- `public System.Int32 requestCount { get }`  

```csharp
public System.Int32 requestCount { get; }
```

- `public Unity.Collections.NativeList<System.Single>[] TexturesMaxPixels { get }`  

```csharp
public Unity.Collections.NativeList<System.Single>[] TexturesMaxPixels { get; }
```


## Constructors

- `public VTTextureRequester(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem)`  

```csharp
public VTTextureRequester(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem);
```


## Methods

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetTextureIndex(System.Int32 stackIndex, System.Int32 texturesIndex) : System.Int32`  

```csharp
public System.Int32 GetTextureIndex(System.Int32 stackIndex, System.Int32 texturesIndex);
```

- `public RegisterTexture(System.Int32 stackConfigIndex, System.Int32 stackGlobalIndex, System.Int32 vtIndex, Colossal.Mathematics.Bounds2 bounds) : System.Int32`  

```csharp
public System.Int32 RegisterTexture(System.Int32 stackConfigIndex, System.Int32 stackGlobalIndex, System.Int32 vtIndex, Colossal.Mathematics.Bounds2 bounds);
```

- `public UpdateMaxPixel(System.Int32 stackIndex, System.Int32 texturesIndex, System.Single maxPixel) : System.Void`  

```csharp
public System.Void UpdateMaxPixel(System.Int32 stackIndex, System.Int32 texturesIndex, System.Single maxPixel);
```

- `public UpdateTexturesVTRequests() : System.Void`  

```csharp
public System.Void UpdateTexturesVTRequests();
```


