# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+BoneHierarchy

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct BoneHierarchy : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.Int32[] hierarchyParentIndices;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.Int32[] hierarchyParentIndices`  

```csharp
public System.Int32[] hierarchyParentIndices;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


