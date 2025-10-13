# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderGroup

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct RenderGroup : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderObject[] renderObjects;
    public System.String bodyParts;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderObject[] renderObjects`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderObject[] renderObjects;
```

- `public System.String bodyParts`  

```csharp
public System.String bodyParts;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


