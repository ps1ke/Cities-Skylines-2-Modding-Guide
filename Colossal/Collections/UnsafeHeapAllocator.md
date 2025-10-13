# Colossal.Collections.UnsafeHeapAllocator

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct UnsafeHeapAllocator : System.IDisposable
{
    private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeHeapAllocator+SizeBin> m_SizeBins;
    private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeHeapAllocator+BlocksOfSize> m_Blocks;
    private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32> m_BlocksFreelist;
    private Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashMap<System.UInt32, System.UInt32> m_FreeEndpoints;
    private System.UInt32 m_Size;
    private System.UInt32 m_Free;
    private readonly System.Int32 m_MinimumAlignmentLog2;
    private System.Boolean m_IsCreated;
    private Unity.Collections.Allocator m_AllocatorLabel;
    public static const System.Int32 MaxAlignmentLog2;
    public static const System.Int32 AlignmentBits;

    public System.UInt32 MinimumAlignment { get; }
    public System.UInt32 FreeSpace { get; }
    public System.UInt32 UsedSpace { get; }
    public System.UInt32 OnePastHighestUsedAddress { get; }
    public System.UInt32 Size { get; }
    public System.Boolean Empty { get; }
    public System.Boolean Full { get; }
    public System.Boolean IsCreated { get; }

    public UnsafeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator);

    private System.Int32 AddNewBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin& bin, System.Int32 index);
    public Colossal.Collections.UnsafeHeapBlock Allocate(System.UInt32 size, System.UInt32 alignment);
    private System.Boolean CanFitAllocation(Colossal.Collections.UnsafeHeapAllocator+SizeBin allocation, Colossal.Collections.UnsafeHeapAllocator+SizeBin bin);
    public System.Void Clear();
    private Colossal.Collections.UnsafeHeapBlock Coalesce(Colossal.Collections.UnsafeHeapBlock block, System.UInt32 endpoint);
    private Colossal.Collections.UnsafeHeapBlock Coalesce(Colossal.Collections.UnsafeHeapBlock block);
    private Colossal.Collections.UnsafeHeapBlock CutAllocationFromBlock(Colossal.Collections.UnsafeHeapAllocator+SizeBin allocation, Colossal.Collections.UnsafeHeapBlock block);
    public System.Void DebugValidateInternalState();
    public System.Void Dispose();
    private System.Int32 FindSmallestSufficientBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin needle);
    private static System.UInt32 NextAligned(System.UInt32 offset, System.Int32 alignmentLog2);
    private Colossal.Collections.UnsafeHeapBlock PopBlockFromBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin bin, System.Int32 index);
    public System.Void Release(Colossal.Collections.UnsafeHeapBlock block);
    private System.Void RemoveBinIfEmpty(Colossal.Collections.UnsafeHeapAllocator+SizeBin bin, System.Int32 index);
    private System.Void RemoveEndpoints(Colossal.Collections.UnsafeHeapBlock block);
    private System.Void RemoveFreeBlock(Colossal.Collections.UnsafeHeapBlock block);
    public System.Boolean Resize(System.UInt32 newSize);
}
```


## Fields

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeHeapAllocator+SizeBin> m_SizeBins`  

```csharp
private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeHeapAllocator+SizeBin> m_SizeBins;
```

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeHeapAllocator+BlocksOfSize> m_Blocks`  

```csharp
private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeHeapAllocator+BlocksOfSize> m_Blocks;
```

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32> m_BlocksFreelist`  

```csharp
private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Int32> m_BlocksFreelist;
```

- `private Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashMap<System.UInt32, System.UInt32> m_FreeEndpoints`  

```csharp
private Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashMap<System.UInt32, System.UInt32> m_FreeEndpoints;
```

- `private System.UInt32 m_Size`  

```csharp
private System.UInt32 m_Size;
```

- `private System.UInt32 m_Free`  

```csharp
private System.UInt32 m_Free;
```

- `private readonly System.Int32 m_MinimumAlignmentLog2`  

```csharp
private readonly System.Int32 m_MinimumAlignmentLog2;
```

- `private System.Boolean m_IsCreated`  

```csharp
private System.Boolean m_IsCreated;
```

- `private Unity.Collections.Allocator m_AllocatorLabel`  

```csharp
private Unity.Collections.Allocator m_AllocatorLabel;
```

- `public static const System.Int32 MaxAlignmentLog2`  

```csharp
public static const System.Int32 MaxAlignmentLog2;
```

- `public static const System.Int32 AlignmentBits`  

```csharp
public static const System.Int32 AlignmentBits;
```


## Properties

- `public System.UInt32 MinimumAlignment { get }`  

```csharp
public System.UInt32 MinimumAlignment { get; }
```

- `public System.UInt32 FreeSpace { get }`  

```csharp
public System.UInt32 FreeSpace { get; }
```

