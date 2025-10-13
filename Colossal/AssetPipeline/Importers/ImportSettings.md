# Colossal.AssetPipeline.Importers.FBXImporter+ImportSettings

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.ISettings`  

## Code

```csharp
public sealed struct ImportSettings : Colossal.AssetPipeline.Importers.ISettings
{
    public System.Double scale;
    public System.Boolean calculateTangents;
    public System.Boolean optimizeForGPU;
    public System.Boolean ignoreMeshName;
    public System.Boolean splitBySubmeshes;

    public static Colossal.AssetPipeline.Importers.FBXImporter+ImportSettings GetDefault();
}
```


## Fields

- `public System.Double scale`  

```csharp
public System.Double scale;
```

- `public System.Boolean calculateTangents`  

```csharp
public System.Boolean calculateTangents;
```

- `public System.Boolean optimizeForGPU`  

```csharp
public System.Boolean optimizeForGPU;
```

- `public System.Boolean ignoreMeshName`  

```csharp
public System.Boolean ignoreMeshName;
```

- `public System.Boolean splitBySubmeshes`  

```csharp
public System.Boolean splitBySubmeshes;
```


## Methods

- `public static GetDefault() : Colossal.AssetPipeline.Importers.FBXImporter+ImportSettings`  

```csharp
public static Colossal.AssetPipeline.Importers.FBXImporter+ImportSettings GetDefault();
```


