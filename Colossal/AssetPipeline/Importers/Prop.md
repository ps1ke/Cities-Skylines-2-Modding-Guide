# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Prop

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Prop : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.String name;
    public System.Int32 renderGroupIndex;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+BoneHierarchy boneHierarchy;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RestPose restPose;
    public static Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Prop empty;

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public System.Int32 renderGroupIndex`  

```csharp
public System.Int32 renderGroupIndex;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+BoneHierarchy boneHierarchy`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+BoneHierarchy boneHierarchy;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RestPose restPose`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+RestPose restPose;
```

- `public static Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Prop empty`  

```csharp
public static Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Prop empty;
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


