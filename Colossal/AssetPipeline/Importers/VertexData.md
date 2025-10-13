# Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData>`  

## Code

```csharp
public class VertexData : System.IComparable<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData>
{
    private UnityEngine.Rendering.VertexAttribute <attribute>k__BackingField;
    private UnityEngine.Rendering.VertexAttributeFormat <format>k__BackingField;
    private System.Int32 <dimension>k__BackingField;
    private Unity.Collections.NativeArray<System.Byte> <data>k__BackingField;
    private System.Boolean <isPacked>k__BackingField;

    public UnityEngine.Rendering.VertexAttribute attribute { get; private set; }
    public UnityEngine.Rendering.VertexAttributeFormat format { get; private set; }
    public System.Int32 dimension { get; private set; }
    public Unity.Collections.NativeArray<System.Byte> data { get; private set; }
    public System.Boolean isPacked { get; private set; }
    public System.Int32 elementSize { get; }

    public VertexData(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension, Unity.Collections.NativeArray<System.Byte> data, System.Boolean isPacked);

    public System.Void ChangeAttribute(UnityEngine.Rendering.VertexAttribute attribute);
    public System.Int32 CompareTo(Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData other);
    public System.Boolean Convert(UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
    public System.Void Dispose();
    public System.Void SetNewData<T>(Unity.Collections.NativeArray<T> newData);
}
```


## Fields

- `private UnityEngine.Rendering.VertexAttribute <attribute>k__BackingField`  

```csharp
private UnityEngine.Rendering.VertexAttribute <attribute>k__BackingField;
```

- `private UnityEngine.Rendering.VertexAttributeFormat <format>k__BackingField`  

```csharp
private UnityEngine.Rendering.VertexAttributeFormat <format>k__BackingField;
```

- `private System.Int32 <dimension>k__BackingField`  

```csharp
private System.Int32 <dimension>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Byte> <data>k__BackingField`  

```csharp
private Unity.Collections.NativeArray<System.Byte> <data>k__BackingField;
```

- `private System.Boolean <isPacked>k__BackingField`  

```csharp
private System.Boolean <isPacked>k__BackingField;
```


## Properties

- `public UnityEngine.Rendering.VertexAttribute attribute { get; private set }`  

```csharp
public UnityEngine.Rendering.VertexAttribute attribute { get; private set; }
```

- `public UnityEngine.Rendering.VertexAttributeFormat format { get; private set }`  

```csharp
public UnityEngine.Rendering.VertexAttributeFormat format { get; private set; }
```

- `public System.Int32 dimension { get; private set }`  

```csharp
public System.Int32 dimension { get; private set; }
```

- `public Unity.Collections.NativeArray<System.Byte> data { get; private set }`  

```csharp
public Unity.Collections.NativeArray<System.Byte> data { get; private set; }
```

- `public System.Boolean isPacked { get; private set }`  

```csharp
public System.Boolean isPacked { get; private set; }
```

- `public System.Int32 elementSize { get }`  

```csharp
public System.Int32 elementSize { get; }
```


## Constructors

- `public VertexData(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension, Unity.Collections.NativeArray<System.Byte> data, System.Boolean isPacked = False)`  

```csharp
public VertexData(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension, Unity.Collections.NativeArray<System.Byte> data, System.Boolean isPacked);
```


## Methods

- `public ChangeAttribute(UnityEngine.Rendering.VertexAttribute attribute) : System.Void`  

```csharp
public System.Void ChangeAttribute(UnityEngine.Rendering.VertexAttribute attribute);
```

- `public CompareTo(Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData other);
```

- `public Convert(UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Boolean`  

```csharp
public System.Boolean Convert(UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public SetNewData<T>(Unity.Collections.NativeArray<T> newData) : System.Void`  

```csharp
public System.Void SetNewData<T>(Unity.Collections.NativeArray<T> newData);
```


