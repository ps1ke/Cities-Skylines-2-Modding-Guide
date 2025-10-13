# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+PropAnimation

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct PropAnimation : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.String propName;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element[] elements;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.String propName`  

```csharp
public System.String propName;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element[] elements`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element[] elements;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


