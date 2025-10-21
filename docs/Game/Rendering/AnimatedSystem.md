# Game.Rendering.AnimatedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimatedSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Colossal.Collections.NativeHeapAllocator m_BoneAllocator;
    private Colossal.Collections.NativeHeapAllocator m_AnimAllocator;
    private Colossal.Collections.NativeHeapAllocator m_IndexAllocator;
    private Unity.Collections.NativeList<Game.Rendering.MetaBufferData> m_MetaBufferData;
    private Unity.Collections.NativeList<System.Int32> m_FreeMetaIndices;
    private Unity.Collections.NativeList<System.Int32> m_UpdatedMetaIndices;
    private Unity.Collections.NativeList<Game.Rendering.RestPoseInstance> m_InstanceIndices;
    private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_BodyInstances;
    private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_FaceInstances;
    private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_CorrectiveInstances;
    private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition> m_BodyTransitions;
    private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition2> m_BodyTransitions2;
    private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition> m_FaceTransitions;
    private Unity.Collections.NativeList<Game.Rendering.AnimatedSystem+ClipPriorityData> m_ClipPriorities;
    private Unity.Collections.NativeList<Game.Rendering.AnimatedSystem+AnimationClipData> m_AnimationClipData;
    private Unity.Collections.NativeList<System.Int32> m_FreeAnimIndices;
    private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AllocationRemove> m_BoneAllocationRemoves;
    private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+IndexRemove> m_MetaBufferRemoves;
    private UnityEngine.ComputeBuffer m_BoneBuffer;
    private UnityEngine.ComputeBuffer m_BoneHistoryBuffer;
    private UnityEngine.ComputeBuffer m_LocalTRSBlendPoseBuffer;
    private UnityEngine.ComputeBuffer m_LocalTRSBoneBuffer;
    private UnityEngine.ComputeBuffer m_AnimInfoBuffer;
    private UnityEngine.ComputeBuffer m_AnimBuffer;
    private UnityEngine.ComputeBuffer m_MetaBuffer;
    private UnityEngine.ComputeBuffer m_IndexBuffer;
    private UnityEngine.ComputeBuffer m_InstanceBuffer;
    private UnityEngine.ComputeBuffer m_BodyInstanceBuffer;
    private UnityEngine.ComputeBuffer m_FaceInstanceBuffer;
    private UnityEngine.ComputeBuffer m_CorrectiveInstanceBuffer;
    private UnityEngine.ComputeBuffer m_BodyTransitionBuffer;
    private UnityEngine.ComputeBuffer m_BodyTransition2Buffer;
    private UnityEngine.ComputeBuffer m_FaceTransitionBuffer;
    private System.Int32 m_AnimationCount;
    private System.Int32 m_MaxBoneCount;
    private System.Int32 m_MaxActiveBoneCount;
    private System.Int32 m_CurrentTime;
    private System.Boolean m_IsAllocating;
    private System.Collections.Generic.Dictionary<System.String, System.Int32> m_PropIDs;
    private UnityEngine.ComputeShader m_AnimationComputeShader;
    private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> m_TempAnimationQueue;
    private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> m_TempPriorityQueue;
    private Unity.Jobs.JobHandle m_AllocateDeps;
    private System.Int32 m_BlendAnimationLayer0KernelIx;
    private System.Int32 m_BlendAnimationLayer1KernelIx;
    private System.Int32 m_BlendAnimationLayer2KernelIx;
    private System.Int32 m_BlendTransitionLayer0KernelIx;
    private System.Int32 m_BlendTransition2Layer0KernelIx;
    private System.Int32 m_BlendTransitionLayer1KernelIx;
    private System.Int32 m_BlendRestPoseKernelIx;
    private System.Int32 m_ConvertLocalCoordinatesKernelIx;
    private System.Int32 m_ConvertLocalCoordinatesWithHistoryKernelIx;
    private System.Int32 m_IndexBufferID;
    private System.Int32 m_MetadataBufferID;
    private System.Int32 m_MetaIndexBufferID;
    private System.Int32 m_AnimatedInstanceBufferID;
    private System.Int32 m_AnimatedTransitionBufferID;
    private System.Int32 m_AnimatedTransition2BufferID;
    private System.Int32 m_AnimationInfoBufferID;
    private System.Int32 m_AnimationBoneBufferID;
    private System.Int32 m_InstanceCountID;
    private System.Int32 m_BodyInstanceCountID;
    private System.Int32 m_BodyTransitionCountID;
    private System.Int32 m_BodyTransition2CountID;
    private System.Int32 m_FaceInstanceCountID;
    private System.Int32 m_FaceTransitionCountID;
    private System.Int32 m_CorrectiveInstanceCountID;
    private System.Int32 m_LocalTRSBlendPoseBufferID;
    private System.Int32 m_LocalTRSBoneBufferID;
    private System.Int32 m_BoneBufferID;
    private System.Int32 m_BoneHistoryBufferID;
    private static Colossal.Logging.ILog log;
    public static const System.UInt32 BONEBUFFER_MEMORY_DEFAULT;
    public static const System.UInt32 BONEBUFFER_MEMORY_INCREMENT;
    public static const System.UInt32 ANIMBUFFER_MEMORY_DEFAULT;
    public static const System.UInt32 ANIMBUFFER_MEMORY_INCREMENT;
    public static const System.UInt32 METABUFFER_MEMORY_DEFAULT;
    public static const System.UInt32 METABUFFER_MEMORY_INCREMENT;
    public static const System.UInt32 INDEXBUFFER_MEMORY_DEFAULT;
    public static const System.UInt32 INDEXBUFFER_MEMORY_INCREMENT;
    public static const System.UInt32 MAX_ASYNC_LOADING_COUNT;
    private static const System.String ANIMATION_COMPUTE_SHADER_RESOURCE;
    private static const System.String SHADER_BLEND_ANIMATION_LAYER0_KERNEL_NAME;
    private static const System.String SHADER_BLEND_ANIMATION_LAYER1_KERNEL_NAME;
    private static const System.String SHADER_BLEND_ANIMATION_LAYER2_KERNEL_NAME;
    private static const System.String SHADER_BLEND_TRANSITION_LAYER0_KERNEL_NAME;
    private static const System.String SHADER_BLEND_TRANSITION2_LAYER0_KERNEL_NAME;
    private static const System.String SHADER_BLEND_TRANSITION_LAYER1_KERNEL_NAME;
    private static const System.String SHADER_BLEND_REST_POSE_KERNEL_NAME;
    private static const System.String SHADER_CONVERT_COORDINATES_KERNEL_NAME;
    private static const System.String SHADER_CONVERT_COORDINATES_WITH_HISTORY_KERNEL_NAME;

    public AnimatedSystem();

    public System.Void AddAllocationWriter(Unity.Jobs.JobHandle handle);
    public System.Void AddAnimationWriter(Unity.Jobs.JobHandle handle);
    private Colossal.Collections.NativeHeapBlock AllocateIndexData(System.UInt32 size);
    private System.Void CacheRestPose(Unity.Entities.Entity style, Colossal.Animations.AnimationClip restPose);
    private System.Single FindTargetRotation(Colossal.Animations.AnimationClip animation, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements);
    private System.Single FindTargetValue(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements);
    public Game.Rendering.AnimatedSystem+AllocationData GetAllocationData(Unity.Jobs.JobHandle& dependencies);
    public Game.Rendering.AnimatedSystem+AnimationData GetAnimationData(Unity.Jobs.JobHandle& dependencies);
    public System.Void GetAnimStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
    public System.Void GetBoneStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
    public System.Void GetIndexStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
    public System.Void GetMetaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
    public Game.Rendering.AnimatedPropID GetPropID(System.String name);
    private System.Boolean LoadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex, Colossal.Animations.AnimationClip animation);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void PlayAnimations();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void RemoveRootMotion(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Entities.DynamicBuffer<Game.Prefabs.RestPoseElement> restPose, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> motions, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements);
    private System.Void ResizeAnimBuffer();
    private System.Void ResizeAnimInfoBuffer();
    private System.Void ResizeBoneBuffer();
    private System.Void ResizeBoneHistoryBuffer();
    private System.Void ResizeIndexBuffer();
    private System.Void ResizeMetaBuffer();
    private System.Void UnCacheRestPose(Unity.Entities.Entity style);
    private System.Void UnloadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex);
    private System.Void UpdateAnimations();
    private System.Void UpdateInstanceBuffer<T>(UnityEngine.ComputeBuffer& buffer, Unity.Collections.NativeList<T> data, System.String name);
    private System.Void UpdateInstances();
    private System.Void UpdateMetaData();
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Colossal.Collections.NativeHeapAllocator m_BoneAllocator`  

```csharp
private Colossal.Collections.NativeHeapAllocator m_BoneAllocator;
```

- `private Colossal.Collections.NativeHeapAllocator m_AnimAllocator`  

```csharp
private Colossal.Collections.NativeHeapAllocator m_AnimAllocator;
```

- `private Colossal.Collections.NativeHeapAllocator m_IndexAllocator`  

```csharp
private Colossal.Collections.NativeHeapAllocator m_IndexAllocator;
```

- `private Unity.Collections.NativeList<Game.Rendering.MetaBufferData> m_MetaBufferData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.MetaBufferData> m_MetaBufferData;
```

- `private Unity.Collections.NativeList<System.Int32> m_FreeMetaIndices`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_FreeMetaIndices;
```

