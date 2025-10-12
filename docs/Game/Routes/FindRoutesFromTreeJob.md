# Game.Routes.RaycastJobs+FindRoutesFromTreeJob

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  
- `public Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  
- `public Unity.Collections.NativeList<Game.Routes.RaycastJobs+RouteItem> m_RouteList`  

## Methods

- `public Execute() : System.Void`  

## Nested types

- `Game.Routes.RaycastJobs+FindRoutesFromTreeJob+FindRoutesIterator`  

