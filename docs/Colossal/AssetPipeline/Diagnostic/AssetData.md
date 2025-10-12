# Colossal.AssetPipeline.Diagnostic.Report+AssetData

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Diagnostic.ReportBase`  

## Fields

- `public readonly System.String name`  
- `private Colossal.AssetPipeline.Diagnostic.ReportAssetData <assetData>k__BackingField`  
- `public readonly System.Type type`  
- `public readonly System.Boolean generated`  
- `public System.Int32 referenceCount`  
- `private readonly System.Collections.Generic.List<Colossal.AssetPipeline.Diagnostic.Report+FileReport> m_Files`  

## Properties

- `public Colossal.AssetPipeline.Diagnostic.ReportAssetData assetData { get; set }`  
- `public System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.Diagnostic.Report+FileReport> files { get }`  
- `public System.Int32 errorsCount { get }`  
- `public System.Boolean hasErrors { get }`  
- `public System.Int32 warningsCount { get }`  
- `public System.Boolean hasWarnings { get }`  

## Constructors

- `public AssetData(System.String name, System.Type type, System.Boolean generated)`  

## Methods

- `public AddFile(Colossal.AssetPipeline.IAsset asset) : System.Void`  
- `public AddFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset) : System.Void`  
- `public AddFiles(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assets) : System.Void`  
- `public AddFiles(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.IAsset> assets) : System.Void`  
- `public AssignAssetData(Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset asset) : System.Void`  
- `public virtual ToString() : System.String`  

