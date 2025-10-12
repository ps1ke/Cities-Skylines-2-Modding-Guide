# Game.Tools.CoveragePreviewSystem+SetupCoverageSearchJob

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.Entity m_Entity`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.BackSide> m_BackSideData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.CoverageData> m_PrefabCoverageData`  
- `public Game.Pathfind.CoverageAction m_Action`  
- `public Game.Pathfind.PathfindTargetSeeker<Game.Pathfind.PathfindTargetBuffer> m_TargetSeeker`  

## Methods

- `public Execute() : System.Void`  

