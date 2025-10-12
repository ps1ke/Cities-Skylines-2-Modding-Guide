# Game.Tutorials.TutorialInfoviewDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Unity.Entities.EntityQuery m_PendingTutorialQuery`  
- `private Unity.Entities.EntityQuery m_ActiveTutorialQuery`  
- `private Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TutorialInfoviewDeactivationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CheckDeactivation(Unity.Entities.EntityQuery query) : System.Void`  
- `private GetActiveInfoview() : Unity.Entities.Entity`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tutorials.TutorialInfoviewDeactivationSystem+CheckDeactivationJob`  
- `Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle`  

