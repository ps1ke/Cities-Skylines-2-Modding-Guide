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
public HeapAllocator(ulong size = 0uL, uint minimumAlignment = 1u)
	{
		m_SizeBins = new NativeList<SizeBin>(Allocator.Persistent);
		m_Blocks = new NativeList<BlocksOfSize>(Allocator.Persistent);
		m_BlocksFreelist = new NativeList<int>(Allocator.Persistent);
		m_FreeEndpoints = new NativeParallelHashMap<ulong, ulong>(0, Allocator.Persistent);
		m_Size = 0uL;
		m_Free = 0uL;
		m_MinimumAlignmentLog2 = math.tzcnt(minimumAlignment);
		m_IsCreated = true;
		Resize(size);
	}
```


## Methods

- `private AddNewBin(Game.Rendering.Utilities.HeapAllocator+SizeBin& bin, System.Int32 index) : System.Int32`  

```csharp
private unsafe int AddNewBin(ref SizeBin bin, int index)
	{
		if (m_BlocksFreelist.IsEmpty)
		{
			bin.blocksId = m_Blocks.Length;
			m_Blocks.Add(new BlocksOfSize(0));
		}
		else
		{
			int num = m_BlocksFreelist.Length - 1;
			bin.blocksId = m_BlocksFreelist[num];
			m_BlocksFreelist.ResizeUninitialized(num);
		}
		int num2 = m_SizeBins.Length - index;
		m_SizeBins.ResizeUninitialized(m_SizeBins.Length + 1);
		SizeBin* unsafePtr = m_SizeBins.GetUnsafePtr();
		UnsafeUtility.MemMove(unsafePtr + (index + 1), unsafePtr + index, num2 * UnsafeUtility.SizeOf<SizeBin>());
		unsafePtr[index] = bin;
		return index;
	}
```

- `public Allocate(System.UInt64 size, System.UInt32 alignment = 1) : Game.Rendering.Utilities.HeapBlock`  

```csharp
public HeapBlock Allocate(ulong size, uint alignment = 1u)
	{
		size = NextAligned(size, m_MinimumAlignmentLog2);
		alignment = math.max(alignment, MinimumAlignment);
		SizeBin sizeBin = new SizeBin(size, alignment);
		for (int i = FindSmallestSufficientBin(sizeBin); i < m_SizeBins.Length; i++)
		{
			SizeBin bin = m_SizeBins[i];
			if (CanFitAllocation(sizeBin, bin))
			{
				HeapBlock block = PopBlockFromBin(bin, i);
				return CutAllocationFromBlock(sizeBin, block);
			}
		}
		return default(HeapBlock);
	}
```

- `private CanFitAllocation(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapAllocator+SizeBin bin) : System.Boolean`  

```csharp
private bool CanFitAllocation(SizeBin allocation, SizeBin bin)
	{
		if (m_Blocks[bin.blocksId].Empty)
		{
			return false;
		}
		if (bin.HasCompatibleAlignment(allocation))
		{
			return true;
		}
		return bin.Size >= allocation.Size + allocation.Alignment;
	}
```

- `public Clear() : System.Void`  

```csharp
public void Clear()
	{
		ulong size = m_Size;
		m_SizeBins.Clear();
		m_Blocks.Clear();
		m_BlocksFreelist.Clear();
		m_FreeEndpoints.Clear();
		m_Size = 0uL;
		m_Free = 0uL;
		Resize(size);
	}
```

- `private Coalesce(Game.Rendering.Utilities.HeapBlock block, System.UInt64 endpoint) : Game.Rendering.Utilities.HeapBlock`  

```csharp
private HeapBlock Coalesce(HeapBlock block)
	{
		block = Coalesce(block, block.begin);
		block = Coalesce(block, block.end);
		return block;
	}
```

- `private Coalesce(Game.Rendering.Utilities.HeapBlock block) : Game.Rendering.Utilities.HeapBlock`  

```csharp
private HeapBlock Coalesce(HeapBlock block)
	{
		block = Coalesce(block, block.begin);
		block = Coalesce(block, block.end);
		return block;
	}
