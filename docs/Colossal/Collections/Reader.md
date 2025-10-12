# Colossal.Collections.NativeParallelQueue`1+Reader

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerSupportsMinMaxWriteRestriction`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal Colossal.Collections.NativeParallelQueueData* m_Buffer`  
- `internal Colossal.Collections.NativeParallelQueueBlockPoolData* m_QueuePool`  
- `internal System.Int32 m_HashRange`  
- `internal System.Int32 m_BufferSize`  

## Properties

- `public System.Int32 HashRange { get }`  

## Methods

- `private CheckRead(System.Int32 hashIndex) : System.Void`  
- `private CheckReadNotEmpty(System.Int32 hashIndex) : System.Void`  
- `private CheckWrite(System.Int32 hashIndex) : System.Void`  
- `public Dequeue(System.Int32 hashIndex) : T`  
- `public GetCount(System.Int32 hashIndex) : System.Int32`  
- `public GetEnumerator(System.Int32 hashIndex) : Colossal.Collections.NativeParallelQueue<T>`  
- `public IsEmpty(System.Int32 hashIndex) : System.Boolean`  
- `public Peek(System.Int32 hashIndex) : T`  
- `public ToArray(System.Int32 hashIndex, Unity.Collections.AllocatorManager+AllocatorHandle allocator) : Unity.Collections.NativeArray<T>`  
- `public TryDequeue(System.Int32 hashIndex, T& item) : System.Boolean`  

