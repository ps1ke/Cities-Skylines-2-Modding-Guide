# Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static ByteArrayToStructure<T>(System.Byte[] bytes) : T`  
- `private static CopyData(System.UInt32 nbDstBlockRows, System.UInt32 nbDstBlockColumns, System.Int32 blockSizeInBytes, Unity.Collections.NativeSlice<System.Byte> bytes, Unity.Collections.NativeSlice<System.Byte> dstData, System.Int32 srcRowOffsetInBlocks, System.Int32 srcColumnOffsetInBlocks, System.Int32 rectHeightBlocks, System.Int32 rectWidthBlocks, System.Int32 scanlineSize, System.Int32 srcMipBlockOffset, System.Int32 destinationOffset) : System.Void`  
- `private static CopyFromTextureData(System.Int32 level, System.Int32 textureX, System.Int32 textureY, System.Int32 reqWidth, System.Int32 reqHeight, Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeSlice<System.Byte> dstData, System.Int32 textureWidth, System.Int32 textureHeight, System.Boolean requiresCachedMip, System.Int32 scanlineSize, System.Int32 dstOffset, System.Int32 trilinearDstOffset, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo) : System.Void`  
- `public static GetBiasedSize(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize unbiasedSize, System.Int32 mipBias, System.Int32 tileSize) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  
- `public static IsPowerOf2(System.Int32 x) : System.Boolean`  
- `public static PreProcessData(Unity.Collections.NativeSlice<System.Byte> data, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& processedData, System.Int32 textureWidth, System.Int32 textureHeight, System.Int32 preprocessedTileSize, System.Int32 maxLevel, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo) : System.Void`  
- `private static PreProcessData(Unity.Collections.NativeSlice<System.Byte> data, Unity.Collections.NativeArray<System.Byte> processedData, System.Int32 textureWidth, System.Int32 textureHeight, System.Int32 preprocessedTileSize, System.Int32 maxLevel, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 totalBlockSize, System.Int32 textureBlockOffsetInBytes) : System.Void`  
- `public static SimpleCopy(Unity.Collections.NativeSlice<System.Byte> srcData, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 startSrcBlockOffset, System.Int32 startDstBlockOffset, System.Int32 nbBlockColumns, System.Int32 nbBlockRows, System.Int32 readScanlineInBlocks, System.Int32 writeScanlineInBlocks, System.Int32 blockSizeInBytes) : System.Void`  
- `public static TextureRelativeTileIndex(System.Int32 textureWidth, System.Int32 textureHeight, System.Int32 level, System.Int32 xPixels, System.Int32 yPixels, System.Int32 tileSize) : System.Int32`  
- `public static TextureRelativeTileIndex(System.Int32 textureWidth, System.Int32 textureHeight, System.Int32 rectWidth, System.Int32 rectHeight, System.Int32 level, System.Int32 xPixels, System.Int32 yPixels, System.Int32 tileSize) : System.Int32`  
- `public static WriteMidMip(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, Unity.Collections.NativeSlice<System.Byte> srcData, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 midMipLevel, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords internalDstCoords, System.Int32 srcColumn, System.Int32 scrRow, System.Int32 nbScrColumns, System.Int32 nbSrcRows) : System.Void`  
- `public static WriteMipsSmallerThanBlockSize(Unity.Collections.NativeArray<System.Byte> srcData, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 textureWidth, System.Int32 textureHeight, System.Int32 level, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 dstOffsetInBytes) : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo`  

