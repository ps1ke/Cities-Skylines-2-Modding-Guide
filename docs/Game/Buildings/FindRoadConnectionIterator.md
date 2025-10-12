# Game.Buildings.RoadConnectionSystem+FindRoadConnectionJob+FindRoadConnectionIterator

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  
- `public System.Single m_MinDistance`  
- `public System.Single m_BestCurvePos`  
- `public Unity.Entities.Entity m_BestRoad`  
- `public Unity.Mathematics.float3 m_FrontPosition`  
- `public System.Boolean m_CanBeOnRoad`  
- `public Unity.Entities.BufferLookup<Game.Buildings.ConnectedBuilding> m_ConnectedBuildings`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  
- `public Unity.Entities.ComponentLookup<Game.Net.EdgeGeometry> m_EdgeGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Net.StartNodeGeometry> m_StartNodeGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Net.EndNodeGeometry> m_EndNodeGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabNetCompositionData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Deleted> m_DeletedData`  

## Methods

- `public CheckEdge(Unity.Entities.Entity edgeEntity) : System.Void`  
- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  
- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity edgeEntity) : System.Void`  