- `public System.UInt32 UsedSpace { get }`  

```csharp
public System.UInt32 UsedSpace { get; }
```

- `public System.UInt32 OnePastHighestUsedAddress { get }`  

```csharp
public System.UInt32 OnePastHighestUsedAddress { get; }
```

- `public System.UInt32 Size { get }`  

```csharp
public System.UInt32 Size { get; }
```

- `public System.Boolean Empty { get }`  

```csharp
public System.Boolean Empty { get; }
```

- `public System.Boolean Full { get }`  

```csharp
public System.Boolean Full { get; }
```

- `public System.Boolean IsCreated { get }`  

```csharp
public System.Boolean IsCreated { get; }
```


## Constructors

- `public UnsafeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator)`  

```csharp
public UnsafeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator);
```


## Methods

- `private AddNewBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin& bin, System.Int32 index) : System.Int32`  

```csharp
private System.Int32 AddNewBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin& bin, System.Int32 index);
```

- `public Allocate(System.UInt32 size, System.UInt32 alignment = 1) : Colossal.Collections.UnsafeHeapBlock`  

```csharp
public Colossal.Collections.UnsafeHeapBlock Allocate(System.UInt32 size, System.UInt32 alignment);
```

- `private CanFitAllocation(Colossal.Collections.UnsafeHeapAllocator+SizeBin allocation, Colossal.Collections.UnsafeHeapAllocator+SizeBin bin) : System.Boolean`  

```csharp
private System.Boolean CanFitAllocation(Colossal.Collections.UnsafeHeapAllocator+SizeBin allocation, Colossal.Collections.UnsafeHeapAllocator+SizeBin bin);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `private Coalesce(Colossal.Collections.UnsafeHeapBlock block, System.UInt32 endpoint) : Colossal.Collections.UnsafeHeapBlock`  

```csharp
private Colossal.Collections.UnsafeHeapBlock Coalesce(Colossal.Collections.UnsafeHeapBlock block, System.UInt32 endpoint);
```

- `private Coalesce(Colossal.Collections.UnsafeHeapBlock block) : Colossal.Collections.UnsafeHeapBlock`  

```csharp
private Colossal.Collections.UnsafeHeapBlock Coalesce(Colossal.Collections.UnsafeHeapBlock block);
```

- `private CutAllocationFromBlock(Colossal.Collections.UnsafeHeapAllocator+SizeBin allocation, Colossal.Collections.UnsafeHeapBlock block) : Colossal.Collections.UnsafeHeapBlock`  

```csharp
private Colossal.Collections.UnsafeHeapBlock CutAllocationFromBlock(Colossal.Collections.UnsafeHeapAllocator+SizeBin allocation, Colossal.Collections.UnsafeHeapBlock block);
```

- `public DebugValidateInternalState() : System.Void`  

```csharp
public System.Void DebugValidateInternalState();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private FindSmallestSufficientBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin needle) : System.Int32`  

```csharp
private System.Int32 FindSmallestSufficientBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin needle);
```

- `private static NextAligned(System.UInt32 offset, System.Int32 alignmentLog2) : System.UInt32`  

```csharp
private static System.UInt32 NextAligned(System.UInt32 offset, System.Int32 alignmentLog2);
```

- `private PopBlockFromBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin bin, System.Int32 index) : Colossal.Collections.UnsafeHeapBlock`  

```csharp
private Colossal.Collections.UnsafeHeapBlock PopBlockFromBin(Colossal.Collections.UnsafeHeapAllocator+SizeBin bin, System.Int32 index);
```

- `public Release(Colossal.Collections.UnsafeHeapBlock block) : System.Void`  

```csharp
public System.Void Release(Colossal.Collections.UnsafeHeapBlock block);
```

- `private RemoveBinIfEmpty(Colossal.Collections.UnsafeHeapAllocator+SizeBin bin, System.Int32 index) : System.Void`  

```csharp
private System.Void RemoveBinIfEmpty(Colossal.Collections.UnsafeHeapAllocator+SizeBin bin, System.Int32 index);
```

- `private RemoveEndpoints(Colossal.Collections.UnsafeHeapBlock block) : System.Void`  

```csharp
private System.Void RemoveEndpoints(Colossal.Collections.UnsafeHeapBlock block);
```

- `private RemoveFreeBlock(Colossal.Collections.UnsafeHeapBlock block) : System.Void`  

```csharp
private System.Void RemoveFreeBlock(Colossal.Collections.UnsafeHeapBlock block);
```

- `public Resize(System.UInt32 newSize) : System.Boolean`  

```csharp
public System.Boolean Resize(System.UInt32 newSize);
```


## Nested types

- `Colossal.Collections.UnsafeHeapAllocator+SizeBin`  
- `Colossal.Collections.UnsafeHeapAllocator+BlocksOfSize`  

