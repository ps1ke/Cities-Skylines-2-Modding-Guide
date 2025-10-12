# Game.Notifications.IconCommandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  
- `private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command>> m_Queues`  
- `private Unity.Jobs.JobHandle m_Dependencies`  
- `private System.Int32 m_BufferIndex`  
- `private Game.Notifications.IconCommandSystem+TypeHandle __TypeHandle`  

## Constructors

- `public IconCommandSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddCommandBufferWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public CreateCommandBuffer() : Game.Notifications.IconCommandBuffer`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Notifications.IconCommandSystem+IconCommandPlaybackJob`  
- `Game.Notifications.IconCommandSystem+TypeHandle`  

