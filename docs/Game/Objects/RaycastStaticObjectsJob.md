# Game.Objects.RaycastJobs+RaycastStaticObjectsJob

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
- `public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_Objects`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastResult> m_TerrainResults`  
- `public Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Elevation> m_ElevationData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Placeholder> m_PlaceholderData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Tree> m_TreeData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.NetObject> m_NetObjectData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Quantity> m_QuantityData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Stack> m_StackData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Secondary> m_SecondaryData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.UnderConstruction> m_UnderConstructionData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnectionData`  
- `public Unity.Entities.ComponentLookup<Game.Tools.EditorContainer> m_EditorContainerData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.GrowthScaleData> m_PrefabGrowthScaleData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.QuantityObjectData> m_PrefabQuantityObjectData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.StackData> m_PrefabStackData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Overridden> m_OverriddenData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Destroyed> m_DestroyedData`  
- `public Unity.Entities.ComponentLookup<Game.Rendering.CullingInfo> m_CullingInfoData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Node> m_NodeData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Orphan> m_OrphanData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.ServiceUpgrade> m_ServiceUpgradeData`  
- `public Unity.Entities.ComponentLookup<Game.Areas.Lot> m_LotAreaData`  
- `public Unity.Entities.BufferLookup<Game.Net.SubNet> m_SubNets`  
- `public Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_ConnectedEdges`  
- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  
- `public Unity.Entities.BufferLookup<Game.Rendering.Skeleton> m_Skeletons`  
- `public Unity.Entities.BufferLookup<Game.Rendering.Bone> m_Bones`  
- `public Unity.Entities.BufferLookup<Game.Rendering.MeshGroup> m_MeshGroups`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> m_PrefabMeshData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ImpostorData> m_PrefabImpostorData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SharedMeshData> m_PrefabSharedMeshData`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.SubMesh> m_Meshes`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.SubMeshGroup> m_SubMeshGroups`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.LodMesh> m_Lods`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.MeshVertex> m_Vertices`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.MeshIndex> m_Indices`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.MeshNode> m_Nodes`  
- `public Unity.Entities.BufferLookup<Game.Prefabs.ProceduralBone> m_ProceduralBones`  
- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

## Methods

- `private CheckCompositionCollisionMask(Game.Common.RaycastInput& input, Unity.Entities.Entity composition) : System.Boolean`  
- `private CheckNetCollisionMask(Game.Common.RaycastInput& input, Unity.Entities.Entity owner) : System.Boolean`  
- `private CheckPlaceholder(Game.Common.RaycastInput& input, Unity.Entities.Entity& entity) : System.Boolean`  
- `public Execute(System.Int32 index) : System.Void`  
- `private FindClosestNode(Game.Common.RaycastInput& input, Game.Common.RaycastResult& result) : System.Boolean`  
- `private HasCachedMesh(Unity.Entities.Entity mesh, Unity.Entities.Entity& sharedMesh) : System.Boolean`  
- `private IsNearCamera(Unity.Entities.Entity entity) : System.Boolean`  
- `private RaycastLot(Game.Common.RaycastResult& result, Game.Prefabs.ObjectGeometryData prefabObjectData, Colossal.Mathematics.Line3+Segment worldLine, System.Int32 raycastIndex, Unity.Mathematics.quaternion inverseRotation, Unity.Mathematics.float3 position) : System.Void`  
- `private RaycastMeshes(Game.Common.RaycastInput& input, Game.Common.RaycastResult& result, Unity.Entities.Entity entity, Game.Prefabs.PrefabRef prefabRef, Colossal.Mathematics.Line3+Segment worldLine, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.quaternion localToWorldRotation, Unity.Mathematics.float2 cutOffset) : System.Boolean`  
- `private ValidateResult(Game.Common.RaycastInput& input, Game.Common.RaycastResult& result) : System.Boolean`  

