# Game.Tutorials.TutorialUIDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  
**Implements:** `Game.Tutorials.ITutorialUIDeactivationSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private readonly System.Collections.Generic.HashSet<System.String> m_Deactivate`  
- `private Unity.Entities.EntityQuery m_PendingTutorialQuery`  
- `private Unity.Entities.EntityQuery m_ActiveTutorialQuery`  

## Constructors

- `public TutorialUIDeactivationSystem()`  

## Methods

- `private CheckDeactivate(Unity.Entities.EntityQuery query) : System.Void`  
- `public DeactivateTag(System.String tag) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

