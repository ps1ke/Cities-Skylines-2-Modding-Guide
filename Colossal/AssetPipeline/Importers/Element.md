# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct Element : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3 position;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float4 rotation;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3 position`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3 position;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float4 rotation`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float4 rotation;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


