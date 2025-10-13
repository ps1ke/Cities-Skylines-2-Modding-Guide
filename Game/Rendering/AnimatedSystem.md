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
[Preserve]
	public AnimatedSystem()
	{
	}
```


## Methods

- `public AddAllocationWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddAllocationWriter(JobHandle handle)
	{
		m_AllocateDeps = handle;
	}
```

- `public AddAnimationWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddAnimationWriter(JobHandle handle)
	{
		m_AllocateDeps = handle;
	}
```

- `private AllocateIndexData(System.UInt32 size) : Colossal.Collections.NativeHeapBlock`  

```csharp
private NativeHeapBlock AllocateIndexData(uint size)
	{
		NativeHeapBlock result = m_IndexAllocator.Allocate(size);
		while (result.Empty)
		{
			uint num = 4096u;
			num = (num + size - 1) / num * num;
			m_IndexAllocator.Resize(m_IndexAllocator.Size + num);
			result = m_IndexAllocator.Allocate(size);
		}
		return result;
	}
```

- `private CacheRestPose(Unity.Entities.Entity style, Colossal.Animations.AnimationClip restPose) : System.Void`  

```csharp
private void CacheRestPose(Entity style, Colossal.Animations.AnimationClip restPose)
	{
		DynamicBuffer<RestPoseElement> buffer = base.EntityManager.GetBuffer<RestPoseElement>(style);
		buffer.ResizeUninitialized(restPose.m_Animation.elements.Length);
		for (int i = 0; i < buffer.Length; i++)
		{
			Colossal.Animations.Animation.ElementRaw elementRaw = AnimationEncoding.DecodeElement(restPose.m_Animation.elements[i], restPose.m_Animation.positionMin, restPose.m_Animation.positionRange);
			buffer[i] = new RestPoseElement
			{
				m_Position = elementRaw.position,
				m_Rotation = elementRaw.rotation
			};
		}
	}
```

- `private FindTargetRotation(Colossal.Animations.AnimationClip animation, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements) : System.Single`  

```csharp
private float FindTargetRotation(Colossal.Animations.AnimationClip animation, NativeArray<Colossal.Animations.Animation.Element> elements)
	{
		int num = animation.m_Animation.shapeIndices.Length;
		int num2 = animation.m_Animation.boneIndices.Length;
		float num3 = 0f;
		for (int i = 0; i < num2; i++)
		{
			Colossal.Animations.Animation.ElementRaw elementRaw = AnimationEncoding.DecodeElement(elements.ElementAt(i * num), animation.m_Animation.positionMin, animation.m_Animation.positionRange);
			float y = MathUtils.RotationAngle(quaternion.identity, elementRaw.rotation);
			num3 = math.max(num3, y);
		}
		return num3;
	}
```

- `private FindTargetValue(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements) : System.Single`  

```csharp
private float FindTargetValue(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, NativeArray<Colossal.Animations.Animation.Element> elements)
	{
		if (animationClip.m_Activity == ActivityType.Driving)
		{
			Game.Prefabs.AnimationType type = animationClip.m_Type;
			if ((uint)(type - 6) <= 3u)
			{
				return FindTargetRotation(animation, elements);
			}
		}
		return 0f;
	}
```

- `public GetAllocationData(Unity.Jobs.JobHandle& dependencies) : Game.Rendering.AnimatedSystem+AllocationData`  

```csharp
public AllocationData GetAllocationData(out JobHandle dependencies)
	{
		dependencies = m_AllocateDeps;
		m_IsAllocating = true;
		return new AllocationData(m_BoneAllocator, m_MetaBufferData, m_FreeMetaIndices, m_UpdatedMetaIndices, m_BoneAllocationRemoves, m_MetaBufferRemoves, m_CurrentTime);
	}
```

- `public GetAnimationData(Unity.Jobs.JobHandle& dependencies) : Game.Rendering.AnimatedSystem+AnimationData`  

```csharp
public AnimationData GetAnimationData(out JobHandle dependencies)
	{
		dependencies = m_AllocateDeps;
		if (!m_TempAnimationQueue.IsCreated)
		{
			m_TempAnimationQueue = new NativeQueue<AnimationFrameData>(Allocator.TempJob);
		}
		if (!m_TempPriorityQueue.IsCreated)
		{
			m_TempPriorityQueue = new NativeQueue<ClipPriorityData>(Allocator.TempJob);
		}
		m_IsAllocating = true;
		return new AnimationData(m_TempAnimationQueue, m_TempPriorityQueue);
	}
```

- `public GetAnimStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public unsafe void GetAnimStats(out uint allocatedSize, out uint bufferSize, out uint count)
	{
		m_AllocateDeps.Complete();
		allocatedSize = m_AnimAllocator.UsedSpace * (uint)sizeof(Colossal.Animations.Animation.Element);
		bufferSize = m_AnimAllocator.Size * (uint)sizeof(Colossal.Animations.Animation.Element);
		count = (uint)m_AnimationCount;
	}
```

- `public GetBoneStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public unsafe void GetBoneStats(out uint allocatedSize, out uint bufferSize, out uint count)
	{
		m_AllocateDeps.Complete();
		allocatedSize = m_BoneAllocator.UsedSpace * (uint)sizeof(BoneElement);
		bufferSize = m_BoneAllocator.Size * (uint)sizeof(BoneElement);
		if (m_RenderingSystem.motionVectors)
		{
			allocatedSize <<= 1;
			bufferSize <<= 1;
		}
		count = (uint)(m_MetaBufferData.Length - m_FreeMetaIndices.Length - 1);
	}
```

- `public GetIndexStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public void GetIndexStats(out uint allocatedSize, out uint bufferSize, out uint count)
	{
		m_AllocateDeps.Complete();
		allocatedSize = m_IndexAllocator.UsedSpace * 4;
		bufferSize = m_IndexAllocator.Size * 4;
		count = (uint)m_AnimationCount;
	}
```

- `public GetMetaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public unsafe void GetMetaStats(out uint allocatedSize, out uint bufferSize, out uint count)
	{
		m_AllocateDeps.Complete();
		count = (uint)(m_MetaBufferData.Length - m_FreeMetaIndices.Length - 1);
		if (m_MetaBuffer != null)
		{
			allocatedSize = (count + 1) * (uint)sizeof(MetaBufferData);
			bufferSize = (uint)(m_MetaBuffer.count * sizeof(MetaBufferData));
		}
		else
		{
			allocatedSize = 0u;
			bufferSize = 0u;
		}
	}
