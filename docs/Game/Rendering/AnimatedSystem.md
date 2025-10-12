# Game.Rendering.AnimatedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Colossal.Collections.NativeHeapAllocator m_BoneAllocator`  
- `private Colossal.Collections.NativeHeapAllocator m_AnimAllocator`  
- `private Colossal.Collections.NativeHeapAllocator m_IndexAllocator`  
- `private Unity.Collections.NativeList<Game.Rendering.MetaBufferData> m_MetaBufferData`  
- `private Unity.Collections.NativeList<System.Int32> m_FreeMetaIndices`  
- `private Unity.Collections.NativeList<System.Int32> m_UpdatedMetaIndices`  
- `private Unity.Collections.NativeList<Game.Rendering.RestPoseInstance> m_InstanceIndices`  
- `private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_BodyInstances`  
- `private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_FaceInstances`  
- `private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_CorrectiveInstances`  
- `private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition> m_BodyTransitions`  
- `private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition2> m_BodyTransitions2`  
- `private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition> m_FaceTransitions`  
- `private Unity.Collections.NativeList<Game.Rendering.AnimatedSystem+ClipPriorityData> m_ClipPriorities`  
- `private Unity.Collections.NativeList<Game.Rendering.AnimatedSystem+AnimationClipData> m_AnimationClipData`  
- `private Unity.Collections.NativeList<System.Int32> m_FreeAnimIndices`  
- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AllocationRemove> m_BoneAllocationRemoves`  
- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+IndexRemove> m_MetaBufferRemoves`  
- `private UnityEngine.ComputeBuffer m_BoneBuffer`  
- `private UnityEngine.ComputeBuffer m_BoneHistoryBuffer`  
- `private UnityEngine.ComputeBuffer m_LocalTRSBlendPoseBuffer`  
- `private UnityEngine.ComputeBuffer m_LocalTRSBoneBuffer`  
- `private UnityEngine.ComputeBuffer m_AnimInfoBuffer`  
- `private UnityEngine.ComputeBuffer m_AnimBuffer`  
- `private UnityEngine.ComputeBuffer m_MetaBuffer`  
- `private UnityEngine.ComputeBuffer m_IndexBuffer`  
- `private UnityEngine.ComputeBuffer m_InstanceBuffer`  
- `private UnityEngine.ComputeBuffer m_BodyInstanceBuffer`  
- `private UnityEngine.ComputeBuffer m_FaceInstanceBuffer`  
- `private UnityEngine.ComputeBuffer m_CorrectiveInstanceBuffer`  
- `private UnityEngine.ComputeBuffer m_BodyTransitionBuffer`  
- `private UnityEngine.ComputeBuffer m_BodyTransition2Buffer`  
- `private UnityEngine.ComputeBuffer m_FaceTransitionBuffer`  
- `private System.Int32 m_AnimationCount`  
- `private System.Int32 m_MaxBoneCount`  
- `private System.Int32 m_MaxActiveBoneCount`  
- `private System.Int32 m_CurrentTime`  
- `private System.Boolean m_IsAllocating`  
- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_PropIDs`  
- `private UnityEngine.ComputeShader m_AnimationComputeShader`  
- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> m_TempAnimationQueue`  
- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> m_TempPriorityQueue`  
- `private Unity.Jobs.JobHandle m_AllocateDeps`  
- `private System.Int32 m_BlendAnimationLayer0KernelIx`  
- `private System.Int32 m_BlendAnimationLayer1KernelIx`  
- `private System.Int32 m_BlendAnimationLayer2KernelIx`  
- `private System.Int32 m_BlendTransitionLayer0KernelIx`  
- `private System.Int32 m_BlendTransition2Layer0KernelIx`  
- `private System.Int32 m_BlendTransitionLayer1KernelIx`  
- `private System.Int32 m_BlendRestPoseKernelIx`  
- `private System.Int32 m_ConvertLocalCoordinatesKernelIx`  
- `private System.Int32 m_ConvertLocalCoordinatesWithHistoryKernelIx`  
- `private System.Int32 m_IndexBufferID`  
- `private System.Int32 m_MetadataBufferID`  
- `private System.Int32 m_MetaIndexBufferID`  
- `private System.Int32 m_AnimatedInstanceBufferID`  
- `private System.Int32 m_AnimatedTransitionBufferID`  
- `private System.Int32 m_AnimatedTransition2BufferID`  
- `private System.Int32 m_AnimationInfoBufferID`  
- `private System.Int32 m_AnimationBoneBufferID`  
- `private System.Int32 m_InstanceCountID`  
- `private System.Int32 m_BodyInstanceCountID`  
- `private System.Int32 m_BodyTransitionCountID`  
- `private System.Int32 m_BodyTransition2CountID`  
- `private System.Int32 m_FaceInstanceCountID`  
- `private System.Int32 m_FaceTransitionCountID`  
- `private System.Int32 m_CorrectiveInstanceCountID`  
- `private System.Int32 m_LocalTRSBlendPoseBufferID`  
- `private System.Int32 m_LocalTRSBoneBufferID`  
- `private System.Int32 m_BoneBufferID`  
- `private System.Int32 m_BoneHistoryBufferID`  
- `private static Colossal.Logging.ILog log`  
- `public static const System.UInt32 BONEBUFFER_MEMORY_DEFAULT`  
- `public static const System.UInt32 BONEBUFFER_MEMORY_INCREMENT`  
- `public static const System.UInt32 ANIMBUFFER_MEMORY_DEFAULT`  
- `public static const System.UInt32 ANIMBUFFER_MEMORY_INCREMENT`  
- `public static const System.UInt32 METABUFFER_MEMORY_DEFAULT`  
- `public static const System.UInt32 METABUFFER_MEMORY_INCREMENT`  
- `public static const System.UInt32 INDEXBUFFER_MEMORY_DEFAULT`  
- `public static const System.UInt32 INDEXBUFFER_MEMORY_INCREMENT`  
- `public static const System.UInt32 MAX_ASYNC_LOADING_COUNT`  
- `private static const System.String ANIMATION_COMPUTE_SHADER_RESOURCE`  
- `private static const System.String SHADER_BLEND_ANIMATION_LAYER0_KERNEL_NAME`  
- `private static const System.String SHADER_BLEND_ANIMATION_LAYER1_KERNEL_NAME`  
- `private static const System.String SHADER_BLEND_ANIMATION_LAYER2_KERNEL_NAME`  
- `private static const System.String SHADER_BLEND_TRANSITION_LAYER0_KERNEL_NAME`  
- `private static const System.String SHADER_BLEND_TRANSITION2_LAYER0_KERNEL_NAME`  
- `private static const System.String SHADER_BLEND_TRANSITION_LAYER1_KERNEL_NAME`  
- `private static const System.String SHADER_BLEND_REST_POSE_KERNEL_NAME`  
- `private static const System.String SHADER_CONVERT_COORDINATES_KERNEL_NAME`  
- `private static const System.String SHADER_CONVERT_COORDINATES_WITH_HISTORY_KERNEL_NAME`  

## Constructors

- `public AnimatedSystem()`  

## Methods

- `public AddAllocationWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddAnimationWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `private AllocateIndexData(System.UInt32 size) : Colossal.Collections.NativeHeapBlock`  
- `private CacheRestPose(Unity.Entities.Entity style, Colossal.Animations.AnimationClip restPose) : System.Void`  
- `private FindTargetRotation(Colossal.Animations.AnimationClip animation, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements) : System.Single`  
- `private FindTargetValue(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements) : System.Single`  
- `public GetAllocationData(Unity.Jobs.JobHandle& dependencies) : Game.Rendering.AnimatedSystem+AllocationData`  
- `public GetAnimationData(Unity.Jobs.JobHandle& dependencies) : Game.Rendering.AnimatedSystem+AnimationData`  
- `public GetAnimStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  
- `public GetBoneStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  
- `public GetIndexStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  
- `public GetMetaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  
- `public GetPropID(System.String name) : Game.Rendering.AnimatedPropID`  
- `private LoadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex, Colossal.Animations.AnimationClip animation) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private PlayAnimations() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private RemoveRootMotion(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Entities.DynamicBuffer<Game.Prefabs.RestPoseElement> restPose, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> motions, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements) : System.Void`  
- `private ResizeAnimBuffer() : System.Void`  
- `private ResizeAnimInfoBuffer() : System.Void`  
- `private ResizeBoneBuffer() : System.Void`  
- `private ResizeBoneHistoryBuffer() : System.Void`  
- `private ResizeIndexBuffer() : System.Void`  
- `private ResizeMetaBuffer() : System.Void`  
- `private UnCacheRestPose(Unity.Entities.Entity style) : System.Void`  
- `private UnloadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex) : System.Void`  
- `private UpdateAnimations() : System.Void`  
- `private UpdateInstanceBuffer<T>(UnityEngine.ComputeBuffer& buffer, Unity.Collections.NativeList<T> data, System.String name) : System.Void`  
- `private UpdateInstances() : System.Void`  
- `private UpdateMetaData() : System.Void`  

## Nested types

- `Game.Rendering.AnimatedSystem+Prepare`  
- `Game.Rendering.AnimatedSystem+AddAnimationInstancesJob`  
- `Game.Rendering.AnimatedSystem+UpdateAnimationPriorityJob`  
- `Game.Rendering.AnimatedSystem+AnimationData`  
- `Game.Rendering.AnimatedSystem+EndAllocationJob`  
- `Game.Rendering.AnimatedSystem+IndexRemove`  
- `Game.Rendering.AnimatedSystem+AllocationRemove`  
- `Game.Rendering.AnimatedSystem+AllocationData`  
- `Game.Rendering.AnimatedSystem+ReverseIntComparer`  
- `Game.Rendering.AnimatedSystem+AnimationLayerData`  
- `Game.Rendering.AnimatedSystem+AnimationLayerData2`  
- `Game.Rendering.AnimatedSystem+AnimationFrameData`  
- `Game.Rendering.AnimatedSystem+ClipPriorityData`  
- `Game.Rendering.AnimatedSystem+ClipIndex`  
- `Game.Rendering.AnimatedSystem+AnimationClipData`  

