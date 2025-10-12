# Colossal.InstaLOD.InstaLODMaterial

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `internal System.IntPtr m_Ptr`  

## Properties

- `public System.Int32 textureCount { get }`  

## Constructors

- `internal InstaLODMaterial(System.IntPtr ptr)`  

## Methods

- `public AddTexture(System.String name, Colossal.InstaLOD.TextureType type, System.Int32 width, System.Int32 height, System.Int32 bitsPerChannel, System.Int32 channels, System.IntPtr data) : System.Void`  
- `public GetTextureData(System.Int32 index) : System.IntPtr`  
- `public GetTextureDesc(System.Int32 index, Colossal.InstaLOD.TextureType& textureType, System.Int32& width, System.Int32& height, System.Int32& bitsPerChannel, System.Int32& channels) : System.String`  