```

- `public GetPropID(System.String name) : Game.Rendering.AnimatedPropID`  

```csharp
public AnimatedPropID GetPropID(string name)
	{
		int value = -1;
		if (!string.IsNullOrEmpty(name) && !m_PropIDs.TryGetValue(name, out value))
		{
			value = m_PropIDs.Count;
			m_PropIDs.Add(name, value);
		}
		return new AnimatedPropID(value);
	}
```

- `private LoadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex, Colossal.Animations.AnimationClip animation) : System.Boolean`  

```csharp
private unsafe bool LoadAnimation(ClipIndex clipIndex, Colossal.Animations.AnimationClip animation)
	{
		CharacterStyleData componentData = base.EntityManager.GetComponentData<CharacterStyleData>(clipIndex.m_Style);
		DynamicBuffer<Game.Prefabs.AnimationClip> buffer = base.EntityManager.GetBuffer<Game.Prefabs.AnimationClip>(clipIndex.m_Style);
		DynamicBuffer<AnimationMotion> buffer2 = base.EntityManager.GetBuffer<AnimationMotion>(clipIndex.m_Style, isReadOnly: true);
		ref Game.Prefabs.AnimationClip reference = ref buffer.ElementAt(clipIndex.m_Index);
		DynamicBuffer<RestPoseElement> buffer3 = default(DynamicBuffer<RestPoseElement>);
		if (reference.m_RootMotionBone != -1 && (!base.EntityManager.TryGetBuffer(clipIndex.m_Style, isReadOnly: true, out buffer3) || buffer3.Length == 0))
		{
			return false;
		}
		uint num = (uint)animation.m_Animation.elements.Length;
		AnimationClipData value = new AnimationClipData
		{
			m_AnimAllocation = m_AnimAllocator.Allocate(num)
		};
		m_AnimationCount++;
		int num2 = m_ClipPriorities.Length - 1;
		while (value.m_AnimAllocation.Empty)
		{
			if (num2 >= 0)
			{
				ref ClipPriorityData reference2 = ref m_ClipPriorities.ElementAt(num2--);
				if (reference2.m_Priority >= 0)
				{
					num2 = -1;
					continue;
				}
				if (reference2.m_ClipIndex.Equals(clipIndex) || reference2.m_IsLoading || !reference2.m_IsLoaded)
				{
					continue;
				}
				reference2.m_IsLoaded = false;
				UnloadAnimation(reference2.m_ClipIndex);
			}
			else
			{
				uint num3 = 8388608u / (uint)sizeof(Colossal.Animations.Animation.Element);
				num3 = (num3 + num - 1) / num3 * num3;
				m_AnimAllocator.Resize(m_AnimAllocator.Size + num3);
			}
			value.m_AnimAllocation = m_AnimAllocator.Allocate(num);
		}
		if (componentData.m_RestPoseClipIndex == clipIndex.m_Index)
		{
			value.m_HierarchyAllocation = AllocateIndexData((uint)animation.m_BoneHierarchy.hierarchyParentIndices.Length);
			CacheRestPose(clipIndex.m_Style, animation);
		}
		value.m_ShapeAllocation = AllocateIndexData((uint)componentData.m_ShapeCount);
		value.m_BoneAllocation = AllocateIndexData((uint)animation.m_Animation.boneIndices.Length);
		value.m_InverseBoneAllocation = AllocateIndexData((uint)componentData.m_BoneCount);
		m_MaxBoneCount = math.max(m_MaxBoneCount, animation.m_BoneHierarchy.hierarchyParentIndices.Length);
		m_MaxActiveBoneCount = math.max(m_MaxActiveBoneCount, animation.m_Animation.boneIndices.Length);
		if (m_FreeAnimIndices.IsEmpty)
		{
			reference.m_InfoIndex = m_AnimationClipData.Length;
			m_AnimationClipData.Add(in value);
		}
		else
		{
			reference.m_InfoIndex = m_FreeAnimIndices[m_FreeAnimIndices.Length - 1];
			m_FreeAnimIndices.RemoveAt(m_FreeAnimIndices.Length - 1);
			m_AnimationClipData[reference.m_InfoIndex] = value;
		}
		ResizeAnimInfoBuffer();
		ResizeAnimBuffer();
		ResizeIndexBuffer();
		NativeArray<AnimationInfoData> data = new NativeArray<AnimationInfoData>(1, Allocator.Temp) { [0] = new AnimationInfoData
		{
			m_Offset = (int)value.m_AnimAllocation.Begin,
			m_Hierarchy = (value.m_HierarchyAllocation.Empty ? (-1) : ((int)value.m_HierarchyAllocation.Begin)),
			m_Shapes = (int)value.m_ShapeAllocation.Begin,
			m_Bones = (int)value.m_BoneAllocation.Begin,
			m_InverseBones = (int)value.m_InverseBoneAllocation.Begin,
			m_ShapeCount = animation.m_Animation.shapeIndices.Length,
			m_BoneCount = animation.m_Animation.boneIndices.Length,
			m_Type = (int)animation.m_Animation.type,
			m_PositionMin = animation.m_Animation.positionMin,
			m_PositionRange = animation.m_Animation.positionRange
		} };
		m_AnimInfoBuffer.SetData(data, 0, reference.m_InfoIndex, 1);
		data.Dispose();
		NativeArray<Colossal.Animations.Animation.Element> nativeArray = new NativeArray<Colossal.Animations.Animation.Element>(animation.m_Animation.elements, Allocator.Temp);
		if (reference.m_RootMotionBone != -1)
		{
			NativeArray<AnimationMotion> subArray = buffer2.AsNativeArray().GetSubArray(reference.m_MotionRange.x, reference.m_MotionRange.y - reference.m_MotionRange.x);
			RemoveRootMotion(animation, reference, buffer3, subArray, nativeArray);
		}
		if (reference.m_Layer == Game.Prefabs.AnimationLayer.Prop && reference.m_TargetValue == float.MinValue)
		{
			reference.m_TargetValue = FindTargetValue(animation, reference, nativeArray);
			for (int i = 0; i < buffer.Length; i++)
			{
				if (i != clipIndex.m_Index)
				{
					ref Game.Prefabs.AnimationClip reference3 = ref buffer.ElementAt(i);
					if (reference3.m_PropClipIndex == clipIndex.m_Index)
					{
						reference3.m_TargetValue = reference.m_TargetValue;
					}
				}
			}
		}
		m_AnimBuffer.SetData(nativeArray, 0, (int)value.m_AnimAllocation.Begin, (int)num);
		nativeArray.Dispose();
		if (!value.m_HierarchyAllocation.Empty)
		{
			m_IndexBuffer.SetData(animation.m_BoneHierarchy.hierarchyParentIndices, 0, (int)value.m_HierarchyAllocation.Begin, animation.m_BoneHierarchy.hierarchyParentIndices.Length);
		}
		if (!value.m_ShapeAllocation.Empty)
		{
			NativeArray<int> data2 = new NativeArray<int>(componentData.m_ShapeCount, Allocator.Temp);
			for (int j = 0; j < data2.Length; j++)
			{
				data2[j] = -1;
			}
			for (int k = 0; k < animation.m_Animation.shapeIndices.Length; k++)
			{
				data2[animation.m_Animation.shapeIndices[k]] = k;
			}
			m_IndexBuffer.SetData(data2, 0, (int)value.m_ShapeAllocation.Begin, data2.Length);
			data2.Dispose();
		}
		if (!value.m_BoneAllocation.Empty)
		{
			m_IndexBuffer.SetData(animation.m_Animation.boneIndices, 0, (int)value.m_BoneAllocation.Begin, animation.m_Animation.boneIndices.Length);
		}
		if (!value.m_InverseBoneAllocation.Empty && reference.m_Layer != Game.Prefabs.AnimationLayer.Prop)
		{
			NativeArray<int> data3 = new NativeArray<int>(componentData.m_BoneCount, Allocator.Temp);
			for (int l = 0; l < data3.Length; l++)
			{
				data3[l] = -1;
			}
			for (int m = 0; m < animation.m_Animation.boneIndices.Length; m++)
			{
				data3[animation.m_Animation.boneIndices[m]] = m;
			}
			m_IndexBuffer.SetData(data3, 0, (int)value.m_InverseBoneAllocation.Begin, data3.Length);
			data3.Dispose();
		}
		return true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected unsafe override void OnCreate()
	{
		log = LogManager.GetLogger("Rendering");
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_BoneAllocator = new NativeHeapAllocator(8388608u / (uint)sizeof(BoneElement), 1u, Allocator.Persistent);
		m_AnimAllocator = new NativeHeapAllocator(33554432u / (uint)sizeof(Colossal.Animations.Animation.Element), 1u, Allocator.Persistent);
		m_IndexAllocator = new NativeHeapAllocator(16384u, 1u, Allocator.Persistent);
		m_MetaBufferData = new NativeList<MetaBufferData>(1000, Allocator.Persistent);
		m_FreeMetaIndices = new NativeList<int>(10, Allocator.Persistent);
		m_UpdatedMetaIndices = new NativeList<int>(10, Allocator.Persistent);
		m_InstanceIndices = new NativeList<RestPoseInstance>(1000, Allocator.Persistent);
		m_BodyInstances = new NativeList<AnimatedInstance>(1000, Allocator.Persistent);
		m_FaceInstances = new NativeList<AnimatedInstance>(1000, Allocator.Persistent);
		m_CorrectiveInstances = new NativeList<AnimatedInstance>(100, Allocator.Persistent);
		m_BodyTransitions = new NativeList<AnimatedTransition>(100, Allocator.Persistent);
		m_BodyTransitions2 = new NativeList<AnimatedTransition2>(100, Allocator.Persistent);
		m_FaceTransitions = new NativeList<AnimatedTransition>(100, Allocator.Persistent);
		m_ClipPriorities = new NativeList<ClipPriorityData>(10, Allocator.Persistent);
		m_AnimationClipData = new NativeList<AnimationClipData>(10, Allocator.Persistent);
		m_FreeAnimIndices = new NativeList<int>(10, Allocator.Persistent);
		m_BoneAllocationRemoves = new NativeQueue<AllocationRemove>(Allocator.Persistent);
		m_MetaBufferRemoves = new NativeQueue<IndexRemove>(Allocator.Persistent);
		m_PropIDs = new Dictionary<string, int>();
		m_AnimationComputeShader = UnityEngine.Object.Instantiate(Resources.Load<ComputeShader>("Didimo/AnimationBlendCompute"));
		m_BlendAnimationLayer0KernelIx = m_AnimationComputeShader.FindKernel("BlendAnimationLayer0");
		m_BlendAnimationLayer1KernelIx = m_AnimationComputeShader.FindKernel("BlendAnimationLayer1");
		m_BlendAnimationLayer2KernelIx = m_AnimationComputeShader.FindKernel("BlendAnimationLayer2");
		m_BlendTransitionLayer0KernelIx = m_AnimationComputeShader.FindKernel("BlendTransitionLayer0");
		m_BlendTransition2Layer0KernelIx = m_AnimationComputeShader.FindKernel("BlendTransition2Layer0");
		m_BlendTransitionLayer1KernelIx = m_AnimationComputeShader.FindKernel("BlendTransitionLayer1");
		m_BlendRestPoseKernelIx = m_AnimationComputeShader.FindKernel("BlendRestPose");
		m_ConvertLocalCoordinatesKernelIx = m_AnimationComputeShader.FindKernel("ConvertLocalCoordinates");
		m_ConvertLocalCoordinatesWithHistoryKernelIx = m_AnimationComputeShader.FindKernel("ConvertLocalCoordinatesWithHistory");
		m_IndexBufferID = Shader.PropertyToID("IndexDataBuffer");
		m_MetadataBufferID = Shader.PropertyToID("MetaDataBuffer");
		m_MetaIndexBufferID = Shader.PropertyToID("MetaIndexBuffer");
		m_AnimatedInstanceBufferID = Shader.PropertyToID("AnimatedInstanceBuffer");
		m_AnimatedTransitionBufferID = Shader.PropertyToID("AnimatedTransitionBuffer");
		m_AnimatedTransition2BufferID = Shader.PropertyToID("AnimatedTransition2Buffer");
		m_AnimationInfoBufferID = Shader.PropertyToID("AnimationInfoBuffer");
		m_AnimationBoneBufferID = Shader.PropertyToID("AnimationBoneBuffer");
		m_InstanceCountID = Shader.PropertyToID("instanceCount");
		m_BodyInstanceCountID = Shader.PropertyToID("bodyInstanceCount");
		m_BodyTransitionCountID = Shader.PropertyToID("bodyTransitionCount");
		m_BodyTransition2CountID = Shader.PropertyToID("bodyTransition2Count");
		m_FaceInstanceCountID = Shader.PropertyToID("faceInstanceCount");
		m_FaceTransitionCountID = Shader.PropertyToID("faceTransitionCount");
		m_CorrectiveInstanceCountID = Shader.PropertyToID("correctiveInstanceCount");
		m_LocalTRSBlendPoseBufferID = Shader.PropertyToID("LocalTRSBlendPoseBuffer");
		m_LocalTRSBoneBufferID = Shader.PropertyToID("LocalTRSBoneBuffer");
		m_BoneBufferID = Shader.PropertyToID("BoneBuffer");
		m_BoneHistoryBufferID = Shader.PropertyToID("BoneHistoryBuffer");
		m_BoneAllocator.Allocate(1u);
		m_MetaBufferData.Add(default(MetaBufferData));
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		if (m_IsAllocating)
		{
			m_AllocateDeps.Complete();
			m_IsAllocating = false;
		}
		m_BoneAllocator.Dispose();
		m_AnimAllocator.Dispose();
		m_IndexAllocator.Dispose();
		m_MetaBufferData.Dispose();
		m_FreeMetaIndices.Dispose();
		m_UpdatedMetaIndices.Dispose();
		m_InstanceIndices.Dispose();
		m_BodyInstances.Dispose();
		m_FaceInstances.Dispose();
		m_CorrectiveInstances.Dispose();
		m_BodyTransitions.Dispose();
		m_BodyTransitions2.Dispose();
		m_FaceTransitions.Dispose();
		m_ClipPriorities.Dispose();
		m_AnimationClipData.Dispose();
		m_FreeAnimIndices.Dispose();
		m_BoneAllocationRemoves.Dispose();
		m_MetaBufferRemoves.Dispose();
		if (m_BoneBuffer != null)
		{
			m_BoneBuffer.Release();
		}
		if (m_BoneHistoryBuffer != null)
		{
			m_BoneHistoryBuffer.Release();
		}
		if (m_LocalTRSBlendPoseBuffer != null)
		{
			m_LocalTRSBlendPoseBuffer.Release();
		}
		if (m_LocalTRSBoneBuffer != null)
		{
			m_LocalTRSBoneBuffer.Release();
		}
		if (m_AnimInfoBuffer != null)
		{
			m_AnimInfoBuffer.Release();
		}
		if (m_AnimBuffer != null)
		{
			m_AnimBuffer.Release();
		}
		if (m_MetaBuffer != null)
		{
			m_MetaBuffer.Release();
		}
		if (m_IndexBuffer != null)
		{
			m_IndexBuffer.Release();
		}
		if (m_InstanceBuffer != null)
		{
			m_InstanceBuffer.Release();
		}
		if (m_BodyInstanceBuffer != null)
		{
			m_BodyInstanceBuffer.Release();
		}
		if (m_FaceInstanceBuffer != null)
		{
			m_FaceInstanceBuffer.Release();
		}
		if (m_CorrectiveInstanceBuffer != null)
		{
			m_CorrectiveInstanceBuffer.Release();
		}
		if (m_BodyTransitionBuffer != null)
		{
			m_BodyTransitionBuffer.Release();
		}
		if (m_BodyTransition2Buffer != null)
		{
			m_BodyTransition2Buffer.Release();
		}
		if (m_FaceTransitionBuffer != null)
		{
			m_FaceTransitionBuffer.Release();
		}
		UnityEngine.Object.DestroyImmediate(m_AnimationComputeShader);
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_IsAllocating)
		{
			m_AllocateDeps.Complete();
			m_IsAllocating = false;
			ResizeBoneBuffer();
			ResizeMetaBuffer();
			UpdateAnimations();
			UpdateMetaData();
			UpdateInstances();
		}
		PlayAnimations();
	}
