# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Material

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct Material : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.String name;
    public System.String shader;
    public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Material+Texture> textures;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public System.String shader`  

```csharp
public System.String shader;
```

- `public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Material+Texture> textures`  

```csharp
public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Material+Texture> textures;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


## Nested types

- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Material+Texture`  

