# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+MetaElement

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct MetaElement : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.Int32 index;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 shapeWeights;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 textureWeights;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 overlayWeights;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 maskWeights;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationElement animation;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ColorizationElement colorization;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.Int32 index`  

```csharp
public System.Int32 index;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 shapeWeights`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 shapeWeights;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 textureWeights`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 textureWeights;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 overlayWeights`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 overlayWeights;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 maskWeights`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8 maskWeights;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationElement animation`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationElement animation;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ColorizationElement colorization`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ColorizationElement colorization;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


