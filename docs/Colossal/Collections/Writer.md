# Colossal.Collections.NativeParallelQueue`1+Writer

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerIsAtomicWriteOnly`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal Colossal.Collections.NativeParallelQueueData* m_Buffer`  
- `internal Colossal.Collections.NativeParallelQueueBlockPoolData* m_QueuePool`  
- `internal System.Int32 m_HashRange`  
- `internal System.Int32 m_BufferSize`  
- `internal System.Int32 m_ThreadIndex`  

## Properties

- `public System.Int32 HashRange { get }`  

## Methods

- `private CheckWrite() : System.Void`  
- `public Enqueue(T value) : System.Void`  
- `public Enqueue(System.Int32 hashCode, T value) : System.Void`  

