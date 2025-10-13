# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Character

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct Character : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.Int32 index;
    public System.Int32 styleIndex;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+MetaElement meta;
    public System.Collections.Generic.List<System.Int32> renderObjectIndices;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.Int32 index`  

```csharp
public System.Int32 index;
```

- `public System.Int32 styleIndex`  

```csharp
public System.Int32 styleIndex;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+MetaElement meta`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+MetaElement meta;
```

- `public System.Collections.Generic.List<System.Int32> renderObjectIndices`  

```csharp
public System.Collections.Generic.List<System.Int32> renderObjectIndices;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


