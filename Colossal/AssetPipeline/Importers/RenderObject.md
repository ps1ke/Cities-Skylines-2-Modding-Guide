# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderObject

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct RenderObject : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.Int32 boneCount;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Mesh mesh;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Material material;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ShapeBuffer shapeBuffer;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.Int32 boneCount`  

```csharp
public System.Int32 boneCount;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Mesh mesh`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Mesh mesh;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Material material`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Material material;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ShapeBuffer shapeBuffer`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ShapeBuffer shapeBuffer;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


