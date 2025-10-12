# Colossal.AssetPipeline.PostProcessors.IModelPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** interface abstract public  

**Implements:** `Colossal.AssetPipeline.Importers.ISettingable`  

## Properties

- `public System.Int32 priority { get }`  

## Methods

- `public abstract Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  
- `public abstract ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model) : System.Boolean`  

