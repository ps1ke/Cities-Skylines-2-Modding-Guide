# Game.Rendering.RequiredBatchesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Unity.Entities.EntityQuery m_AllQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Rendering.RequiredBatchesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RequiredBatchesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.RequiredBatchesSystem+RequiredBatchesJob`  
- `Game.Rendering.RequiredBatchesSystem+TypeHandle`  