```

- `private PlayAnimations() : System.Void`  

```csharp
private void PlayAnimations()
	{
		if (m_InstanceIndices.Length != 0 && m_MaxBoneCount != 0)
		{
			ResizeBoneHistoryBuffer();
			m_AnimationComputeShader.SetInt(m_InstanceCountID, m_InstanceIndices.Length);
			m_AnimationComputeShader.SetInt(m_BodyInstanceCountID, m_BodyInstances.Length);
			m_AnimationComputeShader.SetInt(m_BodyTransitionCountID, m_BodyTransitions.Length);
			m_AnimationComputeShader.SetInt(m_BodyTransition2CountID, m_BodyTransitions2.Length);
			m_AnimationComputeShader.SetInt(m_FaceInstanceCountID, m_FaceInstances.Length);
			m_AnimationComputeShader.SetInt(m_FaceTransitionCountID, m_FaceTransitions.Length);
			m_AnimationComputeShader.SetInt(m_CorrectiveInstanceCountID, m_CorrectiveInstances.Length);
			m_AnimationComputeShader.SetBuffer(m_BlendRestPoseKernelIx, m_MetadataBufferID, m_MetaBuffer);
			m_AnimationComputeShader.SetBuffer(m_BlendRestPoseKernelIx, m_MetaIndexBufferID, m_InstanceBuffer);
			m_AnimationComputeShader.SetBuffer(m_BlendRestPoseKernelIx, m_LocalTRSBoneBufferID, m_LocalTRSBoneBuffer);
			m_AnimationComputeShader.SetBuffer(m_BlendRestPoseKernelIx, m_LocalTRSBlendPoseBufferID, m_LocalTRSBlendPoseBuffer);
			m_AnimationComputeShader.SetBuffer(m_BlendRestPoseKernelIx, m_AnimationInfoBufferID, m_AnimInfoBuffer);
			m_AnimationComputeShader.SetBuffer(m_BlendRestPoseKernelIx, m_AnimationBoneBufferID, m_AnimBuffer);
			m_AnimationComputeShader.SetBuffer(m_BlendRestPoseKernelIx, m_IndexBufferID, m_IndexBuffer);
			if (m_BodyInstances.Length != 0)
			{
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer0KernelIx, m_AnimationInfoBufferID, m_AnimInfoBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer0KernelIx, m_AnimationBoneBufferID, m_AnimBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer0KernelIx, m_MetadataBufferID, m_MetaBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer0KernelIx, m_AnimatedInstanceBufferID, m_BodyInstanceBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer0KernelIx, m_LocalTRSBoneBufferID, m_LocalTRSBoneBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer0KernelIx, m_LocalTRSBlendPoseBufferID, m_LocalTRSBlendPoseBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer0KernelIx, m_IndexBufferID, m_IndexBuffer);
			}
			if (m_BodyTransitions.Length != 0)
			{
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer0KernelIx, m_AnimationInfoBufferID, m_AnimInfoBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer0KernelIx, m_AnimationBoneBufferID, m_AnimBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer0KernelIx, m_MetadataBufferID, m_MetaBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer0KernelIx, m_AnimatedTransitionBufferID, m_BodyTransitionBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer0KernelIx, m_LocalTRSBoneBufferID, m_LocalTRSBoneBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer0KernelIx, m_LocalTRSBlendPoseBufferID, m_LocalTRSBlendPoseBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer0KernelIx, m_IndexBufferID, m_IndexBuffer);
			}
			if (m_BodyTransitions2.Length != 0)
			{
				m_AnimationComputeShader.SetBuffer(m_BlendTransition2Layer0KernelIx, m_AnimationInfoBufferID, m_AnimInfoBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransition2Layer0KernelIx, m_AnimationBoneBufferID, m_AnimBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransition2Layer0KernelIx, m_MetadataBufferID, m_MetaBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransition2Layer0KernelIx, m_AnimatedTransition2BufferID, m_BodyTransition2Buffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransition2Layer0KernelIx, m_LocalTRSBoneBufferID, m_LocalTRSBoneBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransition2Layer0KernelIx, m_LocalTRSBlendPoseBufferID, m_LocalTRSBlendPoseBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransition2Layer0KernelIx, m_IndexBufferID, m_IndexBuffer);
			}
			if (m_FaceInstances.Length != 0)
			{
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer1KernelIx, m_AnimationInfoBufferID, m_AnimInfoBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer1KernelIx, m_AnimationBoneBufferID, m_AnimBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer1KernelIx, m_MetadataBufferID, m_MetaBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer1KernelIx, m_AnimatedInstanceBufferID, m_FaceInstanceBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer1KernelIx, m_LocalTRSBoneBufferID, m_LocalTRSBoneBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer1KernelIx, m_LocalTRSBlendPoseBufferID, m_LocalTRSBlendPoseBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer1KernelIx, m_IndexBufferID, m_IndexBuffer);
			}
			if (m_FaceTransitions.Length != 0)
			{
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer1KernelIx, m_AnimationInfoBufferID, m_AnimInfoBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer1KernelIx, m_AnimationBoneBufferID, m_AnimBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer1KernelIx, m_MetadataBufferID, m_MetaBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer1KernelIx, m_AnimatedTransitionBufferID, m_FaceTransitionBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer1KernelIx, m_LocalTRSBoneBufferID, m_LocalTRSBoneBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer1KernelIx, m_LocalTRSBlendPoseBufferID, m_LocalTRSBlendPoseBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendTransitionLayer1KernelIx, m_IndexBufferID, m_IndexBuffer);
			}
			if (m_CorrectiveInstances.Length != 0)
			{
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer2KernelIx, m_AnimationInfoBufferID, m_AnimInfoBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer2KernelIx, m_AnimationBoneBufferID, m_AnimBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer2KernelIx, m_MetadataBufferID, m_MetaBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer2KernelIx, m_AnimatedInstanceBufferID, m_CorrectiveInstanceBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer2KernelIx, m_LocalTRSBoneBufferID, m_LocalTRSBoneBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer2KernelIx, m_LocalTRSBlendPoseBufferID, m_LocalTRSBlendPoseBuffer);
				m_AnimationComputeShader.SetBuffer(m_BlendAnimationLayer2KernelIx, m_IndexBufferID, m_IndexBuffer);
			}
			int kernelIndex = (m_RenderingSystem.motionVectors ? m_ConvertLocalCoordinatesWithHistoryKernelIx : m_ConvertLocalCoordinatesKernelIx);
			m_AnimationComputeShader.SetBuffer(kernelIndex, m_MetadataBufferID, m_MetaBuffer);
			m_AnimationComputeShader.SetBuffer(kernelIndex, m_MetaIndexBufferID, m_InstanceBuffer);
			m_AnimationComputeShader.SetBuffer(kernelIndex, m_LocalTRSBoneBufferID, m_LocalTRSBoneBuffer);
			m_AnimationComputeShader.SetBuffer(kernelIndex, m_LocalTRSBlendPoseBufferID, m_LocalTRSBlendPoseBuffer);
			m_AnimationComputeShader.SetBuffer(kernelIndex, m_BoneBufferID, m_BoneBuffer);
			m_AnimationComputeShader.SetBuffer(kernelIndex, m_IndexBufferID, m_IndexBuffer);
			m_AnimationComputeShader.SetBuffer(kernelIndex, m_AnimationInfoBufferID, m_AnimInfoBuffer);
			if (m_RenderingSystem.motionVectors)
			{
				m_AnimationComputeShader.SetBuffer(kernelIndex, m_BoneHistoryBufferID, m_BoneHistoryBuffer);
			}
			else
			{
				m_AnimationComputeShader.SetBuffer(kernelIndex, m_BoneHistoryBufferID, m_BoneBuffer);
			}
			m_AnimationComputeShader.GetKernelThreadGroupSizes(m_BlendRestPoseKernelIx, out var x, out var y, out var _);
			int threadGroupsX = (m_InstanceIndices.Length + (int)x - 1) / (int)x;
			int threadGroupsY = (m_MaxBoneCount + (int)y - 1) / (int)y;
			int threadGroupsY2 = (m_MaxActiveBoneCount + (int)y - 1) / (int)y;
			m_AnimationComputeShader.Dispatch(m_BlendRestPoseKernelIx, threadGroupsX, threadGroupsY, 1);
			if (m_BodyInstances.Length != 0)
			{
				int threadGroupsX2 = (m_BodyInstances.Length + (int)x - 1) / (int)x;
				m_AnimationComputeShader.Dispatch(m_BlendAnimationLayer0KernelIx, threadGroupsX2, threadGroupsY2, 1);
			}
			if (m_BodyTransitions.Length != 0)
			{
				int threadGroupsX3 = (m_BodyTransitions.Length + (int)x - 1) / (int)x;
				m_AnimationComputeShader.Dispatch(m_BlendTransitionLayer0KernelIx, threadGroupsX3, threadGroupsY, 1);
			}
			if (m_BodyTransitions2.Length != 0)
			{
				int threadGroupsX4 = (m_BodyTransitions2.Length + (int)x - 1) / (int)x;
				m_AnimationComputeShader.Dispatch(m_BlendTransition2Layer0KernelIx, threadGroupsX4, threadGroupsY, 1);
			}
			if (m_FaceInstances.Length != 0)
			{
				int threadGroupsX5 = (m_FaceInstances.Length + (int)x - 1) / (int)x;
				m_AnimationComputeShader.Dispatch(m_BlendAnimationLayer1KernelIx, threadGroupsX5, threadGroupsY2, 1);
			}
			if (m_FaceTransitions.Length != 0)
			{
				int threadGroupsX6 = (m_FaceTransitions.Length + (int)x - 1) / (int)x;
				m_AnimationComputeShader.Dispatch(m_BlendTransitionLayer1KernelIx, threadGroupsX6, threadGroupsY, 1);
			}
			if (m_CorrectiveInstances.Length != 0)
			{
				int threadGroupsX7 = (m_CorrectiveInstances.Length + (int)x - 1) / (int)x;
				m_AnimationComputeShader.Dispatch(m_BlendAnimationLayer2KernelIx, threadGroupsX7, threadGroupsY2, 1);
			}
			m_AnimationComputeShader.Dispatch(kernelIndex, threadGroupsX, threadGroupsY, 1);
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		if (m_IsAllocating)
		{
			m_AllocateDeps.Complete();
			m_IsAllocating = false;
		}
		m_BoneAllocator.Clear();
		m_MetaBufferData.Clear();
		m_FreeMetaIndices.Clear();
		m_UpdatedMetaIndices.Clear();
		m_InstanceIndices.Clear();
		m_BodyInstances.Clear();
		m_FaceInstances.Clear();
		m_CorrectiveInstances.Clear();
		m_BodyTransitions.Clear();
		m_FaceTransitions.Clear();
		m_BoneAllocationRemoves.Clear();
		m_MetaBufferRemoves.Clear();
		m_BoneAllocator.Allocate(1u);
		m_MetaBufferData.Add(default(MetaBufferData));
	}
