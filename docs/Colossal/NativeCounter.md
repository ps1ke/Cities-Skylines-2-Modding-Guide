# Colossal.NativeCounter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`  

## Fields

- `private System.Int32* m_Counter`  
- `private Unity.Collections.Allocator m_AllocatorLabel`  

## Properties

- `public System.Int32 Count { get; set }`  
- `public System.Boolean IsCreated { get }`  

## Constructors

- `public NativeCounter(Unity.Collections.Allocator label)`  

## Methods

- `public Dispose() : System.Void`  
- `public Increment() : System.Void`  
- `public ToConcurrent() : Colossal.NativeCounter+Concurrent`  

## Nested types

- `Colossal.NativeCounter+Concurrent`  

