# Game.Tutorials.TutorialObjectSelectionDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Tools.NetToolSystem m_NetToolSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Unity.Entities.EntityQuery m_PendingTutorialQuery`  
- `private Unity.Entities.EntityQuery m_ActiveTutorialQuery`  
- `private Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TutorialObjectSelectionDeactivationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CheckDeactivate(Unity.Entities.EntityQuery query, Unity.Entities.Entity selection, System.Boolean tool) : System.Void`  
- `private GetSelection(System.Boolean& tool) : Unity.Entities.Entity`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tutorials.TutorialObjectSelectionDeactivationSystem+CheckTutorialsJob`  
- `Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle`  

