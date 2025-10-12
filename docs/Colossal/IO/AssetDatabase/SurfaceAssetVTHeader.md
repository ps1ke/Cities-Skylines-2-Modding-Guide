# Colossal.IO.AssetDatabase.SurfaceAssetVTHeader

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public System.Int32 m_NbVTStacks`  
- `private Colossal.IO.AssetDatabase.PerStackData m_StackData0`  
- `private Colossal.IO.AssetDatabase.PerStackData m_StackData1`  

## Constructors

- `public SurfaceAssetVTHeader(System.Int32 nbVTStacks)`  

## Methods

- `public GetPreProcessedTextureGuid(System.Int32 guidIndex) : Colossal.Hash128`  
- `public GetUnbiasedStackTextureSize(System.Int32 stackIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  
- `public SetPreProcessedTextureGuid(System.Int32 guidIndex, Colossal.Hash128 guid) : System.Void`  
- `public SetTextureGuid(System.Int32 guidIndex, Colossal.Hash128 guid) : System.Void`  
- `public SetUnbiasedStackTextureSize(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  

