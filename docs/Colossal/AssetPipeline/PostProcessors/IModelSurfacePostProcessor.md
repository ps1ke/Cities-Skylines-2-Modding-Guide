# Colossal.AssetPipeline.PostProcessors.IModelSurfacePostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** interface abstract public  

**Implements:** `Colossal.AssetPipeline.Importers.ISettingable`  

## Properties

- `public System.Int32 priority { get }`  

## Methods

- `public abstract Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+FileReport, Colossal.AssetPipeline.Diagnostic.Report+AssetData> report) : System.Void`  
- `public abstract ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, System.Int32 modelIndex, Colossal.AssetPipeline.Surface surface) : System.Boolean`  

