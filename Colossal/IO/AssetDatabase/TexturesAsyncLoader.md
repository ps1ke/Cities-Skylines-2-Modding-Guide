# Colossal.IO.AssetDatabase.TexturesAsyncLoader

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class TexturesAsyncLoader
{
    private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader+AsyncData> m_Format0AsyncData;
    private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader+DependencyData> m_Format0DependenciesData;
    private System.Collections.Generic.List<Unity.IO.LowLevel.Unsafe.ReadHandle> m_ReadHandles;
    public System.Int32 m_StackGlobalIndex;
    public System.Int32 m_TextureIndex;
    public System.Int32 m_TextureWidth;
    public System.Int32 m_TextureHeight;

    public TexturesAsyncLoader();

    public System.Void Add(System.String path, System.Int64 offset, Colossal.Hash128 textureGuid, Unity.Collections.NativeArray<System.Byte> data, System.Int32 layerIndex, System.Int32 nbPreProcessedMidMipLevels);
    public System.Void AddDependency(Colossal.Hash128 textureGuid, System.Int32 layerIndex, System.Int32 nbPreProcessedMidMipLevels);
    public System.Boolean CompleteIfReady(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem);
    public System.Void StartStreaming();
}
```


## Fields

- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader+AsyncData> m_Format0AsyncData`  

```csharp
private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader+AsyncData> m_Format0AsyncData;
```

- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader+DependencyData> m_Format0DependenciesData`  

```csharp
private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader+DependencyData> m_Format0DependenciesData;
```

- `private System.Collections.Generic.List<Unity.IO.LowLevel.Unsafe.ReadHandle> m_ReadHandles`  

```csharp
private System.Collections.Generic.List<Unity.IO.LowLevel.Unsafe.ReadHandle> m_ReadHandles;
```

- `public System.Int32 m_StackGlobalIndex`  

```csharp
public System.Int32 m_StackGlobalIndex;
```

- `public System.Int32 m_TextureIndex`  

```csharp
public System.Int32 m_TextureIndex;
```

- `public System.Int32 m_TextureWidth`  

```csharp
public System.Int32 m_TextureWidth;
```

- `public System.Int32 m_TextureHeight`  

```csharp
public System.Int32 m_TextureHeight;
```


## Constructors

- `public TexturesAsyncLoader()`  

```csharp
public TexturesAsyncLoader();
```


## Methods

- `public Add(System.String path, System.Int64 offset, Colossal.Hash128 textureGuid, Unity.Collections.NativeArray<System.Byte> data, System.Int32 layerIndex, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  

```csharp
public System.Void Add(System.String path, System.Int64 offset, Colossal.Hash128 textureGuid, Unity.Collections.NativeArray<System.Byte> data, System.Int32 layerIndex, System.Int32 nbPreProcessedMidMipLevels);
```

- `public AddDependency(Colossal.Hash128 textureGuid, System.Int32 layerIndex, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  

```csharp
public System.Void AddDependency(Colossal.Hash128 textureGuid, System.Int32 layerIndex, System.Int32 nbPreProcessedMidMipLevels);
```

- `public CompleteIfReady(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem) : System.Boolean`  

```csharp
public System.Boolean CompleteIfReady(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem);
```

- `public StartStreaming() : System.Void`  

```csharp
public System.Void StartStreaming();
```


## Nested types

- `Colossal.IO.AssetDatabase.TexturesAsyncLoader+AsyncData`  
- `Colossal.IO.AssetDatabase.TexturesAsyncLoader+DependencyData`  

