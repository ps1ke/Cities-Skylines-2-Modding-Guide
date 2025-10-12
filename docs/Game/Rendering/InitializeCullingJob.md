# Game.Rendering.PreCullingSystem+InitializeCullingJob

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.Updated> m_UpdatedType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.BatchesUpdated> m_BatchesUpdatedType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.Overridden> m_OverriddenType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Stack> m_StackType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Marker> m_ObjectMarkerType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Unspawned> m_UnspawnedType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.Node> m_NodeType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_EdgeType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.NodeGeometry> m_NodeGeometryType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeGeometry> m_EdgeGeometryType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.StartNodeGeometry> m_StartNodeGeometryType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.EndNodeGeometry> m_EndNodeGeometryType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.Composition> m_CompositionType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.Orphan> m_OrphanType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.UtilityLane> m_UtilityLaneType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.Marker> m_NetMarkerType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Zones.Block> m_ZoneBlockType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `public Unity.Entities.BufferTypeHandle<Game.Objects.TransformFrame> m_TransformFrameType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Rendering.CullingInfo> m_CullingInfoType`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.StackData> m_PrefabStackData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionMeshRef> m_PrefabCompositionMeshRef`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionMeshData> m_PrefabCompositionMeshData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData`  
- `public System.Boolean m_EditorMode`  
- `public System.Boolean m_UpdateAll`  
- `public System.Boolean m_UnspawnedVisible`  
- `public System.Boolean m_Loaded`  
- `public Game.Net.UtilityTypes m_DilatedUtilityTypes`  
- `public Game.Simulation.TerrainHeightData m_TerrainHeightData`  
- `public Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private SetFlags(Game.Rendering.CullingInfo& cullingInfo, System.Int32 updateFrame, System.Boolean isUpdated, System.Boolean batchesUpdated, System.Boolean remove) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

