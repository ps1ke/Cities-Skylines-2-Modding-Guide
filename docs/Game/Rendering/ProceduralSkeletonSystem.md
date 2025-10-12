# Game.Rendering.ProceduralSkeletonSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Colossal.Collections.NativeHeapAllocator m_HeapAllocator`  
- `private Colossal.Rendering.SparseUploader m_SparseUploader`  
- `private Colossal.Rendering.ThreadedSparseUploader m_ThreadedSparseUploader`  
- `private Unity.Collections.NativeReference<Game.Rendering.ProceduralSkeletonSystem+AllocationInfo> m_AllocationInfo`  
- `private Unity.Collections.NativeQueue<Game.Rendering.ProceduralSkeletonSystem+AllocationRemove> m_AllocationRemoves`  
- `private System.Boolean m_IsAllocating`  
- `private System.Boolean m_IsUploading`  
- `private UnityEngine.GraphicsBuffer m_ComputeBuffer`  
- `private Unity.Jobs.JobHandle m_HeapDeps`  
- `private Unity.Jobs.JobHandle m_UploadDeps`  
- `private System.Int32 m_HeapAllocatorByteSize`  
- `private System.Int32 m_CurrentTime`  
- `private System.Boolean m_AreMotionVectorsEnabled`  
- `private System.Boolean m_ForceHistoryUpdate`  
- `public static const System.UInt32 SKELETON_MEMORY_DEFAULT`  
- `public static const System.UInt32 SKELETON_MEMORY_INCREMENT`  
- `public static const System.UInt32 UPLOADER_CHUNK_SIZE`  

## Properties

- `public System.Boolean isMotionBlurEnabled { get }`  
- `public System.Boolean forceHistoryUpdate { get }`  

## Constructors

- `public ProceduralSkeletonSystem()`  

## Methods

- `public AddHeapWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddUploadWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `private AllocateIdentityEntry() : System.Void`  
- `public BeginUpload(System.Int32 opCount, System.UInt32 dataSize, System.UInt32 maxOpSize, System.Int32& historyByteOffset) : Colossal.Rendering.ThreadedSparseUploader`  
- `public CompleteUpload() : System.Void`  
- `public GetHeapAllocator(Unity.Collections.NativeReference`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationInfo, Unity.Collections.NativeQueue`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationRemove, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationRemoves, System.Int32& currentTime, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeHeapAllocator`  
- `public GetMemoryStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& currentUpload, System.UInt32& uploadSize, System.Int32& allocationCount) : System.Void`  
- `public static GetSkinMatrices(Game.Rendering.Skeleton skeleton, Unity.Entities.DynamicBuffer`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBones, Unity.Entities.DynamicBuffer`1[[Game.Rendering.Bone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bones, Unity.Collections.NativeList<Unity.Mathematics.float4x4> tempMatrices) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Rendering.ProceduralSkeletonSystem+AllocationInfo`  
- `Game.Rendering.ProceduralSkeletonSystem+AllocationRemove`  
- `Game.Rendering.ProceduralSkeletonSystem+RemoveAllocationsJob`  

