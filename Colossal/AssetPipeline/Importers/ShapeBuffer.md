# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ShapeBuffer

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct ShapeBuffer : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.Int32 stride;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ShapeBuffer+Element[] elements;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.Int32 stride`  

```csharp
public System.Int32 stride;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ShapeBuffer+Element[] elements`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ShapeBuffer+Element[] elements;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


## Nested types

- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ShapeBuffer+Element`  