```

- `private RemoveRootMotion(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, Unity.Entities.DynamicBuffer<Game.Prefabs.RestPoseElement> restPose, Unity.Collections.NativeArray<Game.Prefabs.AnimationMotion> motions, Unity.Collections.NativeArray<Colossal.Animations.Animation+Element> elements) : System.Void`  

```csharp
private void RemoveRootMotion(Colossal.Animations.AnimationClip animation, Game.Prefabs.AnimationClip animationClip, DynamicBuffer<RestPoseElement> restPose, NativeArray<AnimationMotion> motions, NativeArray<Colossal.Animations.Animation.Element> elements)
	{
		int[] inverseBoneIndices = animation.GetInverseBoneIndices();
		int num = animation.m_Animation.shapeIndices.Length;
		int num2 = animation.m_Animation.boneIndices.Length;
		int num3 = num * num2;
		int num4 = elements.Length / num3 - 1;
		int num5 = inverseBoneIndices.Length;
		int num6 = restPose.Length / num5;
		for (int i = 0; i <= num4; i++)
		{
			float t = math.select((float)i / (float)(num4 - 1), 0f, i >= num4);
			for (int j = 0; j < num; j++)
			{
				int num7 = animation.m_Animation.shapeIndices[j];
				AnimationMotion animationMotion = motions[num7];
				int num8 = inverseBoneIndices[animationClip.m_RootMotionBone];
				if (num8 < 0)
				{
					continue;
				}
				int num9 = i * num3 + num8 * num;
				ref Colossal.Animations.Animation.Element reference = ref elements.ElementAt(num9 + j);
				Colossal.Animations.Animation.ElementRaw input = AnimationEncoding.DecodeElement(reference, animation.m_Animation.positionMin, animation.m_Animation.positionRange);
				quaternion quaternion = math.slerp(animationMotion.m_StartRotation, animationMotion.m_EndRotation, t);
				float3 @float = ((animationClip.m_Playback == AnimationPlayback.Once) ? MathUtils.Position(new Bezier4x3(animationMotion.m_StartOffset, animationMotion.m_StartOffset, animationMotion.m_EndOffset, animationMotion.m_EndOffset), t) : math.lerp(animationMotion.m_StartOffset, animationMotion.m_EndOffset, t));
				if (num7 != 0)
				{
					AnimationMotion animationMotion2 = motions[0];
					quaternion b = math.slerp(animationMotion2.m_StartRotation, animationMotion2.m_EndRotation, t);
					float3 float2 = ((animationClip.m_Playback == AnimationPlayback.Once) ? MathUtils.Position(new Bezier4x3(animationMotion2.m_StartOffset, animationMotion2.m_StartOffset, animationMotion2.m_EndOffset, animationMotion2.m_EndOffset), t) : math.lerp(animationMotion2.m_StartOffset, animationMotion2.m_EndOffset, t));
					@float += float2;
					quaternion = math.mul(quaternion, b);
				}
				for (int num10 = animation.m_BoneHierarchy.hierarchyParentIndices[animationClip.m_RootMotionBone]; num10 != -1; num10 = animation.m_BoneHierarchy.hierarchyParentIndices[num10])
				{
					num8 = inverseBoneIndices[num10];
					if (num8 >= 0)
					{
						num9 = i * num3 + num8 * num;
						ref Colossal.Animations.Animation.Element reference2 = ref elements.ElementAt(num9 + j);
						Colossal.Animations.Animation.ElementRaw input2 = AnimationEncoding.DecodeElement(reference2, animation.m_Animation.positionMin, animation.m_Animation.positionRange);
						input.position = input2.position + math.mul(input2.rotation, input.position);
						input.rotation = math.mul((quaternion)input2.rotation, (quaternion)input.rotation).value;
						reference = AnimationEncoding.EncodeElement(input, animation.m_Animation.positionMin, animation.m_Animation.positionRange);
						input2.position = float3.zero;
						input2.rotation = quaternion.identity.value;
						reference2 = AnimationEncoding.EncodeElement(input2, animation.m_Animation.positionMin, animation.m_Animation.positionRange);
					}
					else
					{
						int num11 = num10 * num6;
						RestPoseElement restPoseElement = restPose[num11 + num7];
						restPoseElement.m_Rotation = math.inverse(restPoseElement.m_Rotation);
						@float = math.mul(restPoseElement.m_Rotation, @float - restPoseElement.m_Position);
						quaternion = math.normalize(math.mul(restPoseElement.m_Rotation, quaternion));
					}
				}
				quaternion = math.inverse(quaternion);
				input.position = math.mul(quaternion, input.position - @float);
				input.rotation = math.normalize(math.mul(quaternion, input.rotation)).value;
				reference = AnimationEncoding.EncodeElement(input, animation.m_Animation.positionMin, animation.m_Animation.positionRange);
			}
		}
	}
