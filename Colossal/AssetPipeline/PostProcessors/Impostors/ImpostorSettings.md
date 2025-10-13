# Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Impostors`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.ISettings`  

## Code

```csharp
public sealed struct ImpostorSettings : Colossal.AssetPipeline.Importers.ISettings
{
    public System.Boolean hemiSpherical;
    public System.Int32 frames;
    public System.Boolean tightBounds;
    public System.Single tightMesh;
    public System.Int32 resolution;
    public System.Int32 dilate;

    public static Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings GetDefault();
}
```


## Fields

- `public System.Boolean hemiSpherical`  

```csharp
public System.Boolean hemiSpherical;
```

- `public System.Int32 frames`  

```csharp
public System.Int32 frames;
```

- `public System.Boolean tightBounds`  

```csharp
public System.Boolean tightBounds;
```

- `public System.Single tightMesh`  

```csharp
public System.Single tightMesh;
```

- `public System.Int32 resolution`  

```csharp
public System.Int32 resolution;
```

- `public System.Int32 dilate`  

```csharp
public System.Int32 dilate;
```


## Methods

- `public static GetDefault() : Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings`  

```csharp
public static Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings GetDefault();
```