- `private Unity.Collections.NativeList<System.Int32> m_UpdatedMetaIndices`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_UpdatedMetaIndices;
```

- `private Unity.Collections.NativeList<Game.Rendering.RestPoseInstance> m_InstanceIndices`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.RestPoseInstance> m_InstanceIndices;
```

- `private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_BodyInstances`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_BodyInstances;
```

- `private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_FaceInstances`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_FaceInstances;
```

- `private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_CorrectiveInstances`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AnimatedInstance> m_CorrectiveInstances;
```

- `private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition> m_BodyTransitions`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition> m_BodyTransitions;
```

- `private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition2> m_BodyTransitions2`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition2> m_BodyTransitions2;
```

- `private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition> m_FaceTransitions`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AnimatedTransition> m_FaceTransitions;
```

- `private Unity.Collections.NativeList<Game.Rendering.AnimatedSystem+ClipPriorityData> m_ClipPriorities`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AnimatedSystem+ClipPriorityData> m_ClipPriorities;
```

- `private Unity.Collections.NativeList<Game.Rendering.AnimatedSystem+AnimationClipData> m_AnimationClipData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AnimatedSystem+AnimationClipData> m_AnimationClipData;
```

- `private Unity.Collections.NativeList<System.Int32> m_FreeAnimIndices`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_FreeAnimIndices;
```

- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AllocationRemove> m_BoneAllocationRemoves`  

```csharp
private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AllocationRemove> m_BoneAllocationRemoves;
```

- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+IndexRemove> m_MetaBufferRemoves`  

```csharp
private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+IndexRemove> m_MetaBufferRemoves;
```

- `private UnityEngine.ComputeBuffer m_BoneBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_BoneBuffer;
```

- `private UnityEngine.ComputeBuffer m_BoneHistoryBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_BoneHistoryBuffer;
```

- `private UnityEngine.ComputeBuffer m_LocalTRSBlendPoseBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_LocalTRSBlendPoseBuffer;
```

- `private UnityEngine.ComputeBuffer m_LocalTRSBoneBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_LocalTRSBoneBuffer;
```

- `private UnityEngine.ComputeBuffer m_AnimInfoBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_AnimInfoBuffer;
```

- `private UnityEngine.ComputeBuffer m_AnimBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_AnimBuffer;
```

- `private UnityEngine.ComputeBuffer m_MetaBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_MetaBuffer;
```

- `private UnityEngine.ComputeBuffer m_IndexBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_IndexBuffer;
```

- `private UnityEngine.ComputeBuffer m_InstanceBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_InstanceBuffer;
```

- `private UnityEngine.ComputeBuffer m_BodyInstanceBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_BodyInstanceBuffer;
```

- `private UnityEngine.ComputeBuffer m_FaceInstanceBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_FaceInstanceBuffer;
```

- `private UnityEngine.ComputeBuffer m_CorrectiveInstanceBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_CorrectiveInstanceBuffer;
```

- `private UnityEngine.ComputeBuffer m_BodyTransitionBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_BodyTransitionBuffer;
```

- `private UnityEngine.ComputeBuffer m_BodyTransition2Buffer`  

```csharp
private UnityEngine.ComputeBuffer m_BodyTransition2Buffer;
```

- `private UnityEngine.ComputeBuffer m_FaceTransitionBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_FaceTransitionBuffer;
```

- `private System.Int32 m_AnimationCount`  

```csharp
private System.Int32 m_AnimationCount;
```

- `private System.Int32 m_MaxBoneCount`  

```csharp
private System.Int32 m_MaxBoneCount;
```

- `private System.Int32 m_MaxActiveBoneCount`  

