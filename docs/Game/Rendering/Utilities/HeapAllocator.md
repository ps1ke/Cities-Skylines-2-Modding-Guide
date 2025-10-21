# Game.Rendering.Utilities.HeapAllocator

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct HeapAllocator : System.IDisposable
{
    private Unity.Collections.NativeList<Game.Rendering.Utilities.HeapAllocator+SizeBin> m_SizeBins;
    private Unity.Collections.NativeList<Game.Rendering.Utilities.HeapAllocator+BlocksOfSize> m_Blocks;
    private Unity.Collections.NativeList<System.Int32> m_BlocksFreelist;
    private Unity.Collections.NativeParallelHashMap<System.UInt64, System.UInt64> m_FreeEndpoints;
    private System.UInt64 m_Size;
    private System.UInt64 m_Free;
    private readonly System.Int32 m_MinimumAlignmentLog2;
    private System.Boolean m_IsCreated;
    public static const System.Int32 MaxAlignmentLog2;
    public static const System.Int32 AlignmentBits;

    public System.UInt32 MinimumAlignment { get; }
    public System.UInt64 FreeSpace { get; }
    public System.UInt64 UsedSpace { get; }
    public System.UInt64 OnePastHighestUsedAddress { get; }
    public System.UInt64 Size { get; }
    public System.Boolean Empty { get; }
    public System.Boolean Full { get; }
    public System.Boolean IsCreated { get; }

    public HeapAllocator(System.UInt64 size, System.UInt32 minimumAlignment);

    private System.Int32 AddNewBin(Game.Rendering.Utilities.HeapAllocator+SizeBin& bin, System.Int32 index);
    public Game.Rendering.Utilities.HeapBlock Allocate(System.UInt64 size, System.UInt32 alignment);
    private System.Boolean CanFitAllocation(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapAllocator+SizeBin bin);
    public System.Void Clear();
    private Game.Rendering.Utilities.HeapBlock Coalesce(Game.Rendering.Utilities.HeapBlock block, System.UInt64 endpoint);
    private Game.Rendering.Utilities.HeapBlock Coalesce(Game.Rendering.Utilities.HeapBlock block);
    private Game.Rendering.Utilities.HeapBlock CutAllocationFromBlock(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapBlock block);
    public System.Void DebugValidateInternalState();
    public System.Void Dispose();
    private System.Int32 FindSmallestSufficientBin(Game.Rendering.Utilities.HeapAllocator+SizeBin needle);
    private static System.UInt64 NextAligned(System.UInt64 offset, System.Int32 alignmentLog2);
    private Game.Rendering.Utilities.HeapBlock PopBlockFromBin(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index);
    public System.Void Release(Game.Rendering.Utilities.HeapBlock block);
    private System.Void RemoveBinIfEmpty(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index);
    private System.Void RemoveEndpoints(Game.Rendering.Utilities.HeapBlock block);
    private System.Void RemoveFreeBlock(Game.Rendering.Utilities.HeapBlock block);
    public System.Boolean Resize(System.UInt64 newSize);
}
```


## Fields

- `private Unity.Collections.NativeList<Game.Rendering.Utilities.HeapAllocator+SizeBin> m_SizeBins`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.Utilities.HeapAllocator+SizeBin> m_SizeBins;
```

- `private Unity.Collections.NativeList<Game.Rendering.Utilities.HeapAllocator+BlocksOfSize> m_Blocks`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.Utilities.HeapAllocator+BlocksOfSize> m_Blocks;
```

- `private Unity.Collections.NativeList<System.Int32> m_BlocksFreelist`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_BlocksFreelist;
```

- `private Unity.Collections.NativeParallelHashMap<System.UInt64, System.UInt64> m_FreeEndpoints`  

```csharp
private Unity.Collections.NativeParallelHashMap<System.UInt64, System.UInt64> m_FreeEndpoints;
```

- `private System.UInt64 m_Size`  

```csharp
private System.UInt64 m_Size;
```

- `private System.UInt64 m_Free`  

```csharp
private System.UInt64 m_Free;
```

- `private readonly System.Int32 m_MinimumAlignmentLog2`  

```csharp
private readonly System.Int32 m_MinimumAlignmentLog2;
```

- `private System.Boolean m_IsCreated`  

