# Colossal.AssetPipeline.PostProcessors.IModelPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** interface abstract public  

**Implements:** `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public abstract interface IModelPostProcessor : Colossal.AssetPipeline.Importers.ISettingable
{
    public System.Int32 priority { get; }

    public abstract System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
    public abstract System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model);
}
```


## Properties

- `public System.Int32 priority { get }`  

```csharp
public System.Int32 priority { get; }
```


## Methods

- `public abstract Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report) : System.Void`  

```csharp
public abstract System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model, Colossal.AssetPipeline.Diagnostic.Report+FileReport report);
```

- `public abstract ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model) : System.Boolean`  

```csharp
public abstract System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, Colossal.AssetPipeline.ModelAsset model);
```


