# Game.Rendering.AnimatedSystem+AllocationData

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Colossal.Collections.NativeHeapAllocator m_BoneAllocator`  
- `private Unity.Collections.NativeList<Game.Rendering.MetaBufferData> m_MetaBufferData`  
- `private Unity.Collections.NativeList<System.Int32> m_FreeMetaIndices`  
- `private Unity.Collections.NativeList<System.Int32> m_UpdatedMetaIndices`  
- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AllocationRemove> m_BoneAllocationRemoves`  
- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+IndexRemove> m_MetaBufferRemoves`  
- `private System.Int32 m_CurrentTime`  

## Constructors

- `public AllocationData(Colossal.Collections.NativeHeapAllocator boneAllocator, Unity.Collections.NativeList<Game.Rendering.MetaBufferData> metaBufferData, Unity.Collections.NativeList<System.Int32> freeMetaIndices, Unity.Collections.NativeList<System.Int32> updatedMetaIndices, Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AllocationRemove> boneAllocationRemoves, Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+IndexRemove> metaBufferRemoves, System.Int32 currentTime)`  

## Methods

- `public AddMetaBufferData(Game.Rendering.MetaBufferData metaBufferData) : System.Int32`  
- `public AllocateBones(System.Int32 boneCount) : Colossal.Collections.NativeHeapBlock`  
- `public ReleaseBones(Colossal.Collections.NativeHeapBlock allocation) : System.Void`  
- `public RemoveMetaBufferData(System.Int32 metaIndex) : System.Void`  

