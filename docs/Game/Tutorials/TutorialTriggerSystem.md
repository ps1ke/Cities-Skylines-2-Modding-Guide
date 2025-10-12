# Game.Tutorials.TutorialTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Fields

- `private readonly System.Collections.Generic.List<Game.Tutorials.TutorialTriggerSystemBase> m_Systems`  
- `private Unity.Entities.EntityQuery m_TriggerQuery`  

## Constructors

- `public TutorialTriggerSystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

