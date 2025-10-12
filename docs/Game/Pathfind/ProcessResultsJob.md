# Game.Pathfind.PathfindJobs+ProcessResultsJob

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelFor`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_ResultItems`  
- `public Unity.Entities.ComponentLookup<Game.Pathfind.PathOwner> m_PathOwner`  
- `public Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformation`  
- `public Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  
- `public Unity.Entities.BufferLookup<Game.Pathfind.PathInformations> m_PathInformations`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  

