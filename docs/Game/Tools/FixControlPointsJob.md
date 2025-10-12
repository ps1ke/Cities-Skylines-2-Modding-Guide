# Game.Tools.NetToolSystem+FixControlPointsJob

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_Chunks`  
- `public Game.Tools.NetToolSystem+Mode m_Mode`  
- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType`  
- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  
- `public Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

## Methods

- `public Execute() : System.Void`  
- `private FixControlPoints(Unity.Entities.Entity entity, Unity.Entities.Entity replace) : System.Void`  
- `private InverseCurvePositions(Unity.Entities.Entity entity) : System.Void`  

