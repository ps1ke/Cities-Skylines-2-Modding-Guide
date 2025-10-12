# Game.Simulation.WatercraftMoveSystem+UpdateTransformDataJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public System.UInt32 m_TransformFrameIndex`  
- `public Unity.Entities.ComponentTypeHandle<Game.Vehicles.WatercraftNavigation> m_NavigationType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Vehicles.WatercraftCurrentLane> m_CurrentLaneType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.WatercraftData> m_PrefabWatercraftData`  
- `public Game.Simulation.TerrainHeightData m_TerrainHeightData`  
- `public Game.Simulation.WaterSurfaceData m_WaterSurfaceData`  
- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Moving> m_MovingType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType`  
- `public Unity.Entities.BufferTypeHandle<Game.Objects.TransformFrame> m_TransformFrameType`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private SampleWater(Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, Game.Prefabs.ObjectGeometryData prefabGeometryData) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

