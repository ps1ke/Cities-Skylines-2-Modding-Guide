# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class DidimoData
{
    public System.Int32 version;
    public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Texture> textures;
    public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Group> groups;
    public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Prop> props;
    public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderGroup> renderGroups;
    public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationGroup> animationGroups;
    public System.Collections.Generic.List<System.String> textureOverlays;
    public System.Collections.Generic.List<System.String> skinMasks;
    public System.Int32 key;
    private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField;
    public static const System.Int32 kFileFormatKey;

    public System.Boolean isValid { get; }
    public Colossal.AssetPipeline.IAsset sourceAsset { get; set; }

    public DidimoData();

    public static Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.Int32 version`  

```csharp
public System.Int32 version;
```

- `public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Texture> textures`  

```csharp
public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Texture> textures;
```

- `public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Group> groups`  

```csharp
public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Group> groups;
```

- `public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Prop> props`  

```csharp
public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Prop> props;
```

- `public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderGroup> renderGroups`  

```csharp
public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderGroup> renderGroups;
```

- `public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationGroup> animationGroups`  

```csharp
public System.Collections.Generic.List<Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationGroup> animationGroups;
```

- `public System.Collections.Generic.List<System.String> textureOverlays`  

```csharp
public System.Collections.Generic.List<System.String> textureOverlays;
```

- `public System.Collections.Generic.List<System.String> skinMasks`  

```csharp
public System.Collections.Generic.List<System.String> skinMasks;
```

- `public System.Int32 key`  

```csharp
public System.Int32 key;
```

- `private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField`  

```csharp
private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField;
```

- `public static const System.Int32 kFileFormatKey`  

```csharp
public static const System.Int32 kFileFormatKey;
```


## Properties

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```

- `public Colossal.AssetPipeline.IAsset sourceAsset { get; set }`  

```csharp
public Colossal.AssetPipeline.IAsset sourceAsset { get; set; }
```


## Constructors

- `public DidimoData()`  

```csharp
public DidimoData();
```


## Methods

- `public static Deserialize(System.IO.BinaryReader reader) : Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData`  

```csharp
public static Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData Deserialize(System.IO.BinaryReader reader);
```


## Nested types

- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Texture`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Group`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Character`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+MetaElement`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationElement`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationLayerElement`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight8`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight4`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ColorizationElement`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderGroup`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RenderObject`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Prop`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+ShapeBuffer`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Mesh`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float2`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float4`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Material`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationGroup`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RestPose`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+BoneHierarchy`  
- `Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Animation`  

