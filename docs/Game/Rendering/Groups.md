# Game.Rendering.BatchInstanceSystem+Groups

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  
- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  
- `public Colossal.Collections.NativeParallelQueue<Game.Rendering.BatchInstanceSystem+GroupActionData> m_GroupActionQueue`  
- `public Unity.Collections.NativeQueue<Game.Rendering.BatchInstanceSystem+VelocityData> m_VelocityQueue`  
- `public Unity.Collections.NativeQueue<Game.Rendering.BatchInstanceSystem+FadeData> m_FadeQueue`  
- `public Unity.Jobs.JobHandle m_Dependency`  
- `private Game.Rendering.BatchInstanceSystem+Groups+TypeHandle __TypeHandle`  

## Constructors

- `public Groups()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.BatchInstanceSystem+Groups+TypeHandle`  

