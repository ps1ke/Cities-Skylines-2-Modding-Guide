# Game.Objects.RaycastJobs+RaycastMovingObjectsJob

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct RaycastMovingObjectsJob : Unity.Jobs.IJobParallelForDefer
{
    public System.Boolean m_EditorMode;
    public System.Boolean m_LeftHandTraffic;
    public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
    public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_ObjectList;
    public Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Quantity> m_QuantityData;
    public Unity.Entities.ComponentLookup<Game.Rendering.CullingInfo> m_CullingInfoData;
    public Unity.Entities.ComponentLookup<Game.Rendering.InterpolatedTransform> m_InterpolatedTransformData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.QuantityObjectData> m_PrefabQuantityObjectData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> m_PrefabMeshData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SharedMeshData> m_PrefabSharedMeshData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.BufferLookup<Game.Objects.SubObject> m_SubObjects;
    public Unity.Entities.BufferLookup<Game.Vehicles.Passenger> m_Passengers;
    public Unity.Entities.BufferLookup<Game.Rendering.Skeleton> m_Skeletons;
    public Unity.Entities.BufferLookup<Game.Rendering.Bone> m_Bones;
    public Unity.Entities.BufferLookup<Game.Rendering.MeshGroup> m_MeshGroups;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubMesh> m_Meshes;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubMeshGroup> m_SubMeshGroups;
    public Unity.Entities.BufferLookup<Game.Prefabs.LodMesh> m_Lods;
    public Unity.Entities.BufferLookup<Game.Prefabs.MeshVertex> m_Vertices;
    public Unity.Entities.BufferLookup<Game.Prefabs.MeshIndex> m_Indices;
    public Unity.Entities.BufferLookup<Game.Prefabs.MeshNode> m_Nodes;
    public Unity.Entities.BufferLookup<Game.Prefabs.ProceduralBone> m_ProceduralBones;
    public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;

    public System.Void Execute(System.Int32 index);
    private System.Boolean HasCachedMesh(Unity.Entities.Entity mesh, Unity.Entities.Entity& sharedMesh);
    private System.Boolean IsNearCamera(Unity.Entities.Entity entity);
    private System.Boolean RaycastMeshes(Game.Common.RaycastInput input, Game.Common.RaycastResult& result, Unity.Entities.Entity entity, Game.Prefabs.PrefabRef prefabRefData, Colossal.Mathematics.Line3+Segment worldLine, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.quaternion localToWorldRotation, Unity.Mathematics.float2 cutOffset);
    private System.Void RaycastObject(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity owner, Unity.Entities.Entity entity);
    private System.Void RaycastObjects(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity owner, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Boolean m_EditorMode`  

```csharp
public System.Boolean m_EditorMode;
```

- `public System.Boolean m_LeftHandTraffic`  

```csharp
public System.Boolean m_LeftHandTraffic;
```

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
```

- `public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_ObjectList`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_ObjectList;
```

- `public Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData`  

```csharp
public Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Quantity> m_QuantityData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Quantity> m_QuantityData;
```

- `public Unity.Entities.ComponentLookup<Game.Rendering.CullingInfo> m_CullingInfoData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Rendering.CullingInfo> m_CullingInfoData;
```

- `public Unity.Entities.ComponentLookup<Game.Rendering.InterpolatedTransform> m_InterpolatedTransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Rendering.InterpolatedTransform> m_InterpolatedTransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.QuantityObjectData> m_PrefabQuantityObjectData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.QuantityObjectData> m_PrefabQuantityObjectData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> m_PrefabMeshData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> m_PrefabMeshData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SharedMeshData> m_PrefabSharedMeshData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SharedMeshData> m_PrefabSharedMeshData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.BufferLookup<Game.Objects.SubObject> m_SubObjects`  

```csharp
public Unity.Entities.BufferLookup<Game.Objects.SubObject> m_SubObjects;
```

- `public Unity.Entities.BufferLookup<Game.Vehicles.Passenger> m_Passengers`  

```csharp
public Unity.Entities.BufferLookup<Game.Vehicles.Passenger> m_Passengers;
```

- `public Unity.Entities.BufferLookup<Game.Rendering.Skeleton> m_Skeletons`  

```csharp
public Unity.Entities.BufferLookup<Game.Rendering.Skeleton> m_Skeletons;
```

- `public Unity.Entities.BufferLookup<Game.Rendering.Bone> m_Bones`  

```csharp
public Unity.Entities.BufferLookup<Game.Rendering.Bone> m_Bones;
```

- `public Unity.Entities.BufferLookup<Game.Rendering.MeshGroup> m_MeshGroups`  

```csharp
public Unity.Entities.BufferLookup<Game.Rendering.MeshGroup> m_MeshGroups;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubMesh> m_Meshes`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubMesh> m_Meshes;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubMeshGroup> m_SubMeshGroups`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubMeshGroup> m_SubMeshGroups;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.LodMesh> m_Lods`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.LodMesh> m_Lods;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.MeshVertex> m_Vertices`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.MeshVertex> m_Vertices;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.MeshIndex> m_Indices`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.MeshIndex> m_Indices;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.MeshNode> m_Nodes`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.MeshNode> m_Nodes;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.ProceduralBone> m_ProceduralBones`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.ProceduralBone> m_ProceduralBones;
```

- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

```csharp
public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;
```


## Methods

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```

- `private HasCachedMesh(Unity.Entities.Entity mesh, Unity.Entities.Entity& sharedMesh) : System.Boolean`  

```csharp
private System.Boolean HasCachedMesh(Unity.Entities.Entity mesh, Unity.Entities.Entity& sharedMesh);
```

- `private IsNearCamera(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
private System.Boolean IsNearCamera(Unity.Entities.Entity entity);
```

- `private RaycastMeshes(Game.Common.RaycastInput input, Game.Common.RaycastResult& result, Unity.Entities.Entity entity, Game.Prefabs.PrefabRef prefabRefData, Colossal.Mathematics.Line3+Segment worldLine, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.quaternion localToWorldRotation, Unity.Mathematics.float2 cutOffset) : System.Boolean`  

```csharp
private System.Boolean RaycastMeshes(Game.Common.RaycastInput input, Game.Common.RaycastResult& result, Unity.Entities.Entity entity, Game.Prefabs.PrefabRef prefabRefData, Colossal.Mathematics.Line3+Segment worldLine, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.quaternion localToWorldRotation, Unity.Mathematics.float2 cutOffset);
```

- `private RaycastObject(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity owner, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void RaycastObject(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity owner, Unity.Entities.Entity entity);
```

- `private RaycastObjects(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity owner, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void RaycastObjects(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity owner, Unity.Entities.Entity entity);
```