```

- `private ResizeAnimBuffer() : System.Void`  

```csharp
private unsafe void ResizeAnimBuffer()
	{
		int num = ((m_AnimBuffer != null) ? m_AnimBuffer.count : 0);
		int size = (int)m_AnimAllocator.Size;
		if (num != size)
		{
			ComputeBuffer computeBuffer = new ComputeBuffer(size, sizeof(Colossal.Animations.Animation.Element), ComputeBufferType.Structured)
			{
				name = "Animation buffer"
			};
			int num2 = math.min(num, size);
			if (num2 > 0)
			{
				Colossal.Animations.Animation.Element[] data = new Colossal.Animations.Animation.Element[num2];
				m_AnimBuffer.GetData(data, 0, 0, num2);
				computeBuffer.SetData(data);
			}
			if (m_AnimBuffer != null)
			{
				m_AnimBuffer.Release();
			}
			m_AnimBuffer = computeBuffer;
		}
	}
```

- `private ResizeAnimInfoBuffer() : System.Void`  

```csharp
private unsafe void ResizeAnimInfoBuffer()
	{
		int num = ((m_AnimInfoBuffer != null) ? m_AnimInfoBuffer.count : 0);
		int capacity = m_AnimationClipData.Capacity;
		if (num != capacity)
		{
			ComputeBuffer computeBuffer = new ComputeBuffer(capacity, sizeof(AnimationInfoData), ComputeBufferType.Structured)
			{
				name = "Animation info buffer"
			};
			int num2 = math.min(num, capacity);
			if (num2 > 0)
			{
				AnimationInfoData[] data = new AnimationInfoData[num2];
				m_AnimInfoBuffer.GetData(data, 0, 0, num2);
				computeBuffer.SetData(data);
			}
			if (m_AnimInfoBuffer != null)
			{
				m_AnimInfoBuffer.Release();
			}
			m_AnimInfoBuffer = computeBuffer;
		}
	}
