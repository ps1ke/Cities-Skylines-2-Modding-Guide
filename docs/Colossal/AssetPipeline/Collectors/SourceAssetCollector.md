# Colossal.AssetPipeline.Collectors.SourceAssetCollector

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Collectors`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>>`, `System.Collections.IEnumerable`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly System.Collections.Generic.HashSet<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>> m_AssetList`  

## Properties

- `public System.Int32 count { get }`  

## Constructors

- `public SourceAssetCollector(System.String projectRootPath, System.String relativePath)`  
- `public SourceAssetCollector(System.String projectRootPath, System.Collections.Generic.IEnumerable<System.String> relativePaths)`  

## Methods

- `private static GetDirectories(System.String path, System.String projectRootPath, System.Collections.Generic.HashSet`1[[Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup`1[[Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& assetList) : System.Void`  
- `public GetEnumerator() : System.Collections.Generic.HashSet<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>>`  
- `private static Internal_GetDirectories(System.String path) : System.Collections.Generic.IEnumerable<System.String>`  
- `private static Internal_GetFiles(System.String path) : System.Collections.Generic.IEnumerable<System.String>`  
- `private System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector.AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector.Asset>>.GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>>`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

## Nested types

- `Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset`  
- `Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<T>`  
- `Colossal.AssetPipeline.Collectors.SourceAssetCollector+<>c`  

