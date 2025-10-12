# Game.Serialization.DataMigration.HomelessAndWorkerFixSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  
- `private Game.Serialization.DeserializationBarrier m_DeserializationBarrier`  
- `private Unity.Entities.EntityQuery m_WorkerQuery`  
- `private Unity.Entities.EntityQuery m_HomelessQuery`  
- `private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery`  
- `private Unity.Entities.EntityQuery m_AbandonedPropertyQuery`  
- `private Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle __TypeHandle`  

## Constructors

- `public HomelessAndWorkerFixSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+WorkerFixJob`  
- `Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+AddPropertySeekerJob`  
- `Game.Serialization.DataMigration.HomelessAndWorkerFixSystem+TypeHandle`  

