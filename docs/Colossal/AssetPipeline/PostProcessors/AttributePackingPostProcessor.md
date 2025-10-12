# Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor`, `Colossal.AssetPipeline.Importers.ISettingable`  

**Attributes:** `BurstCompile`  

## Fields

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfExecute`  

## Properties

- `public System.Int32 priority { get }`  

## Constructors

- `public AttributePackingPostProcessor()`  

## Methods

- `private static ArrayFloat4ToUnorm(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count) : System.Void`  
- `public static ArrayFloat4ToUnorm$BurstManaged(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count) : System.Void`  
- `private static ArrayUInt32To8(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count) : System.Void`  
- `public static ArrayUInt32To8$BurstManaged(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& dstData, System.Int32 count) : System.Void`  
- `private static ArrayUInt4MaxValue(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, System.Int32 count) : System.UInt32`  
- `public static ArrayUInt4MaxValue$BurstManaged(Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& srcData, System.Int32 count) : System.UInt32`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `private Execute(Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.ModelAsset modelAsset, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  
- `public Execute(Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+PostProcessSettings settings, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> assets, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  
- `public GetDefaultSettings() : Colossal.AssetPipeline.Importers.ISettings`  
- `private static PackFloatAttribute(Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.ISurface surface, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData attr, System.Int32 vertexCount) : System.Void`  
- `public static PackModel(Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+PostProcessSettings settings, Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.ISurface surface) : System.Void`  
- `private static PackUIntAttribute(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData attr, System.Int32 vertexCount) : System.Void`  
- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface) : System.Boolean`  
- `public ShouldExecute(Colossal.AssetPipeline.Importers.ISettings settings, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface) : System.Boolean`  
- `public ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+PostProcessSettings`  
- `Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+Colossal.AssetPipeline.PostProcessors.ArrayFloat4ToUnorm_0000011D$PostfixBurstDelegate`  
- `Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+Colossal.AssetPipeline.PostProcessors.ArrayFloat4ToUnorm_0000011D$BurstDirectCall`  
- `Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+Colossal.AssetPipeline.PostProcessors.ArrayUInt32To8_0000011E$PostfixBurstDelegate`  
- `Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+Colossal.AssetPipeline.PostProcessors.ArrayUInt32To8_0000011E$BurstDirectCall`  
- `Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+Colossal.AssetPipeline.PostProcessors.ArrayUInt4MaxValue_0000011F$PostfixBurstDelegate`  
- `Colossal.AssetPipeline.PostProcessors.AttributePackingPostProcessor+Colossal.AssetPipeline.PostProcessors.ArrayUInt4MaxValue_0000011F$BurstDirectCall`  

