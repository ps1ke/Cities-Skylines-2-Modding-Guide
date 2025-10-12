# Game.Tutorials.TutorialUIActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Tutorials.ITutorialUIActivationSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  
- `private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Unity.Entities.Entity>> m_TutorialMap`  
- `private readonly System.Collections.Generic.List<System.String> m_ActiveTags`  
- `private Unity.Entities.EntityQuery m_TutorialQuery`  

## Constructors

- `public TutorialUIActivationSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RebuildTutorialMap() : System.Void`  
- `public SetTag(System.String tag, System.Boolean active) : System.Void`  

