# Colossal.IO.AssetDatabase.GeometryAsset+SubMeshInfo

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SubMeshInfo
{
    private System.Int32 indexStart;
    private System.Int32 indexCount;
    private System.Int32 firstVertex;
    private System.Int32 vertexCount;
    private UnityEngine.Bounds bounds;

    public SubMeshInfo(UnityEngine.Rendering.SubMeshDescriptor sm);

    public UnityEngine.Rendering.SubMeshDescriptor ToSubMeshDescriptor();
}
```


## Fields

- `private System.Int32 indexStart`  

```csharp
private System.Int32 indexStart;
```

- `private System.Int32 indexCount`  

```csharp
private System.Int32 indexCount;
```

- `private System.Int32 firstVertex`  

```csharp
private System.Int32 firstVertex;
```

- `private System.Int32 vertexCount`  

```csharp
private System.Int32 vertexCount;
```

- `private UnityEngine.Bounds bounds`  

```csharp
private UnityEngine.Bounds bounds;
```


## Constructors

- `public SubMeshInfo(UnityEngine.Rendering.SubMeshDescriptor sm)`  

```csharp
public SubMeshInfo(UnityEngine.Rendering.SubMeshDescriptor sm);
```


## Methods

- `public ToSubMeshDescriptor() : UnityEngine.Rendering.SubMeshDescriptor`  

```csharp
public UnityEngine.Rendering.SubMeshDescriptor ToSubMeshDescriptor();
```


