# Game.Debug.DebugWatchDistribution

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Unity.Collections.NativeQueue<System.Int32> m_RawData`  
- `private Unity.Jobs.JobHandle m_Deps`  
- `private System.Boolean m_Persistent`  
- `private System.Boolean m_Relative`  

## Properties

- `public System.Boolean Persistent { get }`  
- `public System.Boolean Relative { get }`  
- `public System.Boolean IsEnabled { get }`  

## Constructors

- `public DebugWatchDistribution(System.Boolean persistent = False, System.Boolean relative = False)`  

## Methods

- `public AddWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public Disable() : System.Void`  
- `public Dispose() : System.Void`  
- `public Enable() : System.Void`  
- `public GetQueue(System.Boolean clear, Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<System.Int32>`  

## Nested types

- `Game.Debug.DebugWatchDistribution+ClearJob`  

