# Colossal.AssetPipeline.ModelAsset

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Asset<Colossal.AssetPipeline.Importers.ModelImporter, Colossal.AssetPipeline.Importers.ModelImporter+ModelList>`  
**Implements:** `Colossal.AssetPipeline.IAsset`, `System.IEquatable<Colossal.AssetPipeline.IAsset>`, `System.IEquatable<Colossal.AssetPipeline.ModelAsset>`  

## Code

```csharp
public class ModelAsset : Colossal.AssetPipeline.Asset<Colossal.AssetPipeline.Importers.ModelImporter, Colossal.AssetPipeline.Importers.ModelImporter+ModelList>, Colossal.AssetPipeline.IAsset, System.IEquatable<Colossal.AssetPipeline.IAsset>, System.IEquatable<Colossal.AssetPipeline.ModelAsset>
{
    public ModelAsset(System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset, Colossal.AssetPipeline.Importers.ModelImporter importer, System.Boolean validateFileName);

    public static Colossal.AssetPipeline.ModelAsset CreateDummy(System.String name, System.String dummyPath, System.Boolean validateFileName);
    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Colossal.AssetPipeline.ModelAsset other);
    public virtual System.Int32 GetHashCode();
}
```


## Constructors

- `public ModelAsset(System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset, Colossal.AssetPipeline.Importers.ModelImporter importer, System.Boolean validateFileName)`  

```csharp
public ModelAsset(System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset, Colossal.AssetPipeline.Importers.ModelImporter importer, System.Boolean validateFileName);
```


## Methods

- `public static CreateDummy(System.String name, System.String dummyPath, System.Boolean validateFileName) : Colossal.AssetPipeline.ModelAsset`  

```csharp
public static Colossal.AssetPipeline.ModelAsset CreateDummy(System.String name, System.String dummyPath, System.Boolean validateFileName);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Colossal.AssetPipeline.ModelAsset other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.AssetPipeline.ModelAsset other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


