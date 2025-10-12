# Game.Tutorials.TutorialEventActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ActivationQueue`  
- `private Unity.Jobs.JobHandle m_InputDependencies`  

## Constructors

- `public TutorialEventActivationSystem()`  

## Methods

- `public AddQueueWriter(Unity.Jobs.JobHandle dependency) : System.Void`  
- `public GetQueue(Unity.Jobs.JobHandle& dependency) : Unity.Collections.NativeQueue<Unity.Entities.Entity>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

