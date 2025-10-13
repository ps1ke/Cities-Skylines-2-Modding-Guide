# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RestPose

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct RestPose : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element[] elements;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element[] elements`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element[] elements;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


