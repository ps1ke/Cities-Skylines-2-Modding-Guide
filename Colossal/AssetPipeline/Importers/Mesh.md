# Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+Mesh

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.AssetPipeline.Importers.Internal.IDeserialize`  

## Code

```csharp
public sealed struct Mesh : Colossal.AssetPipeline.Importers.Internal.IDeserialize
{
    public System.String name;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float2[] uv;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3[] vertices;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3[] normals;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float4[] tangents;
    public System.Int32[] indices;
    public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight4[] boneWeights;

    public System.Int32 vertexCount { get; }
    public System.Int32 indexCount { get; }

    public System.Void Deserialize(System.IO.BinaryReader reader);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float2[] uv`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float2[] uv;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3[] vertices`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3[] vertices;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3[] normals`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float3[] normals;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float4[] tangents`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+float4[] tangents;
```

- `public System.Int32[] indices`  

```csharp
public System.Int32[] indices;
```

- `public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight4[] boneWeights`  

```csharp
public Colossal.AssetPipeline.Importers.DidimoImporter+DidimoData+IndexWeight4[] boneWeights;
```


## Properties

- `public System.Int32 vertexCount { get }`  

```csharp
public System.Int32 vertexCount { get; }
```

- `public System.Int32 indexCount { get }`  

```csharp
public System.Int32 indexCount { get; }
```


## Methods

- `public Deserialize(System.IO.BinaryReader reader) : System.Void`  

```csharp
public System.Void Deserialize(System.IO.BinaryReader reader);
```