```

- `private ResizeBoneBuffer() : System.Void`  

```csharp
private unsafe void ResizeBoneBuffer()
	{
		int num = ((m_BoneBuffer != null) ? m_BoneBuffer.count : 0);
		int size = (int)m_BoneAllocator.Size;
		if (num != size)
		{
			ComputeBuffer computeBuffer = new ComputeBuffer(size, sizeof(BoneElement), ComputeBufferType.Structured)
			{
				name = "Bone buffer"
			};
			Shader.SetGlobalBuffer("boneBuffer", computeBuffer);
			if (m_BoneHistoryBuffer == null)
			{
				Shader.SetGlobalBuffer("boneHistoryBuffer", computeBuffer);
			}
			if (m_BoneBuffer != null)
			{
				m_BoneBuffer.Release();
			}
			if (m_LocalTRSBlendPoseBuffer != null)
			{
				m_LocalTRSBlendPoseBuffer.Release();
			}
			if (m_LocalTRSBoneBuffer != null)
			{
				m_LocalTRSBoneBuffer.Release();
			}
			BoneElement[] array = new BoneElement[computeBuffer.count];
			for (int i = 0; i < array.Length; i++)
			{
				array[i] = new BoneElement
				{
					m_Matrix = float4x4.identity
				};
			}
			computeBuffer.SetData(array);
			m_BoneBuffer = computeBuffer;
			m_LocalTRSBlendPoseBuffer = new ComputeBuffer(size, sizeof(BoneElement), ComputeBufferType.Structured);
			m_LocalTRSBoneBuffer = new ComputeBuffer(size, sizeof(BoneElement), ComputeBufferType.Structured);
			m_LocalTRSBlendPoseBuffer.name = "LocalTRSBlendPoseBuffer";
			m_LocalTRSBoneBuffer.name = "LocalTRSBoneBuffer";
		}
	}
