# Colossal.AssetPipeline.PostProcessors.IGeometryPostProcessor

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** interface abstract public  

**Implements:** `Colossal.AssetPipeline.Importers.ISettingable`  

## Code

```csharp
public abstract interface IGeometryPostProcessor : Colossal.AssetPipeline.Importers.ISettingable
{
    public System.Int32 priority { get; }

    public abstract System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
    public abstract System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset);
}
```


## Properties

- `public System.Int32 priority { get }`  

```csharp
public System.Int32 priority { get; }
```


## Methods

- `public abstract Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report) : System.Void`  

```csharp
public abstract System.Void Execute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset, Colossal.AssetPipeline.Diagnostic.Report+AssetData, Colossal.AssetPipeline.Diagnostic.Report+AssetData[]> report);
```

- `public abstract ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset) : System.Boolean`  

```csharp
public abstract System.Boolean ShouldExecute(Colossal.AssetPipeline.PostProcessors.Context context, System.Collections.Generic.List<Colossal.AssetPipeline.LOD> asset);
```


