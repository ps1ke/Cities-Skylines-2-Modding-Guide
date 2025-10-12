# Game.Serialization.WriteBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Serialization.Entities.IWriteBuffer`, `System.IDisposable`  

## Fields

- `private Unity.Collections.NativeList<System.Byte> <buffer>k__BackingField`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private System.Boolean m_HasDependencies`  
- `private System.Boolean m_IsDone`  

## Properties

- `public Unity.Collections.NativeList<System.Byte> buffer { get; private set }`  
- `public System.Boolean isCompleted { get }`  

## Constructors

- `public WriteBuffer()`  

## Methods

- `public CompleteDependencies() : System.Void`  
- `public Dispose() : System.Void`  
- `private DisposeBuffers() : System.Void`  
- `public Done(Unity.Jobs.JobHandle handle) : System.Void`  
- `public Done() : System.Void`  

