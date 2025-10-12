# Game.Simulation.AircraftNavigationHelpers+AircraftCollisionIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Fields

- `public Unity.Entities.Entity m_Ignore`  
- `public Colossal.Mathematics.Line3+Segment m_Line`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.Entity m_Result`  
- `public System.Single m_ClosestT`  

## Methods

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  
- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity entity) : System.Void`  

