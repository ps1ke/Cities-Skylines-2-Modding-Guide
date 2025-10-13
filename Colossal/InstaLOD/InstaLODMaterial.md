# Colossal.InstaLOD.InstaLODMaterial

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct InstaLODMaterial
{
    internal System.IntPtr m_Ptr;

    public System.Int32 textureCount { get; }

    internal InstaLODMaterial(System.IntPtr ptr);

    public System.Void AddTexture(System.String name, Colossal.InstaLOD.TextureType type, System.Int32 width, System.Int32 height, System.Int32 bitsPerChannel, System.Int32 channels, System.IntPtr data);
    public System.IntPtr GetTextureData(System.Int32 index);
    public System.String GetTextureDesc(System.Int32 index, Colossal.InstaLOD.TextureType& textureType, System.Int32& width, System.Int32& height, System.Int32& bitsPerChannel, System.Int32& channels);
}
```


## Fields

- `internal System.IntPtr m_Ptr`  

```csharp
internal System.IntPtr m_Ptr;
```


## Properties

- `public System.Int32 textureCount { get }`  

```csharp
public System.Int32 textureCount { get; }
```


## Constructors

- `internal InstaLODMaterial(System.IntPtr ptr)`  

```csharp
internal InstaLODMaterial(System.IntPtr ptr);
```


## Methods

- `public AddTexture(System.String name, Colossal.InstaLOD.TextureType type, System.Int32 width, System.Int32 height, System.Int32 bitsPerChannel, System.Int32 channels, System.IntPtr data) : System.Void`  

```csharp
public System.Void AddTexture(System.String name, Colossal.InstaLOD.TextureType type, System.Int32 width, System.Int32 height, System.Int32 bitsPerChannel, System.Int32 channels, System.IntPtr data);
```

- `public GetTextureData(System.Int32 index) : System.IntPtr`  

```csharp
public System.IntPtr GetTextureData(System.Int32 index);
```

- `public GetTextureDesc(System.Int32 index, Colossal.InstaLOD.TextureType& textureType, System.Int32& width, System.Int32& height, System.Int32& bitsPerChannel, System.Int32& channels) : System.String`  

```csharp
public System.String GetTextureDesc(System.Int32 index, Colossal.InstaLOD.TextureType& textureType, System.Int32& width, System.Int32& height, System.Int32& bitsPerChannel, System.Int32& channels);
```