```

- `private CutAllocationFromBlock(Game.Rendering.Utilities.HeapAllocator+SizeBin allocation, Game.Rendering.Utilities.HeapBlock block) : Game.Rendering.Utilities.HeapBlock`  

```csharp
private HeapBlock CutAllocationFromBlock(SizeBin allocation, HeapBlock block)
	{
		if (allocation.Size == block.Length)
		{
			return block;
		}
		ulong num = NextAligned(block.begin, allocation.AlignmentLog2);
		ulong num2 = num + allocation.Size;
		if (num > block.begin)
		{
			Release(new HeapBlock(block.begin, num));
		}
		if (num2 < block.end)
		{
			Release(new HeapBlock(num2, block.end));
		}
		return new HeapBlock(num, num2);
	}
```

- `public DebugValidateInternalState() : System.Void`  

```csharp
public void DebugValidateInternalState()
	{
		int length = m_SizeBins.Length;
		int length2 = m_BlocksFreelist.Length;
		int num = 0;
		int num2 = 0;
		for (int i = 0; i < m_Blocks.Length; i++)
		{
			if (m_Blocks[i].Empty)
			{
				num++;
			}
			else
			{
				num2++;
			}
		}
		Assert.AreEqual(length, num2, "There should be exactly one non-empty block list per size bin");
		Assert.AreEqual(num, length2, "All empty block lists should be in the free list");
		for (int j = 0; j < m_BlocksFreelist.Length; j++)
		{
			int index = m_BlocksFreelist[j];
			Assert.IsTrue(m_Blocks[index].Empty, "There should be only empty block lists in the free list");
		}
		ulong num3 = 0uL;
		int num4 = 0;
		for (int k = 0; k < m_SizeBins.Length; k++)
		{
			SizeBin sizeBin = m_SizeBins[k];
			ulong size = sizeBin.Size;
			uint alignment = sizeBin.Alignment;
			BlocksOfSize blocksOfSize = m_Blocks[sizeBin.blocksId];
			Assert.IsFalse(blocksOfSize.Empty, "All block lists should be non-empty, empty lists should be removed");
			int length3 = blocksOfSize.Length;
			for (int l = 0; l < length3; l++)
			{
				HeapBlock block = blocksOfSize.Block(l);
				SizeBin sizeBin2 = new SizeBin(block);
				Assert.AreEqual(size, sizeBin2.Size, "Block size should match its bin");
				Assert.AreEqual(alignment, sizeBin2.Alignment, "Block alignment should match its bin");
				num3 += block.Length;
				if (m_FreeEndpoints.TryGetValue(block.begin, out var item))
				{
					Assert.AreEqual(block.end, item, "Free block end does not match stored endpoint");
				}
				else
				{
					Assert.IsTrue(condition: false, "No end endpoint found for free block");
				}
				if (m_FreeEndpoints.TryGetValue(block.end, out var item2))
				{
					Assert.AreEqual(block.begin, item2, "Free block begin does not match stored endpoint");
				}
				else
				{
					Assert.IsTrue(condition: false, "No begin endpoint found for free block");
				}
				num4++;
			}
		}
		Assert.AreEqual(num3, FreeSpace, "Free size reported incorrectly");
		Assert.IsTrue(num3 <= Size, "Amount of free size larger than maximum");
		Assert.AreEqual(2 * num4, m_FreeEndpoints.Count(), "Each free block should have exactly 2 stored endpoints");
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		if (IsCreated)
		{
			for (int i = 0; i < m_Blocks.Length; i++)
			{
				m_Blocks[i].Dispose();
			}
			m_FreeEndpoints.Dispose();
			m_Blocks.Dispose();
			m_BlocksFreelist.Dispose();
			m_SizeBins.Dispose();
			m_IsCreated = false;
		}
	}