```csharp
private System.Int32 m_MaxActiveBoneCount;
```

- `private System.Int32 m_CurrentTime`  

```csharp
private System.Int32 m_CurrentTime;
```

- `private System.Boolean m_IsAllocating`  

```csharp
private System.Boolean m_IsAllocating;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_PropIDs`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Int32> m_PropIDs;
```

- `private UnityEngine.ComputeShader m_AnimationComputeShader`  

```csharp
private UnityEngine.ComputeShader m_AnimationComputeShader;
```

- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> m_TempAnimationQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> m_TempAnimationQueue;
```

- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> m_TempPriorityQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> m_TempPriorityQueue;
```

- `private Unity.Jobs.JobHandle m_AllocateDeps`  

```csharp
private Unity.Jobs.JobHandle m_AllocateDeps;
```

- `private System.Int32 m_BlendAnimationLayer0KernelIx`  

```csharp
private System.Int32 m_BlendAnimationLayer0KernelIx;
```

- `private System.Int32 m_BlendAnimationLayer1KernelIx`  

```csharp
private System.Int32 m_BlendAnimationLayer1KernelIx;
```

- `private System.Int32 m_BlendAnimationLayer2KernelIx`  

```csharp
private System.Int32 m_BlendAnimationLayer2KernelIx;
```

- `private System.Int32 m_BlendTransitionLayer0KernelIx`  

```csharp
private System.Int32 m_BlendTransitionLayer0KernelIx;
```

- `private System.Int32 m_BlendTransition2Layer0KernelIx`  

```csharp
private System.Int32 m_BlendTransition2Layer0KernelIx;
```

- `private System.Int32 m_BlendTransitionLayer1KernelIx`  

```csharp
private System.Int32 m_BlendTransitionLayer1KernelIx;
```

- `private System.Int32 m_BlendRestPoseKernelIx`  

```csharp
private System.Int32 m_BlendRestPoseKernelIx;
```

- `private System.Int32 m_ConvertLocalCoordinatesKernelIx`  

```csharp
private System.Int32 m_ConvertLocalCoordinatesKernelIx;
```

- `private System.Int32 m_ConvertLocalCoordinatesWithHistoryKernelIx`  

```csharp
private System.Int32 m_ConvertLocalCoordinatesWithHistoryKernelIx;
```

- `private System.Int32 m_IndexBufferID`  

```csharp
private System.Int32 m_IndexBufferID;
```

- `private System.Int32 m_MetadataBufferID`  

```csharp
private System.Int32 m_MetadataBufferID;
```

- `private System.Int32 m_MetaIndexBufferID`  

```csharp
private System.Int32 m_MetaIndexBufferID;
```

- `private System.Int32 m_AnimatedInstanceBufferID`  

```csharp
private System.Int32 m_AnimatedInstanceBufferID;
```

- `private System.Int32 m_AnimatedTransitionBufferID`  

```csharp
private System.Int32 m_AnimatedTransitionBufferID;
```

- `private System.Int32 m_AnimatedTransition2BufferID`  

```csharp
private System.Int32 m_AnimatedTransition2BufferID;
```

- `private System.Int32 m_AnimationInfoBufferID`  

```csharp
private System.Int32 m_AnimationInfoBufferID;
```

- `private System.Int32 m_AnimationBoneBufferID`  

```csharp
private System.Int32 m_AnimationBoneBufferID;
```

- `private System.Int32 m_InstanceCountID`  

```csharp
private System.Int32 m_InstanceCountID;
```

- `private System.Int32 m_BodyInstanceCountID`  

```csharp
private System.Int32 m_BodyInstanceCountID;
```

- `private System.Int32 m_BodyTransitionCountID`  

```csharp
private System.Int32 m_BodyTransitionCountID;
```

- `private System.Int32 m_BodyTransition2CountID`  

```csharp
private System.Int32 m_BodyTransition2CountID;
```

- `private System.Int32 m_FaceInstanceCountID`  

```csharp
private System.Int32 m_FaceInstanceCountID;
```

- `private System.Int32 m_FaceTransitionCountID`  

```csharp
private System.Int32 m_FaceTransitionCountID;
```

- `private System.Int32 m_CorrectiveInstanceCountID`  

```csharp
private System.Int32 m_CorrectiveInstanceCountID;
```

- `private System.Int32 m_LocalTRSBlendPoseBufferID`  

```csharp
private System.Int32 m_LocalTRSBlendPoseBufferID;
```

- `private System.Int32 m_LocalTRSBoneBufferID`  

```csharp
private System.Int32 m_LocalTRSBoneBufferID;
```

- `private System.Int32 m_BoneBufferID`  

```csharp
private System.Int32 m_BoneBufferID;
```

- `private System.Int32 m_BoneHistoryBufferID`  

```csharp
private System.Int32 m_BoneHistoryBufferID;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `public static const System.UInt32 BONEBUFFER_MEMORY_DEFAULT`  

