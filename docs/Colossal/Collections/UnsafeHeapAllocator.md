# Colossal.Collections.UnsafeHeapAllocator

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `GenerateTestsForBurstCompatibility`  

## Fields

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeHeapAllocator+SizeBin> m_SizeBins`  
- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeHeapAllocator+BlocksOfSize> m_Blocks`  
- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32> m_BlocksFreelist`  
- `private Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashMap<System.UInt32, System.UInt32> m_FreeEndpoints`  
- `private System.UInt32 m_Size`  
- `private System.UInt32 m_Free`  
- `private readonly System.Int32 m_MinimumAlignmentLog2`  
- `private System.Boolean m_IsCreated`  
- `private Unity.Collections.Allocator m_AllocatorLabel`  
- `public static const System.Int32 MaxAlignmentLog2`  
- `public static const System.Int32 AlignmentBits`  

## Properties

- `public System.UInt32 MinimumAlignment { get }`  
- `public System.UInt32 FreeSpace { get }`  
- `public System.UInt32 UsedSpace { get }`  
- `public System.UInt32 OnePastHighestUsedAddress { get }`  
- `public System.UInt32 Size { get }`  
- `public System.Boolean Empty { get }`  
- `public System.Boolean Full { get }`  
- `public System.Boolean IsCreated { get }`  

## Constructors

- `public UnsafeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator)`  

## Methods

- `private AddNewBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin& bin, System.Int32 index) : System.Int32`  
- `public Allocate(System.UInt32 size, System.UInt32 alignment = 1) : Colossal.Collections.UnsafeHeapBlock`  
- `private CanFitAllocation(Colossal.Collections.UnsafeHeapAllocator+SizeBin allocation, Colossal.Collections.UnsafeHeapAllocator+SizeBin bin) : System.Boolean`  
- `public Clear() : System.Void`  
- `private Coalesce(Colossal.Collections.UnsafeHeapBlock block, System.UInt32 endpoint) : Colossal.Collections.UnsafeHeapBlock`  
- `private Coalesce(Colossal.Collections.UnsafeHeapBlock block) : Colossal.Collections.UnsafeHeapBlock`  
- `private CutAllocationFromBlock(Colossal.Collections.UnsafeHeapAllocator+SizeBin allocation, Colossal.Collections.UnsafeHeapBlock block) : Colossal.Collections.UnsafeHeapBlock`  
- `public DebugValidateInternalState() : System.Void`  
- `public Dispose() : System.Void`  
- `private FindSmallestSufficientBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin needle) : System.Int32`  
- `private static NextAligned(System.UInt32 offset, System.Int32 alignmentLog2) : System.UInt32`  
- `private PopBlockFromBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin bin, System.Int32 index) : Colossal.Collections.UnsafeHeapBlock`  
- `public Release(Colossal.Collections.UnsafeHeapBlock block) : System.Void`  
- `private RemoveBinIfEmpty(Colossal.Collections.UnsafeHeapAllocator+SizeBin bin, System.Int32 index) : System.Void`  
- `private RemoveEndpoints(Colossal.Collections.UnsafeHeapBlock block) : System.Void`  
- `private RemoveFreeBlock(Colossal.Collections.UnsafeHeapBlock block) : System.Void`  
- `public Resize(System.UInt32 newSize) : System.Boolean`  

## Nested types

- `Colossal.Collections.UnsafeHeapAllocator+SizeBin`  
- `Colossal.Collections.UnsafeHeapAllocator+BlocksOfSize`  

