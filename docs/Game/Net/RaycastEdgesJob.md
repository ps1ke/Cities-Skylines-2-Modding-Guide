# Game.Net.RaycastJobs+RaycastEdgesJob

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public System.Single m_FovTan`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_Edges`  
- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Node> m_NodeData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Elevation> m_ElevationData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Orphan> m_OrphanData`  
- `public Unity.Entities.ComponentLookup<Game.Net.NodeGeometry> m_NodeGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Net.EdgeGeometry> m_EdgeGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Net.StartNodeGeometry> m_StartNodeGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Net.EndNodeGeometry> m_EndNodeGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Placeholder> m_PlaceholderData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.ServiceUpgrade> m_ServiceUpgradeData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData`  
- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  
- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

## Methods

- `private CheckEdge(Unity.Entities.Entity entity, System.Int32 raycastIndex, Game.Common.RaycastInput input) : System.Void`  
- `private CheckNode(Unity.Entities.Entity entity, System.Int32 raycastIndex, Game.Common.RaycastInput input) : System.Void`  
- `private CheckPlaceholder(Game.Common.RaycastInput input, Unity.Entities.Entity& entity) : System.Boolean`  
- `private CheckSegment(Game.Common.RaycastInput input, System.Int32 raycastIndex, Unity.Entities.Entity owner, Unity.Entities.Entity hitEntity, Game.Net.Segment segment, Colossal.Mathematics.Bezier4x3 curve, Game.Prefabs.NetCompositionData prefabCompositionData) : System.Void`  
- `public Execute(System.Int32 index) : System.Void`  
- `private SetElevationOffset(Unity.Mathematics.float3& position, Unity.Entities.Entity node, System.Single maxElevation) : System.Void`  
- `private SetElevationOffset(Colossal.Mathematics.Bezier4x3& curve, Unity.Entities.Entity edge, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, System.Single maxElevation) : System.Void`  
- `private SetElevationOffset(Game.Net.EdgeGeometry& geometry, Unity.Entities.Entity edge, Unity.Entities.Entity startNode, Unity.Entities.Entity endNode, System.Single maxElevation) : System.Void`  
- `private SetElevationOffset(Game.Net.EdgeNodeGeometry& geometry, Unity.Entities.Entity node, System.Single maxElevation) : System.Void`  
- `private SetElevationOffset(Colossal.Mathematics.Bezier4x3& curve, System.Single offset, System.Single maxElevation) : System.Void`  
- `private SetElevationOffset(Colossal.Mathematics.Bezier4x3& curve, Unity.Mathematics.float2 offset, System.Single maxElevation) : System.Void`  
- `private ValidateResult(Game.Common.RaycastInput input, Game.Common.RaycastResult& result) : System.Boolean`  

