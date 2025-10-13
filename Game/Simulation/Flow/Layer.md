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
public Layer(System.Int32 initialLength, Unity.Collections.Allocator allocator);
```


## Methods

- `public AddCutElement(Game.Simulation.Flow.CutElement& element) : System.Int32`  

```csharp
public System.Int32 AddCutElement(Game.Simulation.Flow.CutElement& element);
```

- `public AddCutElementRef(Game.Simulation.Flow.CutElementRef& elementRef) : System.Int32`  

```csharp
public System.Int32 AddCutElementRef(Game.Simulation.Flow.CutElementRef& elementRef);
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
public System.Boolean ContainsCutElement(Game.Simulation.Flow.Identifier id);
```

- `public ContainsCutElementForConnection(Game.Simulation.Flow.Identifier id, Game.Simulation.Flow.Connection connection, System.Boolean admissible) : System.Boolean`  

```csharp
public System.Boolean ContainsCutElementForConnection(Game.Simulation.Flow.Identifier id, Game.Simulation.Flow.Connection connection, System.Boolean admissible);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public FreeCutElement(System.Int32 index) : System.Void`  

```csharp
public System.Void FreeCutElement(System.Int32 index);
```

- `public FreeCutElementRef(System.Int32 index) : System.Void`  

```csharp
public System.Void FreeCutElementRef(System.Int32 index);
```

- `public GetCutElement(System.Int32 index) : Game.Simulation.Flow.CutElement&`  

```csharp
public Game.Simulation.Flow.CutElement& GetCutElement(System.Int32 index);
```

- `public GetCutElementRef(System.Int32 index) : Game.Simulation.Flow.CutElementRef&`  

```csharp
public Game.Simulation.Flow.CutElementRef& GetCutElementRef(System.Int32 index);
```

- `public static Load(Game.Simulation.Flow.LayerState state, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElement> layerElements, System.Int32& elementIndex, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElementRef> layerElementRefs, System.Int32& elementRefIndex) : Game.Simulation.Flow.Layer`  

```csharp
public static Game.Simulation.Flow.Layer Load(Game.Simulation.Flow.LayerState state, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElement> layerElements, System.Int32& elementIndex, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElementRef> layerElementRefs, System.Int32& elementRefIndex);
```

- `public MergeGroups(System.Int32 elementId1, System.Int32 elementId2) : System.Void`  

```csharp
public System.Void MergeGroups(System.Int32 elementId1, System.Int32 elementId2);
```

- `public RemoveElementLink(System.Int32 elementIndex, System.Int32 upperLayerIndex, System.Int32 upperLayerElementIndex) : System.Void`  

```csharp
public System.Void RemoveElementLink(System.Int32 elementIndex, System.Int32 upperLayerIndex, System.Int32 upperLayerElementIndex);
```

- `public Save(Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs) : System.Void`  

```csharp
public System.Void Save(Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs);
```


