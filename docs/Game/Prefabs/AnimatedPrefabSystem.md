# Game.Prefabs.AnimatedPrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Rendering.AnimatedSystem m_AnimatedSystem`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Game.Prefabs.AnimatedPrefabSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AnimatedPrefabSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CleanUpRootMotion(Game.Prefabs.CharacterStyle+AnimationMotion[] source, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> target) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.AnimatedPrefabSystem+TypeHandle`  

