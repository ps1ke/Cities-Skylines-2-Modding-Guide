# Colossal.Collections.NativeHeapAllocator

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `NativeContainer`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal Colossal.Collections.UnsafeHeapAllocator* m_HeapData`  
- `internal Unity.Collections.Allocator m_AllocatorLabel`  

## Properties

- `public System.Boolean IsCreated { get }`  
- `public System.UInt32 MinimumAlignment { get }`  
- `public System.UInt32 FreeSpace { get }`  
- `public System.UInt32 UsedSpace { get }`  
- `public System.UInt32 OnePastHighestUsedAddress { get }`  
- `public System.UInt32 Size { get }`  
- `public System.Boolean Empty { get }`  
- `public System.Boolean Full { get }`  

## Constructors

- `public NativeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator)`  
- `private NativeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator, System.Int32 disposeSentinelStackDepth)`  

## Methods

- `public Allocate(System.UInt32 size, System.UInt32 alignment = 1) : Colossal.Collections.NativeHeapBlock`  
- `private CheckRead() : System.Void`  
- `private CheckWrite() : System.Void`  
- `public Clear() : System.Void`  
- `public Dispose() : System.Void`  
- `public Release(Colossal.Collections.NativeHeapBlock block) : System.Void`  
- `public Resize(System.UInt32 newSize) : System.Boolean`  