```csharp
public static const System.UInt32 BONEBUFFER_MEMORY_DEFAULT;
```

- `public static const System.UInt32 BONEBUFFER_MEMORY_INCREMENT`  

```csharp
public static const System.UInt32 BONEBUFFER_MEMORY_INCREMENT;
```

- `public static const System.UInt32 ANIMBUFFER_MEMORY_DEFAULT`  

```csharp
public static const System.UInt32 ANIMBUFFER_MEMORY_DEFAULT;
```

- `public static const System.UInt32 ANIMBUFFER_MEMORY_INCREMENT`  

```csharp
public static const System.UInt32 ANIMBUFFER_MEMORY_INCREMENT;
```

- `public static const System.UInt32 METABUFFER_MEMORY_DEFAULT`  

```csharp
public static const System.UInt32 METABUFFER_MEMORY_DEFAULT;
```

- `public static const System.UInt32 METABUFFER_MEMORY_INCREMENT`  

```csharp
public static const System.UInt32 METABUFFER_MEMORY_INCREMENT;
```

- `public static const System.UInt32 INDEXBUFFER_MEMORY_DEFAULT`  

```csharp
public static const System.UInt32 INDEXBUFFER_MEMORY_DEFAULT;
```

- `public static const System.UInt32 INDEXBUFFER_MEMORY_INCREMENT`  

```csharp
public static const System.UInt32 INDEXBUFFER_MEMORY_INCREMENT;
```

- `public static const System.UInt32 MAX_ASYNC_LOADING_COUNT`  

```csharp
public static const System.UInt32 MAX_ASYNC_LOADING_COUNT;
```

- `private static const System.String ANIMATION_COMPUTE_SHADER_RESOURCE`  

```csharp
private static const System.String ANIMATION_COMPUTE_SHADER_RESOURCE;
```

- `private static const System.String SHADER_BLEND_ANIMATION_LAYER0_KERNEL_NAME`  

```csharp
private static const System.String SHADER_BLEND_ANIMATION_LAYER0_KERNEL_NAME;
```

- `private static const System.String SHADER_BLEND_ANIMATION_LAYER1_KERNEL_NAME`  

```csharp
private static const System.String SHADER_BLEND_ANIMATION_LAYER1_KERNEL_NAME;
```

- `private static const System.String SHADER_BLEND_ANIMATION_LAYER2_KERNEL_NAME`  

```csharp
private static const System.String SHADER_BLEND_ANIMATION_LAYER2_KERNEL_NAME;
```

- `private static const System.String SHADER_BLEND_TRANSITION_LAYER0_KERNEL_NAME`  

```csharp
private static const System.String SHADER_BLEND_TRANSITION_LAYER0_KERNEL_NAME;
```

- `private static const System.String SHADER_BLEND_TRANSITION2_LAYER0_KERNEL_NAME`  

```csharp
private static const System.String SHADER_BLEND_TRANSITION2_LAYER0_KERNEL_NAME;
```

- `private static const System.String SHADER_BLEND_TRANSITION_LAYER1_KERNEL_NAME`  

```csharp
private static const System.String SHADER_BLEND_TRANSITION_LAYER1_KERNEL_NAME;
```

- `private static const System.String SHADER_BLEND_REST_POSE_KERNEL_NAME`  

```csharp
private static const System.String SHADER_BLEND_REST_POSE_KERNEL_NAME;
```

- `private static const System.String SHADER_CONVERT_COORDINATES_KERNEL_NAME`  

```csharp
private static const System.String SHADER_CONVERT_COORDINATES_KERNEL_NAME;
```

- `private static const System.String SHADER_CONVERT_COORDINATES_WITH_HISTORY_KERNEL_NAME`  

```csharp
private static const System.String SHADER_CONVERT_COORDINATES_WITH_HISTORY_KERNEL_NAME;
```


## Constructors

- `public AnimatedSystem()`  

