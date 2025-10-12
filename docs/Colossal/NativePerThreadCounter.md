# Colossal.NativePerThreadCounter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`  

## Fields

- `private System.Int32* m_Counter`  
- `private Unity.Collections.Allocator m_AllocatorLabel`  
- `public static const System.Int32 IntsPerCacheLine`  

## Properties

- `public System.Int32 Count { get; set }`  
- `public System.Boolean IsCreated { get }`  

## Constructors

- `public NativePerThreadCounter(Unity.Collections.Allocator label)`  

## Methods

- `public Dispose() : System.Void`  
- `public Increment() : System.Void`  
- `public ToConcurrent() : Colossal.NativePerThreadCounter+Concurrent`  

## Nested types

- `Colossal.NativePerThreadCounter+Concurrent`  

