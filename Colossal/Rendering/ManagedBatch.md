# Colossal.Rendering.ManagedBatch

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class ManagedBatch : System.IDisposable
{
    private System.Int32 <groupIndex>k__BackingField;
    private System.Int32 <batchIndex>k__BackingField;
    private UnityEngine.Material <material>k__BackingField;
    private UnityEngine.Mesh <mesh>k__BackingField;
    private System.Int32 <subMeshIndex>k__BackingField;
    private UnityEngine.MaterialPropertyBlock <customProps>k__BackingField;
    private UnityEngine.Rendering.BatchMaterialID <materialID>k__BackingField;
    private UnityEngine.Rendering.BatchMeshID <meshID>k__BackingField;

    public System.Int32 groupIndex { get; internal set; }
    public System.Int32 batchIndex { get; internal set; }
    public UnityEngine.Material material { get; internal set; }
    public UnityEngine.Mesh mesh { get; internal set; }
    public System.Int32 subMeshIndex { get; internal set; }
    public UnityEngine.MaterialPropertyBlock customProps { get; internal set; }
    public UnityEngine.Rendering.BatchMaterialID materialID { get; internal set; }
    public UnityEngine.Rendering.BatchMeshID meshID { get; internal set; }

    public ManagedBatch(System.Int32 groupIndex, System.Int32 batchIndex, UnityEngine.Material material, UnityEngine.Mesh mesh, System.Int32 subMeshIndex, UnityEngine.MaterialPropertyBlock customProps);

    public virtual System.Void Dispose();
}
```


## Fields

- `private System.Int32 <groupIndex>k__BackingField`  

```csharp
private System.Int32 <groupIndex>k__BackingField;
```

- `private System.Int32 <batchIndex>k__BackingField`  

```csharp
private System.Int32 <batchIndex>k__BackingField;
```

- `private UnityEngine.Material <material>k__BackingField`  

```csharp
private UnityEngine.Material <material>k__BackingField;
```

- `private UnityEngine.Mesh <mesh>k__BackingField`  

```csharp
private UnityEngine.Mesh <mesh>k__BackingField;
```

- `private System.Int32 <subMeshIndex>k__BackingField`  

```csharp
private System.Int32 <subMeshIndex>k__BackingField;
```

- `private UnityEngine.MaterialPropertyBlock <customProps>k__BackingField`  

```csharp
private UnityEngine.MaterialPropertyBlock <customProps>k__BackingField;
```

- `private UnityEngine.Rendering.BatchMaterialID <materialID>k__BackingField`  

```csharp
private UnityEngine.Rendering.BatchMaterialID <materialID>k__BackingField;
```

- `private UnityEngine.Rendering.BatchMeshID <meshID>k__BackingField`  

```csharp
private UnityEngine.Rendering.BatchMeshID <meshID>k__BackingField;
```


## Properties

- `public System.Int32 groupIndex { get; internal set }`  

```csharp
public System.Int32 groupIndex { get; internal set; }
```

- `public System.Int32 batchIndex { get; internal set }`  

```csharp
public System.Int32 batchIndex { get; internal set; }
```

- `public UnityEngine.Material material { get; internal set }`  

```csharp
public UnityEngine.Material material { get; internal set; }
```

- `public UnityEngine.Mesh mesh { get; internal set }`  

```csharp
public UnityEngine.Mesh mesh { get; internal set; }
```

- `public System.Int32 subMeshIndex { get; internal set }`  

```csharp
public System.Int32 subMeshIndex { get; internal set; }
```

- `public UnityEngine.MaterialPropertyBlock customProps { get; internal set }`  

```csharp
public UnityEngine.MaterialPropertyBlock customProps { get; internal set; }
```

- `public UnityEngine.Rendering.BatchMaterialID materialID { get; internal set }`  

```csharp
public UnityEngine.Rendering.BatchMaterialID materialID { get; internal set; }
```

- `public UnityEngine.Rendering.BatchMeshID meshID { get; internal set }`  

```csharp
public UnityEngine.Rendering.BatchMeshID meshID { get; internal set; }
```


## Constructors

- `public ManagedBatch(System.Int32 groupIndex, System.Int32 batchIndex, UnityEngine.Material material, UnityEngine.Mesh mesh, System.Int32 subMeshIndex, UnityEngine.MaterialPropertyBlock customProps)`  

```csharp
public ManagedBatch(System.Int32 groupIndex, System.Int32 batchIndex, UnityEngine.Material material, UnityEngine.Mesh mesh, System.Int32 subMeshIndex, UnityEngine.MaterialPropertyBlock customProps);
```


## Methods

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```


