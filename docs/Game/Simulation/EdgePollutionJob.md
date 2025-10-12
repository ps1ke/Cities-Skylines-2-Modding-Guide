# Game.Simulation.WaterPipePollutionSystem+EdgePollutionJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeEdge> m_FlowEdgeType`  
- `public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeNode> m_FlowNodes`  
- `public Unity.Entities.Entity m_SourceNode`  
- `public System.Boolean m_Purify`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

