# Colossal.AssetPipeline.Diagnostic.Report

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Diagnostic.ReportBase`  

## Fields

- `public System.TimeSpan totalTime`  
- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+Asset> m_Assets`  
- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+Prefab> m_Prefabs`  
- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+AssetData> m_AssetDatas`  
- `private static System.Collections.Concurrent.ConcurrentDictionary<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport> s_FileMap`  

## Properties

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+Asset> assets { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+Prefab> prefabs { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+AssetData> assetDatas { get }`  
- `public System.Int32 errorsCount { get }`  
- `public System.Boolean hasErrors { get }`  
- `public System.Int32 warningsCount { get }`  
- `public System.Boolean hasWarnings { get }`  

## Constructors

- `public Report()`  

## Methods

- `public AddAsset(System.String name) : Colossal.AssetPipeline.Diagnostic.Report+Asset`  
- `public AddAssetData(System.String name, System.Type type, System.Boolean generated = False) : Colossal.AssetPipeline.Diagnostic.Report+AssetData`  
- `public AddInfoToAsset(System.String name, System.Type type, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset asset) : System.Void`  
- `public AddPrefab(System.String name) : Colossal.AssetPipeline.Diagnostic.Report+Prefab`  
- `public GetAssetData(System.String name, System.Type type) : Colossal.AssetPipeline.Diagnostic.Report+AssetData`  
- `public GetFileReport(Colossal.AssetPipeline.IAsset asset) : Colossal.AssetPipeline.Diagnostic.Report+FileReport`  
- `public Log(Colossal.Logging.ILog log) : System.Void`  
- `public Log(Colossal.Logging.ILog log, Colossal.AssetPipeline.Diagnostic.Severity overrideSeverity) : System.Void`  
- `public static PrintReportBase(Colossal.IndentedStringBuilder builder, Colossal.AssetPipeline.Diagnostic.ReportBase step, Colossal.AssetPipeline.Diagnostic.Severity severity) : System.Void`  
- `public static PrintSteps(Colossal.IndentedStringBuilder builder, System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps, Colossal.AssetPipeline.Diagnostic.Severity severity) : System.Void`  
- `public virtual ToString() : System.String`  
- `public ToString(Colossal.AssetPipeline.Diagnostic.Severity severity) : System.String`  
- `private static UniqueSteps(System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps) : System.Collections.Generic.ICollection<System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, System.Int32>>`  

## Nested types

- `Colossal.AssetPipeline.Diagnostic.Report+IFile`  
- `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`  
- `Colossal.AssetPipeline.Diagnostic.Report+ImportStep`  
- `Colossal.AssetPipeline.Diagnostic.Report+AssetData`  
- `Colossal.AssetPipeline.Diagnostic.Report+Prefab`  
- `Colossal.AssetPipeline.Diagnostic.Report+Asset`  
- `Colossal.AssetPipeline.Diagnostic.Report+FileReport`  
- `Colossal.AssetPipeline.Diagnostic.Report+<>c__DisplayClass12_0`  
- `Colossal.AssetPipeline.Diagnostic.Report+<>c__DisplayClass13_0`  
- `Colossal.AssetPipeline.Diagnostic.Report+<>c__DisplayClass14_0`  

