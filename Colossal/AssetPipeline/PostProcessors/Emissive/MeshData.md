# Colossal.AssetPipeline.PostProcessors.Emissive.MeshData

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class MeshData
{
    private Colossal.AssetPipeline.PostProcessors.Emissive.MeshData+AttrData[] attributes;

    public MeshData(Colossal.AssetPipeline.Importers.ModelImporter+Model mesh);

    public System.Int32 CopyVertex(System.Int32 srcIndex);
    public System.Void UpdateMesh(Colossal.AssetPipeline.Importers.ModelImporter+Model mesh);
}
```


## Fields

- `private Colossal.AssetPipeline.PostProcessors.Emissive.MeshData+AttrData[] attributes`  

```csharp
private Colossal.AssetPipeline.PostProcessors.Emissive.MeshData+AttrData[] attributes;
```


## Constructors

- `public MeshData(Colossal.AssetPipeline.Importers.ModelImporter+Model mesh)`  

```csharp
public MeshData(Colossal.AssetPipeline.Importers.ModelImporter+Model mesh);
```


## Methods

- `public CopyVertex(System.Int32 srcIndex) : System.Int32`  

```csharp
public System.Int32 CopyVertex(System.Int32 srcIndex);
```

- `public UpdateMesh(Colossal.AssetPipeline.Importers.ModelImporter+Model mesh) : System.Void`  

```csharp
public System.Void UpdateMesh(Colossal.AssetPipeline.Importers.ModelImporter+Model mesh);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Emissive.MeshData+AttrData`  

