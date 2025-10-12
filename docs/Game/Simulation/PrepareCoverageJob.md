# Game.Simulation.ServiceCoverageSystem+PrepareCoverageJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Game.Net.CoverageService m_Service`  
- `public Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> m_BuildingChunks`  
- `public Unity.Entities.SharedComponentTypeHandle<Game.Net.CoverageServiceType> m_CoverageServiceType`  
- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.BufferTypeHandle<Game.Pathfind.CoverageElement> m_CoverageElementType`  
- `public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+BuildingData> m_BuildingData`  
- `public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+CoverageElement> m_Elements`  

## Methods

- `public Execute() : System.Void`  

