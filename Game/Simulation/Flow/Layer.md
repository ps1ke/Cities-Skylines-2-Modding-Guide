# Game.Simulation.Flow.Layer

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct Layer : System.IDisposable
{
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Simulation.Flow.CutElement> m_Elements;
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Simulation.Flow.CutElementRef> m_ElementRefs;
    private System.Int32 m_UsedElementCount;
    private System.Int32 m_UsedElementRefCount;
    private System.Int32 m_FreeElementIndex;
    private System.Int32 m_FreeElementRefIndex;

    public System.Boolean isEmpty { get; }
    public System.Int32 usedElementCount { get; }
    public System.Int32 usedElementRefCount { get; }

    public Layer(System.Int32 initialLength, Unity.Collections.Allocator allocator);

    public System.Int32 AddCutElement(Game.Simulation.Flow.CutElement& element);
    public System.Int32 AddCutElementRef(Game.Simulation.Flow.CutElementRef& elementRef);
    private static System.Void AddRange<T>(UnsafeList`1& unsafeList, Unity.Collections.NativeSlice<T> slice);
    private static System.Void AddRange<T>(Unity.Collections.NativeList<T> list, Unity.Collections.LowLevel.Unsafe.UnsafeList<T> unsafeList);
    public System.Boolean ContainsCutElement(Game.Simulation.Flow.Identifier id);
    public System.Boolean ContainsCutElementForConnection(Game.Simulation.Flow.Identifier id, Game.Simulation.Flow.Connection connection, System.Boolean admissible);
    public System.Void Dispose();
    public System.Void FreeCutElement(System.Int32 index);
    public System.Void FreeCutElementRef(System.Int32 index);
    public Game.Simulation.Flow.CutElement& GetCutElement(System.Int32 index);
    public Game.Simulation.Flow.CutElementRef& GetCutElementRef(System.Int32 index);
    public static Game.Simulation.Flow.Layer Load(Game.Simulation.Flow.LayerState state, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElement> layerElements, System.Int32& elementIndex, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElementRef> layerElementRefs, System.Int32& elementRefIndex);
    public System.Void MergeGroups(System.Int32 elementId1, System.Int32 elementId2);
    public System.Void RemoveElementLink(System.Int32 elementIndex, System.Int32 upperLayerIndex, System.Int32 upperLayerElementIndex);
    public System.Void Save(Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs);
}
```


## Fields

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Simulation.Flow.CutElement> m_Elements`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Simulation.Flow.CutElement> m_Elements;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Simulation.Flow.CutElementRef> m_ElementRefs`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Simulation.Flow.CutElementRef> m_ElementRefs;
```

- `private System.Int32 m_UsedElementCount`  

```csharp
private System.Int32 m_UsedElementCount;
```

- `private System.Int32 m_UsedElementRefCount`  

```csharp
private System.Int32 m_UsedElementRefCount;
```

- `private System.Int32 m_FreeElementIndex`  

```csharp
private System.Int32 m_FreeElementIndex;
```

- `private System.Int32 m_FreeElementRefIndex`  

```csharp
private System.Int32 m_FreeElementRefIndex;
```


## Properties

- `public System.Boolean isEmpty { get }`  

```csharp
public System.Boolean isEmpty { get; }
```

- `public System.Int32 usedElementCount { get }`  

```csharp
public System.Int32 usedElementCount { get; }
```

- `public System.Int32 usedElementRefCount { get }`  

```csharp
public System.Int32 usedElementRefCount { get; }
```


## Constructors

- `public Layer(System.Int32 initialLength, Unity.Collections.Allocator allocator)`  

```csharp
public Layer(int initialLength, Allocator allocator)
	{
		m_Elements = new UnsafeList<CutElement>(initialLength, allocator, NativeArrayOptions.ClearMemory);
		m_Elements.Length = initialLength;
		m_ElementRefs = new UnsafeList<CutElementRef>(initialLength, allocator, NativeArrayOptions.ClearMemory);
		m_ElementRefs.Length = initialLength;
		m_UsedElementCount = 0;
		m_UsedElementRefCount = 0;
		if (initialLength > 0)
		{
			m_FreeElementIndex = 0;
			m_FreeElementRefIndex = 0;
			int num = initialLength - 1;
			for (int i = 0; i < initialLength; i++)
			{
				int nextIndex = ((i == num) ? (-1) : (i + 1));
				CutElement value = m_Elements[i];
				value.m_NextIndex = nextIndex;
				m_Elements[i] = value;
				CutElementRef value2 = m_ElementRefs[i];
				value2.m_NextIndex = nextIndex;
				m_ElementRefs[i] = value2;
			}
		}
		else
		{
			m_FreeElementIndex = -1;
			m_FreeElementRefIndex = -1;
		}
	}
```


## Methods

- `public AddCutElement(Game.Simulation.Flow.CutElement& element) : System.Int32`  

```csharp
public int AddCutElement(in CutElement element)
	{
		int num = m_FreeElementIndex;
		if (num != -1)
		{
			m_FreeElementIndex = m_Elements[num].m_NextIndex;
		}
		else
		{
			num = m_Elements.Length;
			m_Elements.Resize(num + 1, NativeArrayOptions.ClearMemory);
		}
		m_Elements[num] = element;
		m_UsedElementCount++;
		return num;
	}
```

- `public AddCutElementRef(Game.Simulation.Flow.CutElementRef& elementRef) : System.Int32`  

```csharp
public int AddCutElementRef(in CutElementRef elementRef)
	{
		int num = m_FreeElementRefIndex;
		if (num != -1)
		{
			m_FreeElementRefIndex = m_ElementRefs[num].m_NextIndex;
		}
		else
		{
			num = m_ElementRefs.Length;
			m_ElementRefs.Resize(num + 1, NativeArrayOptions.ClearMemory);
		}
		m_ElementRefs[num] = elementRef;
		m_UsedElementRefCount++;
		return num;
	}
```

- `private static AddRange<T>(UnsafeList`1& unsafeList, Unity.Collections.NativeSlice<T> slice) : System.Void`  

```csharp
private static System.Void AddRange<T>(UnsafeList`1& unsafeList, Unity.Collections.NativeSlice<T> slice);
```

- `private static AddRange<T>(Unity.Collections.NativeList<T> list, Unity.Collections.LowLevel.Unsafe.UnsafeList<T> unsafeList) : System.Void`  

```csharp
private static System.Void AddRange<T>(Unity.Collections.NativeList<T> list, Unity.Collections.LowLevel.Unsafe.UnsafeList<T> unsafeList);
```

- `public ContainsCutElement(Game.Simulation.Flow.Identifier id) : System.Boolean`  

```csharp
public bool ContainsCutElement(Identifier id)
	{
		if (id.m_Index != -1)
		{
			CutElement cutElement = m_Elements[id.m_Index];
			if (cutElement.isCreated && cutElement.m_Version == id.m_Version)
			{
				return true;
			}
		}
		return false;
	}
```

- `public ContainsCutElementForConnection(Game.Simulation.Flow.Identifier id, Game.Simulation.Flow.Connection connection, System.Boolean admissible) : System.Boolean`  

```csharp
public bool ContainsCutElementForConnection(Identifier id, Connection connection, bool admissible)
	{
		if (id.m_Index != -1 && id.m_Index < m_Elements.Length)
		{
			CutElement cutElement = m_Elements[id.m_Index];
			if (cutElement.isCreated && cutElement.m_Version == id.m_Version && cutElement.m_Edge == connection.m_Edge && cutElement.m_StartNode == connection.m_StartNode && cutElement.m_EndNode == connection.m_EndNode && cutElement.isAdmissible == admissible)
			{
				return true;
			}
		}
		return false;
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_Elements.Dispose();
		m_ElementRefs.Dispose();
	}
```

- `public FreeCutElement(System.Int32 index) : System.Void`  

```csharp
public void FreeCutElement(int index)
	{
		ref CutElement reference = ref m_Elements.ElementAt(index);
		reference.m_Flags = CutElementFlags.None;
		reference.m_NextIndex = m_FreeElementIndex;
		m_FreeElementIndex = index;
		m_UsedElementCount--;
	}
```

- `public FreeCutElementRef(System.Int32 index) : System.Void`  

```csharp
public void FreeCutElementRef(int index)
	{
		ref CutElementRef reference = ref m_ElementRefs.ElementAt(index);
		reference.m_Layer = -1;
		reference.m_Index = -1;
		reference.m_NextIndex = m_FreeElementRefIndex;
		m_FreeElementRefIndex = index;
		m_UsedElementRefCount--;
	}
```

- `public GetCutElement(System.Int32 index) : Game.Simulation.Flow.CutElement&`  

```csharp
public ref CutElement GetCutElement(int index)
	{
		return ref m_Elements.ElementAt(index);
	}
```

- `public GetCutElementRef(System.Int32 index) : Game.Simulation.Flow.CutElementRef&`  

```csharp
public ref CutElementRef GetCutElementRef(int index)
	{
		return ref m_ElementRefs.ElementAt(index);
	}
```

- `public static Load(Game.Simulation.Flow.LayerState state, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElement> layerElements, System.Int32& elementIndex, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElementRef> layerElementRefs, System.Int32& elementRefIndex) : Game.Simulation.Flow.Layer`  

```csharp
public static Layer Load(LayerState state, NativeArray<CutElement> layerElements, ref int elementIndex, NativeArray<CutElementRef> layerElementRefs, ref int elementRefIndex)
	{
		UnsafeList<CutElement> unsafeList = new UnsafeList<CutElement>(state.m_ElementsLength, Allocator.Temp);
		AddRange(ref unsafeList, layerElements.Slice(elementIndex, state.m_ElementsLength));
		UnsafeList<CutElementRef> unsafeList2 = new UnsafeList<CutElementRef>(state.m_ElementRefsLength, Allocator.Temp);
		AddRange(ref unsafeList2, layerElementRefs.Slice(elementRefIndex, state.m_ElementRefsLength));
		elementIndex += state.m_ElementsLength;
		elementRefIndex += state.m_ElementRefsLength;
		return new Layer
		{
			m_Elements = unsafeList,
			m_ElementRefs = unsafeList2,
			m_UsedElementCount = state.m_UsedElementCount,
			m_UsedElementRefCount = state.m_UsedElementRefCount,
			m_FreeElementIndex = state.m_FreeElementIndex,
			m_FreeElementRefIndex = state.m_FreeElementRefIndex
		};
	}
```

- `public MergeGroups(System.Int32 elementId1, System.Int32 elementId2) : System.Void`  

```csharp
public void MergeGroups(int elementId1, int elementId2)
	{
		ref CutElement cutElement = ref GetCutElement(elementId1);
		CutElement cutElement2 = GetCutElement(elementId2);
		int num = cutElement.m_Group;
		int num2 = cutElement2.m_Group;
		if (num == num2)
		{
			return;
		}
		int nextIndex = cutElement.m_NextIndex;
		cutElement.m_NextIndex = num2;
		int num3 = num2;
		do
		{
			ref CutElement cutElement3 = ref GetCutElement(num3);
			cutElement3.m_Group = num;
			num3 = cutElement3.m_NextIndex;
			if (num3 == -1)
			{
				cutElement3.m_NextIndex = nextIndex;
			}
		}
		while (num3 != -1);
	}
```

- `public RemoveElementLink(System.Int32 elementIndex, System.Int32 upperLayerIndex, System.Int32 upperLayerElementIndex) : System.Void`  

```csharp
public void RemoveElementLink(int elementIndex, int upperLayerIndex, int upperLayerElementIndex)
	{
		ref CutElement cutElement = ref GetCutElement(elementIndex);
		int num = -1;
		int num2 = cutElement.m_LinkedElements;
		while (num2 != -1)
		{
			CutElementRef cutElementRef = GetCutElementRef(num2);
			if (cutElementRef.m_Layer == upperLayerIndex && cutElementRef.m_Index == upperLayerElementIndex)
			{
				break;
			}
			num = num2;
			num2 = cutElementRef.m_NextIndex;
		}
		ref CutElementRef cutElementRef2 = ref GetCutElementRef(num2);
		if (num == -1)
		{
			cutElement.m_LinkedElements = cutElementRef2.m_NextIndex;
		}
		else
		{
			GetCutElementRef(num).m_NextIndex = cutElementRef2.m_NextIndex;
		}
		FreeCutElementRef(num2);
	}
```

- `public Save(Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs) : System.Void`  

```csharp
public void Save(NativeList<LayerState> layerStates, NativeList<CutElement> layerElements, NativeList<CutElementRef> layerElementRefs)
	{
		LayerState value = new LayerState
		{
			m_ElementsLength = m_Elements.Length,
			m_ElementRefsLength = m_ElementRefs.Length,
			m_UsedElementCount = m_UsedElementCount,
			m_UsedElementRefCount = m_UsedElementRefCount,
			m_FreeElementIndex = m_FreeElementIndex,
			m_FreeElementRefIndex = m_FreeElementRefIndex
		};
		layerStates.Add(in value);
		AddRange(layerElements, m_Elements);
		AddRange(layerElementRefs, m_ElementRefs);
	}
```