```

- `private ResizeBoneHistoryBuffer() : System.Void`  

```csharp
private unsafe void ResizeBoneHistoryBuffer()
	{
		int num = ((m_BoneHistoryBuffer != null) ? m_BoneHistoryBuffer.count : 0);
		int num2 = (int)(m_RenderingSystem.motionVectors ? m_BoneAllocator.Size : 0);
		if (num == num2)
		{
			return;
		}
		if (num2 == 0)
		{
			if (m_BoneHistoryBuffer != null)
			{
				if (m_BoneHistoryBuffer != null)
				{
					m_BoneHistoryBuffer.Release();
				}
				m_BoneHistoryBuffer = null;
			}
			if (m_BoneBuffer != null)
			{
				Shader.SetGlobalBuffer("boneHistoryBuffer", m_BoneBuffer);
			}
			return;
		}
		ComputeBuffer computeBuffer = new ComputeBuffer(num2, sizeof(BoneElement), ComputeBufferType.Structured)
		{
			name = "Bone history buffer"
		};
		Shader.SetGlobalBuffer("boneHistoryBuffer", computeBuffer);
		if (m_BoneHistoryBuffer != null)
		{
			m_BoneHistoryBuffer.Release();
		}
		BoneElement[] array = new BoneElement[computeBuffer.count];
		for (int i = 0; i < array.Length; i++)
		{
			array[i] = new BoneElement
			{
				m_Matrix = float4x4.identity
			};
		}
		computeBuffer.SetData(array);
		m_BoneHistoryBuffer = computeBuffer;
	}
```

- `private ResizeIndexBuffer() : System.Void`  

```csharp
private void ResizeIndexBuffer()
	{
		int num = ((m_IndexBuffer != null) ? m_IndexBuffer.count : 0);
		int size = (int)m_IndexAllocator.Size;
		if (num != size)
		{
			ComputeBuffer computeBuffer = new ComputeBuffer(size, 4, ComputeBufferType.Structured)
			{
				name = "Index buffer"
			};
			int num2 = math.min(num, size);
			if (num2 > 0)
			{
				int[] data = new int[num2];
				m_IndexBuffer.GetData(data, 0, 0, num2);
				computeBuffer.SetData(data);
			}
			if (m_IndexBuffer != null)
			{
				m_IndexBuffer.Release();
			}
			m_IndexBuffer = computeBuffer;
		}
	}
