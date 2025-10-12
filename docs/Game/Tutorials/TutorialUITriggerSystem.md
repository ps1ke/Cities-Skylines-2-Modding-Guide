# Game.Tutorials.TutorialUITriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  
**Implements:** `Game.Tutorials.ITutorialUITriggerSystem`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private readonly System.Collections.Generic.HashSet<System.String> m_ActivatedTriggers`  

## Constructors

- `public TutorialUITriggerSystem()`  

## Methods

- `public ActivateTrigger(System.String trigger) : System.Void`  
- `public DisactivateTrigger(System.String trigger) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

