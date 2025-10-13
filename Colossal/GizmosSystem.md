# Colossal.GizmosSystem

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `Colossal.Entities.COSystemBase`  

## Code

```csharp
public class GizmosSystem : Colossal.Entities.COSystemBase
{
    private Colossal.Internal.Gizmos.GizmoObjects m_GizmoObjects;
    private Colossal.NativeCounter m_EstimatedVertexCount;
    private Colossal.NativeCounter m_EstimatedIndexCount;
    private Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> m_CameraInfos;
    private Unity.Collections.NativeList<Unity.Mathematics.float4> m_CullingPlanes;
    private Colossal.GizmoBatcher m_Batcher;
    private Unity.Jobs.JobHandle m_Dependencies;
    private UnityEngine.Material m_Material;
    private UnityEngine.Material m_MaterialOccluded;
    private UnityEngine.MaterialPropertyBlock m_Block;
    private UnityEngine.Mesh m_LinesMesh;
    private UnityEngine.Vector3[] m_Vertices;
    private UnityEngine.Color[] m_Colors;
    private System.Int32[] m_Indices;
    private UnityEngine.Plane[] m_Planes;

    public GizmosSystem();

    private System.Void AddCullingData(UnityEngine.Camera camera);
    public System.Void AddGizmosBatcherWriter(Unity.Jobs.JobHandle handle);
    public Colossal.GizmoBatcher GetGizmosBatcher(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ProcessBatchedGizmos();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
    private System.Void ResetCounters();
}
```


## Fields

- `private Colossal.Internal.Gizmos.GizmoObjects m_GizmoObjects`  

```csharp
private Colossal.Internal.Gizmos.GizmoObjects m_GizmoObjects;
```

- `private Colossal.NativeCounter m_EstimatedVertexCount`  

```csharp
private Colossal.NativeCounter m_EstimatedVertexCount;
```

- `private Colossal.NativeCounter m_EstimatedIndexCount`  

```csharp
private Colossal.NativeCounter m_EstimatedIndexCount;
```

- `private Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> m_CameraInfos`  

```csharp
private Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> m_CameraInfos;
```

- `private Unity.Collections.NativeList<Unity.Mathematics.float4> m_CullingPlanes`  

```csharp
private Unity.Collections.NativeList<Unity.Mathematics.float4> m_CullingPlanes;
```

- `private Colossal.GizmoBatcher m_Batcher`  

```csharp
private Colossal.GizmoBatcher m_Batcher;
```

- `private Unity.Jobs.JobHandle m_Dependencies`  

```csharp
private Unity.Jobs.JobHandle m_Dependencies;
```

- `private UnityEngine.Material m_Material`  

```csharp
private UnityEngine.Material m_Material;
```

- `private UnityEngine.Material m_MaterialOccluded`  

```csharp
private UnityEngine.Material m_MaterialOccluded;
```

- `private UnityEngine.MaterialPropertyBlock m_Block`  

```csharp
private UnityEngine.MaterialPropertyBlock m_Block;
```

- `private UnityEngine.Mesh m_LinesMesh`  

```csharp
private UnityEngine.Mesh m_LinesMesh;
```

- `private UnityEngine.Vector3[] m_Vertices`  

```csharp
private UnityEngine.Vector3[] m_Vertices;
```

- `private UnityEngine.Color[] m_Colors`  

```csharp
private UnityEngine.Color[] m_Colors;
```

- `private System.Int32[] m_Indices`  

```csharp
private System.Int32[] m_Indices;
```

- `private UnityEngine.Plane[] m_Planes`  

```csharp
private UnityEngine.Plane[] m_Planes;
```


## Constructors

- `public GizmosSystem()`  

```csharp
public GizmosSystem();
```


## Methods

- `private AddCullingData(UnityEngine.Camera camera) : System.Void`  

```csharp
private System.Void AddCullingData(UnityEngine.Camera camera);
```

- `public AddGizmosBatcherWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddGizmosBatcherWriter(Unity.Jobs.JobHandle handle);
```

- `public GetGizmosBatcher(Unity.Jobs.JobHandle& dependencies) : Colossal.GizmoBatcher`  

```csharp
public Colossal.GizmoBatcher GetGizmosBatcher(Unity.Jobs.JobHandle& dependencies);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ProcessBatchedGizmos() : System.Void`  

```csharp
private System.Void ProcessBatchedGizmos();
```

- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

```csharp
private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
```

- `private ResetCounters() : System.Void`  

```csharp
private System.Void ResetCounters();
```


## Nested types

- `Colossal.GizmosSystem+CreateGizmoMesh`  