```

- `private FindSmallestSufficientBin(Game.Rendering.Utilities.HeapAllocator+SizeBin needle) : System.Int32`  

```csharp
private int FindSmallestSufficientBin(SizeBin needle)
	{
		if (m_SizeBins.Length == 0)
		{
			return 0;
		}
		int num = 0;
		int num2 = m_SizeBins.Length;
		int num4;
		while (true)
		{
			int num3 = (num2 - num) / 2;
			if (num3 == 0)
			{
				if (needle.CompareTo(m_SizeBins[num]) <= 0)
				{
					return num;
				}
				return num + 1;
			}
			num4 = num + num3;
			int num5 = needle.CompareTo(m_SizeBins[num4]);
			if (num5 < 0)
			{
				num2 = num4;
				continue;
			}
			if (num5 <= 0)
			{
				break;
			}
			num = num4;
		}
		return num4;
	}
```

- `private static NextAligned(System.UInt64 offset, System.Int32 alignmentLog2) : System.UInt64`  

```csharp
private static ulong NextAligned(ulong offset, int alignmentLog2)
	{
		int num = (1 << alignmentLog2) - 1;
		return (ulong)((long)offset + (long)num >>> alignmentLog2 << alignmentLog2);
	}
```

- `private PopBlockFromBin(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index) : Game.Rendering.Utilities.HeapBlock`  

```csharp
private HeapBlock PopBlockFromBin(SizeBin bin, int index)
	{
		HeapBlock heapBlock = m_Blocks[bin.blocksId].Pop();
		RemoveEndpoints(heapBlock);
		m_Free -= heapBlock.Length;
		RemoveBinIfEmpty(bin, index);
		return heapBlock;
	}
```

- `public Release(Game.Rendering.Utilities.HeapBlock block) : System.Void`  

```csharp
public void Release(HeapBlock block)
	{
		block = Coalesce(block);
		SizeBin bin = new SizeBin(block);
		int num = FindSmallestSufficientBin(bin);
		if (num >= m_SizeBins.Length || bin.CompareTo(m_SizeBins[num]) != 0)
		{
			num = AddNewBin(ref bin, num);
		}
		m_Blocks[m_SizeBins[num].blocksId].Push(block);
		m_Free += block.Length;
		m_FreeEndpoints[block.begin] = block.end;
		m_FreeEndpoints[block.end] = block.begin;
	}
```

- `private RemoveBinIfEmpty(Game.Rendering.Utilities.HeapAllocator+SizeBin bin, System.Int32 index) : System.Void`  

```csharp
private unsafe void RemoveBinIfEmpty(SizeBin bin, int index)
	{
		if (m_Blocks[bin.blocksId].Empty)
		{
			int num = m_SizeBins.Length - (index + 1);
			SizeBin* unsafePtr = m_SizeBins.GetUnsafePtr();
			UnsafeUtility.MemMove(unsafePtr + index, unsafePtr + (index + 1), num * UnsafeUtility.SizeOf<SizeBin>());
			m_SizeBins.ResizeUninitialized(m_SizeBins.Length - 1);
			m_BlocksFreelist.Add(in bin.blocksId);
		}
	}
```

- `private RemoveEndpoints(Game.Rendering.Utilities.HeapBlock block) : System.Void`  

```csharp
private void RemoveEndpoints(HeapBlock block)
	{
		m_FreeEndpoints.Remove(block.begin);
		m_FreeEndpoints.Remove(block.end);
	}
```

- `private RemoveFreeBlock(Game.Rendering.Utilities.HeapBlock block) : System.Void`  

```csharp
private void RemoveFreeBlock(HeapBlock block)
	{
		RemoveEndpoints(block);
		SizeBin needle = new SizeBin(block);
		int index = FindSmallestSufficientBin(needle);
		m_Blocks[m_SizeBins[index].blocksId].Remove(block);
		RemoveBinIfEmpty(m_SizeBins[index], index);
		m_Free -= block.Length;
	}
```

- `public Resize(System.UInt64 newSize) : System.Boolean`  

```csharp
public bool Resize(ulong newSize)
	{
		if (newSize == m_Size)
		{
			return true;
		}
		if (newSize > m_Size)
		{
			ulong size = newSize - m_Size;
			HeapBlock block = HeapBlock.OfSize(m_Size, size);
			Release(block);
			m_Size = newSize;
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.Rendering.Utilities.HeapAllocator+SizeBin`  
- `Game.Rendering.Utilities.HeapAllocator+BlocksOfSize`  