```csharp
private System.Boolean m_IsCreated;
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

- `public System.UInt64 FreeSpace { get }`  

```csharp
public System.UInt64 FreeSpace { get; }
```

- `public System.UInt64 UsedSpace { get }`  

```csharp
public System.UInt64 UsedSpace { get; }
```

- `public System.UInt64 OnePastHighestUsedAddress { get }`  

```csharp
public System.UInt64 OnePastHighestUsedAddress { get; }
```

- `public System.UInt64 Size { get }`  

```csharp
public System.UInt64 Size { get; }
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

- `public HeapAllocator(System.UInt64 size = 0, System.UInt32 minimumAlignment = 1)`  

```csharp
public HeapAllocator(System.UInt64 size, System.UInt32 minimumAlignment);
```


## Methods

- `private AddNewBin(Game.Rendering.Utilities.HeapAllocator+SizeBin& bin, System.Int32 index) : System.Int32`  

```csharp
private System.Int32 AddNewBin(Game.Rendering.Utilities.HeapAllocator+SizeBin& bin, System.Int32 index);
```

- `public Allocate(System.UInt64 size, System.UInt32 alignment = 1) : Game.Rendering.Utilities.HeapBlock`  

```csharp
public Game.Rendering.Utilities.HeapBlock Allocate(System.UInt64 size, System.UInt32 alignment);
```

- `private CanFitAllocation(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapAllocator+SizeBin bin) : System.Boolean`  

```csharp
private System.Boolean CanFitAllocation(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapAllocator+SizeBin bin);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `private Coalesce(Game.Rendering.Utilities.HeapBlock block, System.UInt64 endpoint) : Game.Rendering.Utilities.HeapBlock`  

```csharp
private Game.Rendering.Utilities.HeapBlock Coalesce(Game.Rendering.Utilities.HeapBlock block, System.UInt64 endpoint);
```

- `private Coalesce(Game.Rendering.Utilities.HeapBlock block) : Game.Rendering.Utilities.HeapBlock`  

```csharp
private Game.Rendering.Utilities.HeapBlock Coalesce(Game.Rendering.Utilities.HeapBlock block);
```

- `private CutAllocationFromBlock(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapBlock block) : Game.Rendering.Utilities.HeapBlock`  

```csharp
private Game.Rendering.Utilities.HeapBlock CutAllocationFromBlock(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapBlock block);
```

- `public DebugValidateInternalState() : System.Void`  

```csharp
public System.Void DebugValidateInternalState();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private FindSmallestSufficientBin(Game.Rendering.Utilities.HeapAllocator+SizeBin needle) : System.Int32`  

```csharp
private System.Int32 FindSmallestSufficientBin(Game.Rendering.Utilities.HeapAllocator+SizeBin needle);
```

- `private static NextAligned(System.UInt64 offset, System.Int32 alignmentLog2) : System.UInt64`  

```csharp
private static System.UInt64 NextAligned(System.UInt64 offset, System.Int32 alignmentLog2);
```

- `private PopBlockFromBin(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index) : Game.Rendering.Utilities.HeapBlock`  

```csharp
private Game.Rendering.Utilities.HeapBlock PopBlockFromBin(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index);
```

- `public Release(Game.Rendering.Utilities.HeapBlock block) : System.Void`  

```csharp
public System.Void Release(Game.Rendering.Utilities.HeapBlock block);
```

- `private RemoveBinIfEmpty(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index) : System.Void`  

```csharp
private System.Void RemoveBinIfEmpty(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index);
```

- `private RemoveEndpoints(Game.Rendering.Utilities.HeapBlock block) : System.Void`  

```csharp
private System.Void RemoveEndpoints(Game.Rendering.Utilities.HeapBlock block);
```

- `private RemoveFreeBlock(Game.Rendering.Utilities.HeapBlock block) : System.Void`  

```csharp
private System.Void RemoveFreeBlock(Game.Rendering.Utilities.HeapBlock block);
```

- `public Resize(System.UInt64 newSize) : System.Boolean`  

```csharp
public System.Boolean Resize(System.UInt64 newSize);
```


## Nested types

- `Game.Rendering.Utilities.HeapAllocator+SizeBin`  
- `Game.Rendering.Utilities.HeapAllocator+BlocksOfSize`  

