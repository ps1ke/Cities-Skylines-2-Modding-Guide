# Game.Simulation.ResourceExporterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ExporterQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Unity.Collections.NativeQueue<Game.Simulation.ResourceExporterSystem+ExportEvent> m_ExportQueue`  
- `private Game.Simulation.ResourceExporterSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ResourceExporterSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ResourceExporterSystem+ExportJob`  
- `Game.Simulation.ResourceExporterSystem+ExportEvent`  
- `Game.Simulation.ResourceExporterSystem+HandleExportsJob`  
- `Game.Simulation.ResourceExporterSystem+TypeHandle`  

