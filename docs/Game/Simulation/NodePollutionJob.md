# Game.Simulation.WaterPipePollutionSystem+NodePollutionJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.BufferTypeHandle<Game.Simulation.ConnectedFlowEdge> m_FlowConnectionType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeNode> m_NodeType`  
- `public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> m_FlowEdges`  
- `public System.Single m_StaleWaterPipePurification`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

