# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Group

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct Group : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.String name;
    public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Character> characters;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Character> characters`  

```csharp
public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Character> characters;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


