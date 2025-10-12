# Game.Serialization.ConnectedFlowEdgeSystem+ConnectedFlowEdgeJob

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.ElectricityFlowEdge> m_ElectricityFlowEdgeType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeEdge> m_WaterPipeEdgeType`  
- `public Unity.Entities.BufferLookup<Game.Simulation.ConnectedFlowEdge> m_ConnectedFlowEdges`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

