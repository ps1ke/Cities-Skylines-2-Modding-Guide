# Game.Prefabs.UIInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_PolicyQuery`  
- `private Game.Prefabs.UIInitializeSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.PolicyPrefab> policies { get }`  

## Constructors

- `public UIInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> uiGroupElements) : System.Void`  
- `private RemoveFrom(Unity.Entities.Entity entity, Unity.Entities.DynamicBuffer<Game.Prefabs.UnlockRequirement> unlockRequirements) : System.Void`  

## Nested types

- `Game.Prefabs.UIInitializeSystem+TypeHandle`  
- `Game.Prefabs.UIInitializeSystem+<get_policies>d__4`  

