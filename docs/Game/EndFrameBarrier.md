# Game.EndFrameBarrier

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Game.SafeCommandBufferSystem`  

## Fields

- `private System.Diagnostics.Stopwatch m_Stopwatch`  
- `private Unity.Jobs.JobHandle <producerHandle>k__BackingField`  
- `private System.Single <lastElapsedTime>k__BackingField`  

## Properties

- `public Unity.Jobs.JobHandle producerHandle { get; private set }`  
- `public System.Single lastElapsedTime { get; private set }`  
- `public System.Single currentElapsedTime { get }`  

## Constructors

- `public EndFrameBarrier()`  

## Methods

- `public AddJobHandleForProducer(Unity.Jobs.JobHandle producerJob) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

