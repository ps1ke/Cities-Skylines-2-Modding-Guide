# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct Animation : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.String name;
    public System.String targetName;
    public System.Int32 animationType;
    public System.Int32[] shapeIndices;
    public System.Int32[] boneIndices;
    public System.Int32 fps;
    public System.Int32 frameCount;
    public System.Int32 layerIndex;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element[] elements;
    public System.Int32 anchorBoneIndex;
    public System.Int32 anchorTargetBoneIndex;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public System.String targetName`  

```csharp
public System.String targetName;
```

- `public System.Int32 animationType`  

```csharp
public System.Int32 animationType;
```

- `public System.Int32[] shapeIndices`  

```csharp
public System.Int32[] shapeIndices;
```

- `public System.Int32[] boneIndices`  

```csharp
public System.Int32[] boneIndices;
```

- `public System.Int32 fps`  

```csharp
public System.Int32 fps;
```

- `public System.Int32 frameCount`  

```csharp
public System.Int32 frameCount;
```

- `public System.Int32 layerIndex`  

```csharp
public System.Int32 layerIndex;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element[] elements`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element[] elements;
```

- `public System.Int32 anchorBoneIndex`  

```csharp
public System.Int32 anchorBoneIndex;
```

- `public System.Int32 anchorTargetBoneIndex`  

```csharp
public System.Int32 anchorTargetBoneIndex;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


## Nested types

- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+Element`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation+PropAnimation`  

