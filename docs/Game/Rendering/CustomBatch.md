# Game.Rendering.CustomBatch

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Colossal.Rendering.ManagedBatch`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class CustomBatch : Colossal.Rendering.ManagedBatch, System.IDisposable
{
    private Colossal.IO.AssetDatabase.SurfaceAsset <sourceSurface>k__BackingField;
    private UnityEngine.Material <sourceMaterial>k__BackingField;
    private UnityEngine.Material <defaultMaterial>k__BackingField;
    private UnityEngine.Material <loadedMaterial>k__BackingField;
    private System.Int32 <sourceSubMeshIndex>k__BackingField;
    private Unity.Entities.Entity <sourceMeshEntity>k__BackingField;
    private Unity.Entities.Entity <sharedMeshEntity>k__BackingField;
    private Game.Rendering.BatchFlags <sourceFlags>k__BackingField;
    private Game.Rendering.GeneratedType <generatedType>k__BackingField;
    private Game.Prefabs.MeshType <sourceType>k__BackingField;

    public Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface { get; private set; }
    public UnityEngine.Material sourceMaterial { get; private set; }
    public UnityEngine.Material defaultMaterial { get; private set; }
    public UnityEngine.Material loadedMaterial { get; private set; }
    public System.Int32 sourceSubMeshIndex { get; private set; }
    public Unity.Entities.Entity sourceMeshEntity { get; private set; }
    public Unity.Entities.Entity sharedMeshEntity { get; private set; }
    public Game.Rendering.BatchFlags sourceFlags { get; private set; }
    public Game.Rendering.GeneratedType generatedType { get; private set; }
    public Game.Prefabs.MeshType sourceType { get; private set; }

    public CustomBatch(System.Int32 groupIndex, System.Int32 batchIndex, Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface, UnityEngine.Material sourceMaterial, UnityEngine.Material defaultMaterial, UnityEngine.Material loadedMaterial, UnityEngine.Mesh mesh, Unity.Entities.Entity meshEntity, Unity.Entities.Entity sharedEntity, Game.Rendering.BatchFlags flags, Game.Rendering.GeneratedType generatedType, Game.Prefabs.MeshType type, System.Int32 subMeshIndex, UnityEngine.MaterialPropertyBlock customProps);

    public virtual System.Void Dispose();
    public System.Void ReplaceMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.SurfaceAsset <sourceSurface>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.SurfaceAsset <sourceSurface>k__BackingField;
```

- `private UnityEngine.Material <sourceMaterial>k__BackingField`  

```csharp
private UnityEngine.Material <sourceMaterial>k__BackingField;
```

- `private UnityEngine.Material <defaultMaterial>k__BackingField`  

```csharp
private UnityEngine.Material <defaultMaterial>k__BackingField;
```

- `private UnityEngine.Material <loadedMaterial>k__BackingField`  

```csharp
private UnityEngine.Material <loadedMaterial>k__BackingField;
```

- `private System.Int32 <sourceSubMeshIndex>k__BackingField`  

```csharp
private System.Int32 <sourceSubMeshIndex>k__BackingField;
```

- `private Unity.Entities.Entity <sourceMeshEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <sourceMeshEntity>k__BackingField;
```

- `private Unity.Entities.Entity <sharedMeshEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <sharedMeshEntity>k__BackingField;
```

- `private Game.Rendering.BatchFlags <sourceFlags>k__BackingField`  

```csharp
private Game.Rendering.BatchFlags <sourceFlags>k__BackingField;
```

- `private Game.Rendering.GeneratedType <generatedType>k__BackingField`  

```csharp
private Game.Rendering.GeneratedType <generatedType>k__BackingField;
```

- `private Game.Prefabs.MeshType <sourceType>k__BackingField`  

```csharp
private Game.Prefabs.MeshType <sourceType>k__BackingField;
```


## Properties

- `public Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface { get; private set }`  

```csharp
public Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface { get; private set; }
```

- `public UnityEngine.Material sourceMaterial { get; private set }`  

```csharp
public UnityEngine.Material sourceMaterial { get; private set; }
```

- `public UnityEngine.Material defaultMaterial { get; private set }`  

```csharp
public UnityEngine.Material defaultMaterial { get; private set; }
```

- `public UnityEngine.Material loadedMaterial { get; private set }`  

```csharp
public UnityEngine.Material loadedMaterial { get; private set; }
```

- `public System.Int32 sourceSubMeshIndex { get; private set }`  

```csharp
public System.Int32 sourceSubMeshIndex { get; private set; }
```

- `public Unity.Entities.Entity sourceMeshEntity { get; private set }`  

```csharp
public Unity.Entities.Entity sourceMeshEntity { get; private set; }
```

- `public Unity.Entities.Entity sharedMeshEntity { get; private set }`  

```csharp
public Unity.Entities.Entity sharedMeshEntity { get; private set; }
```

- `public Game.Rendering.BatchFlags sourceFlags { get; private set }`  

```csharp
public Game.Rendering.BatchFlags sourceFlags { get; private set; }
```

- `public Game.Rendering.GeneratedType generatedType { get; private set }`  

```csharp
public Game.Rendering.GeneratedType generatedType { get; private set; }
```

- `public Game.Prefabs.MeshType sourceType { get; private set }`  

```csharp
public Game.Prefabs.MeshType sourceType { get; private set; }
```


## Constructors

- `public CustomBatch(System.Int32 groupIndex, System.Int32 batchIndex, Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface, UnityEngine.Material sourceMaterial, UnityEngine.Material defaultMaterial, UnityEngine.Material loadedMaterial, UnityEngine.Mesh mesh, Unity.Entities.Entity meshEntity, Unity.Entities.Entity sharedEntity, Game.Rendering.BatchFlags flags, Game.Rendering.GeneratedType generatedType, Game.Prefabs.MeshType type, System.Int32 subMeshIndex, UnityEngine.MaterialPropertyBlock customProps)`  

```csharp
public CustomBatch(System.Int32 groupIndex, System.Int32 batchIndex, Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface, UnityEngine.Material sourceMaterial, UnityEngine.Material defaultMaterial, UnityEngine.Material loadedMaterial, UnityEngine.Mesh mesh, Unity.Entities.Entity meshEntity, Unity.Entities.Entity sharedEntity, Game.Rendering.BatchFlags flags, Game.Rendering.GeneratedType generatedType, Game.Prefabs.MeshType type, System.Int32 subMeshIndex, UnityEngine.MaterialPropertyBlock customProps);
```


## Methods

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `public ReplaceMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh) : System.Void`  

```csharp
public System.Void ReplaceMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh);
```


