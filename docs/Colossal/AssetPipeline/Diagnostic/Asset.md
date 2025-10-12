# Colossal.AssetPipeline.Diagnostic.Report+Asset

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Diagnostic.ReportBase`  

## Fields

- `public readonly System.String name`  
- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+FileReport> m_Files`  

## Properties

- `public System.Int32 errorsCount { get }`  
- `public System.Boolean hasErrors { get }`  
- `public System.Int32 warningsCount { get }`  
- `public System.Boolean hasWarnings { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+FileReport> files { get }`  

## Constructors

- `public Asset(System.String name)`  

## Methods

- `public AddFile(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset) : Colossal.AssetPipeline.Diagnostic.Report+FileReport`  
- `public AddFile(Colossal.AssetPipeline.IAsset asset) : Colossal.AssetPipeline.Diagnostic.Report+FileReport`  

