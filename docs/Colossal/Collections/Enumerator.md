# Colossal.Collections.NativeParallelQueue`1+Enumerator

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.Collections.Generic.IEnumerator<T>`, `System.IDisposable`, `System.Collections.IEnumerator`  

**Attributes:** `NativeContainer`, `NativeContainerIsReadOnly`  

## Fields

- `internal Colossal.Collections.NativeParallelQueueData* m_Buffer`  
- `internal Colossal.Collections.NativeParallelQueueBlockHeader* m_Block`  
- `internal System.Int32 m_CurrentRead`  

## Properties

- `public T Current { get }`  
- `private System.Object System.Collections.IEnumerator.Current { private get }`  

## Methods

- `public Dispose() : System.Void`  
- `public MoveNext() : System.Boolean`  
- `public Reset() : System.Void`  

