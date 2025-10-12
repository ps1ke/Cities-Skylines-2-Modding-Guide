# Colossal.IO.AssetDatabase.VirtualTexturing.ZOrderer

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Int32 m_TotalSize`  
- `private System.Int32 m_Index`  
- `private static readonly System.Int32[] Morton2dLut`  

## Properties

- `public System.Int32 TotalNbBlocks { get }`  
- `public System.Int32 NbReservedBlocks { get }`  

## Constructors

- `public ZOrderer(System.Int32 totalSize)`  

## Methods

- `public CanAllocate(System.Int32 nbIndices) : System.Boolean`  
- `private static CompactBits(System.Int64 n) : System.Int64`  
- `private static Decode(System.Int64 key) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords`  
- `private static Encode(System.Int32 x, System.Int32 y) : System.Int32`  
- `public static GetCoords(System.Int32 index) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords`  
- `public static GetIndex(System.Int32 column, System.Int32 row) : System.Int32`  
- `public ReserveMultipleRects(System.Int32 nbIndices) : System.Int32`  

