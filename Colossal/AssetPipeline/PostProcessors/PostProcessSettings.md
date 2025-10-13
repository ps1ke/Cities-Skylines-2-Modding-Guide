# Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.ISettings`  

## Code

```csharp
public sealed struct PostProcessSettings : Colossal.AssetPipeline.Importers.ISettings
{
    public System.String materialTemplate;
    public System.Boolean needsAlpha;
    public System.Boolean needsAlphaClip;
    public System.Boolean doubleSided;
    public System.Collections.Generic.Dictionary<System.String, System.Single> floatProperties;
    public System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> colorProperties;
    public System.Collections.Generic.List<System.String> keywords;

    public static Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings GetDefault();
}
```


## Fields

- `public System.String materialTemplate`  

```csharp
public System.String materialTemplate;
```

- `public System.Boolean needsAlpha`  

```csharp
public System.Boolean needsAlpha;
```

- `public System.Boolean needsAlphaClip`  

```csharp
public System.Boolean needsAlphaClip;
```

- `public System.Boolean doubleSided`  

```csharp
public System.Boolean doubleSided;
```

- `public System.Collections.Generic.Dictionary<System.String, System.Single> floatProperties`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Single> floatProperties;
```

- `public System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> colorProperties`  

```csharp
public System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> colorProperties;
```

- `public System.Collections.Generic.List<System.String> keywords`  

```csharp
public System.Collections.Generic.List<System.String> keywords;
```


## Methods

- `public static GetDefault() : Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings`  

```csharp
public static Colossal.AssetPipeline.PostProcessors.SurfacePostProcessor+PostProcessSettings GetDefault();
```


