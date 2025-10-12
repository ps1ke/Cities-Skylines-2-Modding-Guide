# Game.Objects.RaycastJobs+RaycastMovingObjectsJob

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public System.Boolean m_EditorMode`  
- `public System.Boolean m_LeftHandTraffic`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_ObjectList`  
- `public Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Quantity> m_QuantityData`  
- `public Unity.Entities.ComponentLookup<Game.Rendering.CullingInfo> m_CullingInfoData`  
- `public Unity.Entities.ComponentLookup<Game.Rendering.InterpolatedTransform> m_InterpolatedTransformData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.QuantityObjectData> m_PrefabQuantityObjectData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> m_PrefabMeshData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SharedMeshData> m_PrefabSharedMeshData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.BufferLookup<Game.Objects.SubObject> m_SubObjects`  
- `public Unity.Entities.BufferLookup<Game.Vehicles.Passenger> m_Passengers`  
- `public Unity.Entities.BufferLookup<Game.Rendering.Skeleton> m_Skeletons`  
- `public Unity.Entities.BufferLookup<Game.Rendering.Bone> m_Bones`  
- `public Unity.Entities.BufferLookup<Game.Rendering.MeshGroup> m_MeshGroups`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.SubMesh> m_Meshes`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.SubMeshGroup> m_SubMeshGroups`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.LodMesh> m_Lods`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.MeshVertex> m_Vertices`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.MeshIndex> m_Indices`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.MeshNode> m_Nodes`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.ProceduralBone> m_ProceduralBones`  
- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  
- `private HasCachedMesh(Unity.Entities.Entity mesh, Unity.Entities.Entity& sharedMesh) : System.Boolean`  
- `private IsNearCamera(Unity.Entities.Entity entity) : System.Boolean`  
- `private RaycastMeshes(Game.Common.RaycastInput input, Game.Common.RaycastResult& result, Unity.Entities.Entity entity, Game.Prefabs.PrefabRef prefabRefData, Colossal.Mathematics.Line3+Segment worldLine, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.quaternion localToWorldRotation, Unity.Mathematics.float2 cutOffset) : System.Boolean`  
- `private RaycastObject(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity owner, Unity.Entities.Entity entity) : System.Void`  
- `private RaycastObjects(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity owner, Unity.Entities.Entity entity) : System.Void`  

