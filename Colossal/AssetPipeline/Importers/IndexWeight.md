# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct IndexWeight : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.Int32 index;
    public System.Single weight;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.Int32 index`  

```csharp
public System.Int32 index;
```

- `public System.Single weight`  

```csharp
public System.Single weight;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


