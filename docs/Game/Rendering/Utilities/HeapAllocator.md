# Game.Rendering.Utilities.HeapAllocator

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `private Unity.Collections.NativeList<Game.Rendering.Utilities.HeapAllocator+SizeBin> m_SizeBins`  
- `private Unity.Collections.NativeList<Game.Rendering.Utilities.HeapAllocator+BlocksOfSize> m_Blocks`  
- `private Unity.Collections.NativeList<System.Int32> m_BlocksFreelist`  
- `private Unity.Collections.NativeParallelHashMap<System.UInt64, System.UInt64> m_FreeEndpoints`  
- `private System.UInt64 m_Size`  
- `private System.UInt64 m_Free`  
- `private readonly System.Int32 m_MinimumAlignmentLog2`  
- `private System.Boolean m_IsCreated`  
- `public static const System.Int32 MaxAlignmentLog2`  
- `public static const System.Int32 AlignmentBits`  

## Properties

- `public System.UInt32 MinimumAlignment { get }`  
- `public System.UInt64 FreeSpace { get }`  
- `public System.UInt64 UsedSpace { get }`  
- `public System.UInt64 OnePastHighestUsedAddress { get }`  
- `public System.UInt64 Size { get }`  
- `public System.Boolean Empty { get }`  
- `public System.Boolean Full { get }`  
- `public System.Boolean IsCreated { get }`  

## Constructors

- `public HeapAllocator(System.UInt64 size = 0, System.UInt32 minimumAlignment = 1)`  

## Methods

- `private AddNewBin(Game.Rendering.Utilities.HeapAllocator+SizeBin& bin, System.Int32 index) : System.Int32`  
- `public Allocate(System.UInt64 size, System.UInt32 alignment = 1) : Game.Rendering.Utilities.HeapBlock`  
- `private CanFitAllocation(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapAllocator+SizeBin bin) : System.Boolean`  
- `public Clear() : System.Void`  
- `private Coalesce(Game.Rendering.Utilities.HeapBlock block, System.UInt64 endpoint) : Game.Rendering.Utilities.HeapBlock`  
- `private Coalesce(Game.Rendering.Utilities.HeapBlock block) : Game.Rendering.Utilities.HeapBlock`  
- `private CutAllocationFromBlock(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapBlock block) : Game.Rendering.Utilities.HeapBlock`  
- `public DebugValidateInternalState() : System.Void`  
- `public Dispose() : System.Void`  
- `private FindSmallestSufficientBin(Game.Rendering.Utilities.HeapAllocator+SizeBin needle) : System.Int32`  
- `private static NextAligned(System.UInt64 offset, System.Int32 alignmentLog2) : System.UInt64`  
- `private PopBlockFromBin(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index) : Game.Rendering.Utilities.HeapBlock`  
- `public Release(Game.Rendering.Utilities.HeapBlock block) : System.Void`  
- `private RemoveBinIfEmpty(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index) : System.Void`  
- `private RemoveEndpoints(Game.Rendering.Utilities.HeapBlock block) : System.Void`  
- `private RemoveFreeBlock(Game.Rendering.Utilities.HeapBlock block) : System.Void`  
- `public Resize(System.UInt64 newSize) : System.Boolean`  

## Nested types

- `Game.Rendering.Utilities.HeapAllocator+SizeBin`  
- `Game.Rendering.Utilities.HeapAllocator+BlocksOfSize`  

