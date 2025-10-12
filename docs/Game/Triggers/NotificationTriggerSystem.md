# Game.Triggers.NotificationTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Unity.Entities.EntityQuery m_CreatedNotificationsQuery`  
- `private Unity.Entities.EntityQuery m_DeletedNotificationsQuery`  
- `private Unity.Entities.EntityQuery m_AllNotificationsQuery`  
- `private Game.Triggers.NotificationTriggerSystem+TypeHandle __TypeHandle`  

## Constructors

- `public NotificationTriggerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Triggers.NotificationTriggerSystem+TriggerJob`  
- `Game.Triggers.NotificationTriggerSystem+TypeHandle`  

