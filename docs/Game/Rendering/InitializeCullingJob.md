# Game.Rendering.PreCullingSystem+InitializeCullingJob

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct InitializeCullingJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Updated> m_UpdatedType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.BatchesUpdated> m_BatchesUpdatedType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Overridden> m_OverriddenType;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Stack> m_StackType;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Marker> m_ObjectMarkerType;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Unspawned> m_UnspawnedType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Node> m_NodeType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_EdgeType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.NodeGeometry> m_NodeGeometryType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeGeometry> m_EdgeGeometryType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.StartNodeGeometry> m_StartNodeGeometryType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.EndNodeGeometry> m_EndNodeGeometryType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Composition> m_CompositionType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Orphan> m_OrphanType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.UtilityLane> m_UtilityLaneType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Marker> m_NetMarkerType;
    public Unity.Entities.ComponentTypeHandle<Game.Zones.Block> m_ZoneBlockType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.BufferTypeHandle<Game.Objects.TransformFrame> m_TransformFrameType;
    public Unity.Entities.ComponentTypeHandle<Game.Rendering.CullingInfo> m_CullingInfoType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.StackData> m_PrefabStackData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionMeshRef> m_PrefabCompositionMeshRef;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionMeshData> m_PrefabCompositionMeshData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData;
    public System.Boolean m_EditorMode;
    public System.Boolean m_UpdateAll;
    public System.Boolean m_UnspawnedVisible;
    public System.Boolean m_Loaded;
    public Game.Net.UtilityTypes m_DilatedUtilityTypes;
    public Game.Simulation.TerrainHeightData m_TerrainHeightData;
    public Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void SetFlags(Game.Rendering.CullingInfo& cullingInfo, System.Int32 updateFrame, System.Boolean isUpdated, System.Boolean batchesUpdated, System.Boolean remove);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType`  

```csharp
public Unity.Entities.SharedComponentTypeHandle<Game.Simulation.UpdateFrame> m_UpdateFrameType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Updated> m_UpdatedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Updated> m_UpdatedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.BatchesUpdated> m_BatchesUpdatedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.BatchesUpdated> m_BatchesUpdatedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Overridden> m_OverriddenType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Overridden> m_OverriddenType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Stack> m_StackType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Stack> m_StackType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Marker> m_ObjectMarkerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Marker> m_ObjectMarkerType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Unspawned> m_UnspawnedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Unspawned> m_UnspawnedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Node> m_NodeType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Node> m_NodeType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_EdgeType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_EdgeType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.NodeGeometry> m_NodeGeometryType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.NodeGeometry> m_NodeGeometryType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeGeometry> m_EdgeGeometryType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeGeometry> m_EdgeGeometryType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.StartNodeGeometry> m_StartNodeGeometryType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.StartNodeGeometry> m_StartNodeGeometryType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.EndNodeGeometry> m_EndNodeGeometryType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.EndNodeGeometry> m_EndNodeGeometryType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Composition> m_CompositionType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Composition> m_CompositionType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Orphan> m_OrphanType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Orphan> m_OrphanType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.UtilityLane> m_UtilityLaneType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.UtilityLane> m_UtilityLaneType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Marker> m_NetMarkerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Marker> m_NetMarkerType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Zones.Block> m_ZoneBlockType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Zones.Block> m_ZoneBlockType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Objects.TransformFrame> m_TransformFrameType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Objects.TransformFrame> m_TransformFrameType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Rendering.CullingInfo> m_CullingInfoType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Rendering.CullingInfo> m_CullingInfoType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.StackData> m_PrefabStackData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.StackData> m_PrefabStackData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionMeshRef> m_PrefabCompositionMeshRef`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionMeshRef> m_PrefabCompositionMeshRef;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionMeshData> m_PrefabCompositionMeshData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionMeshData> m_PrefabCompositionMeshData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData;
```

- `public System.Boolean m_EditorMode`  

```csharp
public System.Boolean m_EditorMode;
```

- `public System.Boolean m_UpdateAll`  

```csharp
public System.Boolean m_UpdateAll;
```

- `public System.Boolean m_UnspawnedVisible`  

```csharp
public System.Boolean m_UnspawnedVisible;
```

- `public System.Boolean m_Loaded`  

```csharp
public System.Boolean m_Loaded;
```

- `public Game.Net.UtilityTypes m_DilatedUtilityTypes`  

```csharp
public Game.Net.UtilityTypes m_DilatedUtilityTypes;
```

- `public Game.Simulation.TerrainHeightData m_TerrainHeightData`  

```csharp
public Game.Simulation.TerrainHeightData m_TerrainHeightData;
```

- `public Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData`  

```csharp
public Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData;
```


## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private SetFlags(Game.Rendering.CullingInfo& cullingInfo, System.Int32 updateFrame, System.Boolean isUpdated, System.Boolean batchesUpdated, System.Boolean remove) : System.Void`  

```csharp
private System.Void SetFlags(Game.Rendering.CullingInfo& cullingInfo, System.Int32 updateFrame, System.Boolean isUpdated, System.Boolean batchesUpdated, System.Boolean remove);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```


