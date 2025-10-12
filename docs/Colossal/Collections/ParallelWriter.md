# Colossal.Collections.NativeAccumulator`1+ParallelWriter

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerIsAtomicWriteOnly`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal System.Byte* m_Buffer`  
- `internal System.Int32 m_ThreadDataSize`  
- `internal System.Int32 m_ValueCount`  
- `internal System.Int32 m_ThreadIndex`  

## Methods

- `public Accumulate(T value) : System.Void`  
- `public Accumulate(System.Int32 index, T value) : System.Void`  
- `private CheckIndex(System.Int32 index) : System.Void`  
- `private CheckWrite() : System.Void`  

