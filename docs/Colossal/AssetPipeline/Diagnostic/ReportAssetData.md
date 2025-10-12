# Colossal.AssetPipeline.Diagnostic.ReportAssetData

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

**Attributes:** `IsReadOnly`  

## Fields

- `public readonly System.String path`  
- `public readonly System.Int64 size`  
- `public readonly Colossal.Hash128 guid`  
- `public readonly System.Type type`  
- `public readonly System.Boolean generated`  

## Properties

- `private System.String Colossal.AssetPipeline.Diagnostic.Report.IFile.path { private get }`  
- `private System.Int64 Colossal.AssetPipeline.Diagnostic.Report.IFile.size { private get }`  
- `private Colossal.Hash128 Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.guid { private get }`  
- `private System.Type Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.type { private get }`  

## Constructors

- `public ReportAssetData(Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset data, System.Boolean generated)`  

## Methods

- `public virtual ToString() : System.String`  

