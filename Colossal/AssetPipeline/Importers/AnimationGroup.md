# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+AnimationGroup

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct AnimationGroup : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RestPose restPose;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+BoneHierarchy boneHierarchy;
    public System.Collections.Generic.List<System.String> paths;
    public System.Int32 shapeCount;
    public System.Int32 boneCount;
    public System.Int32 propBoneCount;
    public System.String styleName;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RestPose restPose`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RestPose restPose;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+BoneHierarchy boneHierarchy`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+BoneHierarchy boneHierarchy;
```

- `public System.Collections.Generic.List<System.String> paths`  

```csharp
public System.Collections.Generic.List<System.String> paths;
```

- `public System.Int32 shapeCount`  

```csharp
public System.Int32 shapeCount;
```

- `public System.Int32 boneCount`  

```csharp
public System.Int32 boneCount;
```

- `public System.Int32 propBoneCount`  

```csharp
public System.Int32 propBoneCount;
```

- `public System.String styleName`  

```csharp
public System.String styleName;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