```

- `private ResizeMetaBuffer() : System.Void`  

```csharp
private unsafe void ResizeMetaBuffer()
	{
		int num = ((m_MetaBuffer != null) ? m_MetaBuffer.count : 0);
		int num2 = 1048576 / sizeof(MetaBufferData);
		if (m_MetaBufferData.Length > num && m_MetaBufferData.Length > num2)
		{
			num2 += ((m_MetaBufferData.Length - num2) * sizeof(MetaBufferData) + 262144 - 1) / 262144 * 262144 / sizeof(MetaBufferData);
		}
		else if (num > num2)
		{
			num2 = num;
		}
		if (num != num2)
		{
			ComputeBuffer computeBuffer = new ComputeBuffer(num2, sizeof(MetaBufferData), ComputeBufferType.Structured)
			{
				name = "Meta buffer"
			};
			Shader.SetGlobalBuffer("metaBuffer", computeBuffer);
			if (m_MetaBuffer != null)
			{
				computeBuffer.SetData(m_MetaBufferData.AsArray(), 0, 0, num);
				m_MetaBuffer.Release();
			}
			else
			{
				computeBuffer.SetData(m_MetaBufferData.AsArray(), 0, 0, 1);
			}
			m_MetaBuffer = computeBuffer;
		}
	}
```

- `private UnCacheRestPose(Unity.Entities.Entity style) : System.Void`  

```csharp
private void UnCacheRestPose(Entity style)
	{
		DynamicBuffer<RestPoseElement> buffer = base.EntityManager.GetBuffer<RestPoseElement>(style);
		buffer.Clear();
		buffer.TrimExcess();
	}
```

- `private UnloadAnimation(Game.Rendering.AnimatedSystem+ClipIndex clipIndex) : System.Void`  

```csharp
private void UnloadAnimation(ClipIndex clipIndex)
	{
		CharacterStyleData componentData = base.EntityManager.GetComponentData<CharacterStyleData>(clipIndex.m_Style);
		ref Game.Prefabs.AnimationClip reference = ref base.EntityManager.GetBuffer<Game.Prefabs.AnimationClip>(clipIndex.m_Style).ElementAt(clipIndex.m_Index);
		if (reference.m_InfoIndex >= 0)
		{
			AnimationClipData animationClipData = m_AnimationClipData[reference.m_InfoIndex];
			if (componentData.m_RestPoseClipIndex == clipIndex.m_Index)
			{
				UnCacheRestPose(clipIndex.m_Style);
			}
			if (!animationClipData.m_AnimAllocation.Empty)
			{
				m_AnimAllocator.Release(animationClipData.m_AnimAllocation);
			}
			if (!animationClipData.m_HierarchyAllocation.Empty)
			{
				m_IndexAllocator.Release(animationClipData.m_HierarchyAllocation);
			}
			if (!animationClipData.m_ShapeAllocation.Empty)
			{
				m_IndexAllocator.Release(animationClipData.m_ShapeAllocation);
			}
			if (!animationClipData.m_BoneAllocation.Empty)
			{
				m_IndexAllocator.Release(animationClipData.m_BoneAllocation);
			}
			if (!animationClipData.m_InverseBoneAllocation.Empty)
			{
				m_IndexAllocator.Release(animationClipData.m_InverseBoneAllocation);
			}
			if (reference.m_InfoIndex == m_AnimationClipData.Length - 1)
			{
				m_AnimationClipData.RemoveAt(reference.m_InfoIndex);
			}
			else
			{
				m_FreeAnimIndices.Add(in reference.m_InfoIndex);
			}
			reference.m_InfoIndex = -1;
			m_AnimationCount--;
		}
	}
```

- `private UpdateAnimations() : System.Void`  

```csharp
private void UpdateAnimations()
	{
		int num = 0;
		for (int i = 0; i < m_ClipPriorities.Length; i++)
		{
			ref ClipPriorityData reference = ref m_ClipPriorities.ElementAt(i);
			if (reference.m_Priority < 0 && !reference.m_IsLoading)
			{
				break;
			}
			if (reference.m_IsLoaded)
			{
				continue;
			}
			CharacterStyle prefab = m_PrefabSystem.GetPrefab<CharacterStyle>(reference.m_ClipIndex.m_Style);
			AnimationAsset animation = prefab.GetAnimation(reference.m_ClipIndex.m_Index);
			try
			{
				reference.m_IsLoading = true;
				if (animation.AsyncLoad(out var clip))
				{
					if (LoadAnimation(reference.m_ClipIndex, clip))
					{
						reference.m_IsLoading = false;
						reference.m_IsLoaded = true;
						animation.Unload();
					}
					else if (reference.m_Priority < 0)
					{
						reference.m_IsLoading = false;
						animation.Unload();
					}
				}
				else if ((long)(++num) == 10)
				{
					break;
				}
			}
			catch (Exception exception)
			{
				log.ErrorFormat(exception, "Error when loading animation: {0}->{1}", prefab.name, animation.name);
				reference.m_IsLoading = false;
				reference.m_IsLoaded = true;
				animation.Unload();
			}
		}
	}
```

- `private UpdateInstanceBuffer<T>(UnityEngine.ComputeBuffer& buffer, Unity.Collections.NativeList<T> data, System.String name) : System.Void`  

```csharp
private System.Void UpdateInstanceBuffer<T>(UnityEngine.ComputeBuffer& buffer, Unity.Collections.NativeList<T> data, System.String name);
```

- `private UpdateInstances() : System.Void`  

```csharp
private void UpdateInstances()
	{
		UpdateInstanceBuffer(ref m_InstanceBuffer, m_InstanceIndices, "InstanceBuffer");
		UpdateInstanceBuffer(ref m_BodyInstanceBuffer, m_BodyInstances, "BodyInstanceBuffer");
		UpdateInstanceBuffer(ref m_FaceInstanceBuffer, m_FaceInstances, "FaceInstanceBuffer");
		UpdateInstanceBuffer(ref m_CorrectiveInstanceBuffer, m_CorrectiveInstances, "CorrectiveInstanceBuffer");
		UpdateInstanceBuffer(ref m_BodyTransitionBuffer, m_BodyTransitions, "BodyTransitionBuffer");
		UpdateInstanceBuffer(ref m_BodyTransition2Buffer, m_BodyTransitions2, "BodyTransitionBuffer2");
		UpdateInstanceBuffer(ref m_FaceTransitionBuffer, m_FaceTransitions, "FaceTransitionBuffer");
	}
```

- `private UpdateMetaData() : System.Void`  

```csharp
private void UpdateMetaData()
	{
		int num = 0;
		while (num < m_UpdatedMetaIndices.Length)
		{
			int num2 = m_UpdatedMetaIndices[num++];
			int num3 = num2 + 1;
			while (num < m_UpdatedMetaIndices.Length)
			{
				int num4 = m_UpdatedMetaIndices[num];
				if (num4 != num3)
				{
					break;
				}
				num++;
				num3 = num4 + 1;
			}
			m_MetaBuffer.SetData(m_MetaBufferData.AsArray(), num2, num2, num3 - num2);
		}
		m_UpdatedMetaIndices.Clear();
	}
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

