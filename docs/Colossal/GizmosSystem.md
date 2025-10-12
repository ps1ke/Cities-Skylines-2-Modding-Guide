# Colossal.GizmosSystem

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `Colossal.Entities.COSystemBase`  

## Fields

- `private Colossal.Internal.Gizmos.GizmoObjects m_GizmoObjects`  
- `private Colossal.NativeCounter m_EstimatedVertexCount`  
- `private Colossal.NativeCounter m_EstimatedIndexCount`  
- `private Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> m_CameraInfos`  
- `private Unity.Collections.NativeList<Unity.Mathematics.float4> m_CullingPlanes`  
- `private Colossal.GizmoBatcher m_Batcher`  
- `private Unity.Jobs.JobHandle m_Dependencies`  
- `private UnityEngine.Material m_Material`  
- `private UnityEngine.Material m_MaterialOccluded`  
- `private UnityEngine.MaterialPropertyBlock m_Block`  
- `private UnityEngine.Mesh m_LinesMesh`  
- `private UnityEngine.Vector3[] m_Vertices`  
- `private UnityEngine.Color[] m_Colors`  
- `private System.Int32[] m_Indices`  
- `private UnityEngine.Plane[] m_Planes`  

## Constructors

- `public GizmosSystem()`  

## Methods

- `private AddCullingData(UnityEngine.Camera camera) : System.Void`  
- `public AddGizmosBatcherWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public GetGizmosBatcher(Unity.Jobs.JobHandle& dependencies) : Colossal.GizmoBatcher`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ProcessBatchedGizmos() : System.Void`  
- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  
- `private ResetCounters() : System.Void`  

## Nested types

- `Colossal.GizmosSystem+CreateGizmoMesh`  