```csharp
public AnimatedSystem();
```


## Methods

- `public AddAllocationWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddAllocationWriter(Unity.Jobs.JobHandle handle);
```

- `public AddAnimationWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddAnimationWriter(Unity.Jobs.JobHandle handle);
```

- `private AllocateIndexData(System.UInt32 size) : Colossal.Collections.NativeHeapBlock`  

```csharp
private Colossal.Collections.NativeHeapBlock AllocateIndexData(System.UInt32 size);
```

- `private CacheRestPose(Unity.Entities.Entity style, Colossal.Animations.AnimationClip restPose) : System.Void`  

```csharp
private System.Void CacheRestPose(Unity.Entities.Entity style, Colossal.Animations.AnimationClip restPose);
```

- `private FindTargetRotation(Colossal.Animations.AnimationClip animation, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements) : System.Single`  

```csharp
private System.Single FindTargetRotation(Colossal.Animations.AnimationClip animation, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements);
```

- `private FindTargetValue(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements) : System.Single`  

```csharp
private System.Single FindTargetValue(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements);
```

- `public GetAllocationData(Unity.Jobs.JobHandle& dependencies) : Game.Rendering.AnimatedSystem+AllocationData`  

```csharp
public Game.Rendering.AnimatedSystem+AllocationData GetAllocationData(Unity.Jobs.JobHandle& dependencies);
```

- `public GetAnimationData(Unity.Jobs.JobHandle& dependencies) : Game.Rendering.AnimatedSystem+AnimationData`  

```csharp
public Game.Rendering.AnimatedSystem+AnimationData GetAnimationData(Unity.Jobs.JobHandle& dependencies);
```

- `public GetAnimStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public System.Void GetAnimStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
```

- `public GetBoneStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public System.Void GetBoneStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
```

- `public GetIndexStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public System.Void GetIndexStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
```

- `public GetMetaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public System.Void GetMetaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
```

- `public GetPropID(System.String name) : Game.Rendering.AnimatedPropID`  

```csharp
public Game.Rendering.AnimatedPropID GetPropID(System.String name);
```

- `private LoadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex, Colossal.Animations.AnimationClip animation) : System.Boolean`  

```csharp
private System.Boolean LoadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex, Colossal.Animations.AnimationClip animation);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private PlayAnimations() : System.Void`  

```csharp
private System.Void PlayAnimations();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private RemoveRootMotion(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Entities.DynamicBuffer<Game.Prefabs.RestPoseElement> restPose, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> motions, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements) : System.Void`  

```csharp
private System.Void RemoveRootMotion(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Entities.DynamicBuffer<Game.Prefabs.RestPoseElement> restPose, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> motions, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements);
```

- `private ResizeAnimBuffer() : System.Void`  

```csharp
private System.Void ResizeAnimBuffer();
```

- `private ResizeAnimInfoBuffer() : System.Void`  

```csharp
private System.Void ResizeAnimInfoBuffer();
```

- `private ResizeBoneBuffer() : System.Void`  

```csharp
private System.Void ResizeBoneBuffer();
```

- `private ResizeBoneHistoryBuffer() : System.Void`  

```csharp
private System.Void ResizeBoneHistoryBuffer();
```

- `private ResizeIndexBuffer() : System.Void`  

```csharp
private System.Void ResizeIndexBuffer();
```

- `private ResizeMetaBuffer() : System.Void`  

```csharp
private System.Void ResizeMetaBuffer();
```

- `private UnCacheRestPose(Unity.Entities.Entity style) : System.Void`  

```csharp
private System.Void UnCacheRestPose(Unity.Entities.Entity style);
```

- `private UnloadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex) : System.Void`  

```csharp
private System.Void UnloadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex);
```

- `private UpdateAnimations() : System.Void`  

```csharp
private System.Void UpdateAnimations();
```

- `private UpdateInstanceBuffer<T>(UnityEngine.ComputeBuffer& buffer, Unity.Collections.NativeList<T> data, System.String name) : System.Void`  

```csharp
private System.Void UpdateInstanceBuffer<T>(UnityEngine.ComputeBuffer& buffer, Unity.Collections.NativeList<T> data, System.String name);
```

- `private UpdateInstances() : System.Void`  

```csharp
private System.Void UpdateInstances();
```

- `private UpdateMetaData() : System.Void`  

```csharp
private System.Void UpdateMetaData();
```


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

