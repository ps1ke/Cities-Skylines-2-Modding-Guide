# Colossal.AssetPipeline.Diagnostic.ReportBase

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Collections.Concurrent.ConcurrentQueue<System.String> m_Errors`  
- `private readonly System.Collections.Concurrent.ConcurrentQueue<System.String> m_Warnings`  
- `private readonly System.Collections.Concurrent.ConcurrentQueue<System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity>> m_Messages`  
- `private readonly System.Collections.Concurrent.ConcurrentQueue<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> m_ImportSteps`  

## Properties

- `public System.Collections.Generic.IReadOnlyCollection<System.String> errors { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<System.String> warnings { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity>> messages { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.AssetPipeline.Diagnostic.Report+ImportStep> steps { get }`  
- `public System.Int32 errorsCount { get }`  
- `public System.Boolean hasErrors { get }`  
- `public System.Int32 warningsCount { get }`  
- `public System.Boolean hasWarnings { get }`  

## Constructors

- `protected ReportBase()`  

## Methods

- `public AddError(System.String message) : System.Void`  
- `public AddImportStep(System.String name) : Colossal.AssetPipeline.Diagnostic.Report+ImportStep`  
- `public AddImportStep(System.String name, Colossal.PerformanceCounter perf) : Colossal.AssetPipeline.Diagnostic.Report+ImportStep`  
- `public AddImportStep(Colossal.AssetPipeline.Diagnostic.Report+ImportStep step) : System.Void`  
- `public AddMessage(System.String message, Colossal.AssetPipeline.Diagnostic.Severity severity = Normal) : System.Void`  
- `public AddMessage(System.ValueTuple<System.String, Colossal.AssetPipeline.Diagnostic.Severity> message) : System.Void`  
- `public AddWarning(System.String message) : System.Void`  

