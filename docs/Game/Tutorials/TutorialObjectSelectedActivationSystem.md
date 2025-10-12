# Game.Tutorials.TutorialObjectSelectedActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Tools.NetToolSystem m_NetToolSystem`  
- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  
- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  
- `private Unity.Entities.EntityQuery m_TutorialQuery`  
- `private Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TutorialObjectSelectedActivationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetSelection(System.Boolean& tool) : Unity.Entities.Entity`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tutorials.TutorialObjectSelectedActivationSystem+ActivateJob`  
- `Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle`  

