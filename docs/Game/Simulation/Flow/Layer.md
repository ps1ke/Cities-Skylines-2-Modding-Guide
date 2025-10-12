# Game.Simulation.Flow.Layer

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Simulation.Flow.CutElement> m_Elements`  
- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Simulation.Flow.CutElementRef> m_ElementRefs`  
- `private System.Int32 m_UsedElementCount`  
- `private System.Int32 m_UsedElementRefCount`  
- `private System.Int32 m_FreeElementIndex`  
- `private System.Int32 m_FreeElementRefIndex`  

## Properties

- `public System.Boolean isEmpty { get }`  
- `public System.Int32 usedElementCount { get }`  
- `public System.Int32 usedElementRefCount { get }`  

## Constructors

- `public Layer(System.Int32 initialLength, Unity.Collections.Allocator allocator)`  

## Methods

- `public AddCutElement(Game.Simulation.Flow.CutElement& element) : System.Int32`  
- `public AddCutElementRef(Game.Simulation.Flow.CutElementRef& elementRef) : System.Int32`  
- `private static AddRange<T>(UnsafeList`1& unsafeList, Unity.Collections.NativeSlice<T> slice) : System.Void`  
- `private static AddRange<T>(Unity.Collections.NativeList<T> list, Unity.Collections.LowLevel.Unsafe.UnsafeList<T> unsafeList) : System.Void`  
- `public ContainsCutElement(Game.Simulation.Flow.Identifier id) : System.Boolean`  
- `public ContainsCutElementForConnection(Game.Simulation.Flow.Identifier id, Game.Simulation.Flow.Connection connection, System.Boolean admissible) : System.Boolean`  
- `public Dispose() : System.Void`  
- `public FreeCutElement(System.Int32 index) : System.Void`  
- `public FreeCutElementRef(System.Int32 index) : System.Void`  
- `public GetCutElement(System.Int32 index) : Game.Simulation.Flow.CutElement&`  
- `public GetCutElementRef(System.Int32 index) : Game.Simulation.Flow.CutElementRef&`  
- `public static Load(Game.Simulation.Flow.LayerState state, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElement> layerElements, System.Int32& elementIndex, Unity.Collections.NativeArray<Game.Simulation.Flow.CutElementRef> layerElementRefs, System.Int32& elementRefIndex) : Game.Simulation.Flow.Layer`  
- `public MergeGroups(System.Int32 elementId1, System.Int32 elementId2) : System.Void`  
- `public RemoveElementLink(System.Int32 elementIndex, System.Int32 upperLayerIndex, System.Int32 upperLayerElementIndex) : System.Void`  
- `public Save(Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> layerStates, Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> layerElements, Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> layerElementRefs) : System.Void`  

