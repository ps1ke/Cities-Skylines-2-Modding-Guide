# Game.Rendering.ProceduralSkeletonSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class ProceduralSkeletonSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Colossal.Collections.NativeHeapAllocator m_HeapAllocator;
    private Colossal.Rendering.SparseUploader m_SparseUploader;
    private Colossal.Rendering.ThreadedSparseUploader m_ThreadedSparseUploader;
    private Unity.Collections.NativeReference<Game.Rendering.ProceduralSkeletonSystem+AllocationInfo> m_AllocationInfo;
    private Unity.Collections.NativeQueue<Game.Rendering.ProceduralSkeletonSystem+AllocationRemove> m_AllocationRemoves;
    private System.Boolean m_IsAllocating;
    private System.Boolean m_IsUploading;
    private UnityEngine.GraphicsBuffer m_ComputeBuffer;
    private Unity.Jobs.JobHandle m_HeapDeps;
    private Unity.Jobs.JobHandle m_UploadDeps;
    private System.Int32 m_HeapAllocatorByteSize;
    private System.Int32 m_CurrentTime;
    private System.Boolean m_AreMotionVectorsEnabled;
    private System.Boolean m_ForceHistoryUpdate;
    public static const System.UInt32 SKELETON_MEMORY_DEFAULT;
    public static const System.UInt32 SKELETON_MEMORY_INCREMENT;
    public static const System.UInt32 UPLOADER_CHUNK_SIZE;

    public System.Boolean isMotionBlurEnabled { get; }
    public System.Boolean forceHistoryUpdate { get; }

    public ProceduralSkeletonSystem();

    public System.Void AddHeapWriter(Unity.Jobs.JobHandle handle);
    public System.Void AddUploadWriter(Unity.Jobs.JobHandle handle);
    private System.Void AllocateIdentityEntry();
    public Colossal.Rendering.ThreadedSparseUploader BeginUpload(System.Int32 opCount, System.UInt32 dataSize, System.UInt32 maxOpSize, System.Int32& historyByteOffset);
    public System.Void CompleteUpload();
    public Colossal.Collections.NativeHeapAllocator GetHeapAllocator(Unity.Collections.NativeReference`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationInfo, Unity.Collections.NativeQueue`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationRemove, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationRemoves, System.Int32& currentTime, Unity.Jobs.JobHandle& dependencies);
    public System.Void GetMemoryStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& currentUpload, System.UInt32& uploadSize, System.Int32& allocationCount);
    public static System.Void GetSkinMatrices(Game.Rendering.Skeleton skeleton, Unity.Entities.DynamicBuffer`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBones, Unity.Entities.DynamicBuffer`1[[Game.Rendering.Bone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bones, Unity.Collections.NativeList<Unity.Mathematics.float4x4> tempMatrices);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Colossal.Collections.NativeHeapAllocator m_HeapAllocator`  

```csharp
private Colossal.Collections.NativeHeapAllocator m_HeapAllocator;
```

- `private Colossal.Rendering.SparseUploader m_SparseUploader`  

```csharp
private Colossal.Rendering.SparseUploader m_SparseUploader;
```

- `private Colossal.Rendering.ThreadedSparseUploader m_ThreadedSparseUploader`  

```csharp
private Colossal.Rendering.ThreadedSparseUploader m_ThreadedSparseUploader;
```

- `private Unity.Collections.NativeReference<Game.Rendering.ProceduralSkeletonSystem+AllocationInfo> m_AllocationInfo`  

```csharp
private Unity.Collections.NativeReference<Game.Rendering.ProceduralSkeletonSystem+AllocationInfo> m_AllocationInfo;
```

- `private Unity.Collections.NativeQueue<Game.Rendering.ProceduralSkeletonSystem+AllocationRemove> m_AllocationRemoves`  

```csharp
private Unity.Collections.NativeQueue<Game.Rendering.ProceduralSkeletonSystem+AllocationRemove> m_AllocationRemoves;
```

- `private System.Boolean m_IsAllocating`  

```csharp
private System.Boolean m_IsAllocating;
```

- `private System.Boolean m_IsUploading`  

```csharp
private System.Boolean m_IsUploading;
```

- `private UnityEngine.GraphicsBuffer m_ComputeBuffer`  

```csharp
private UnityEngine.GraphicsBuffer m_ComputeBuffer;
```

- `private Unity.Jobs.JobHandle m_HeapDeps`  

```csharp
private Unity.Jobs.JobHandle m_HeapDeps;
```

- `private Unity.Jobs.JobHandle m_UploadDeps`  

```csharp
private Unity.Jobs.JobHandle m_UploadDeps;
```

- `private System.Int32 m_HeapAllocatorByteSize`  

```csharp
private System.Int32 m_HeapAllocatorByteSize;
```

- `private System.Int32 m_CurrentTime`  

```csharp
private System.Int32 m_CurrentTime;
```

- `private System.Boolean m_AreMotionVectorsEnabled`  

```csharp
private System.Boolean m_AreMotionVectorsEnabled;
```

- `private System.Boolean m_ForceHistoryUpdate`  

```csharp
private System.Boolean m_ForceHistoryUpdate;
```

- `public static const System.UInt32 SKELETON_MEMORY_DEFAULT`  

```csharp
public static const System.UInt32 SKELETON_MEMORY_DEFAULT;
```

- `public static const System.UInt32 SKELETON_MEMORY_INCREMENT`  

```csharp
public static const System.UInt32 SKELETON_MEMORY_INCREMENT;
```

- `public static const System.UInt32 UPLOADER_CHUNK_SIZE`  

```csharp
public static const System.UInt32 UPLOADER_CHUNK_SIZE;
```


## Properties

- `public System.Boolean isMotionBlurEnabled { get }`  

```csharp
public System.Boolean isMotionBlurEnabled { get; }
```

- `public System.Boolean forceHistoryUpdate { get }`  

```csharp
public System.Boolean forceHistoryUpdate { get; }
```


## Constructors

- `public ProceduralSkeletonSystem()`  

```csharp
[Preserve]
	public ProceduralSkeletonSystem()
	{
	}
```


## Methods

- `public AddHeapWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddHeapWriter(JobHandle handle)
	{
		m_HeapDeps = handle;
	}
```

- `public AddUploadWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddUploadWriter(JobHandle handle)
	{
		m_UploadDeps = handle;
	}
```

- `private AllocateIdentityEntry() : System.Void`  

```csharp
private void AllocateIdentityEntry()
	{
		m_IsAllocating = true;
		m_HeapAllocator.Allocate(1u);
		m_AllocationInfo.Value = new AllocationInfo
		{
			m_AllocationCount = 0u
		};
	}
```

- `public BeginUpload(System.Int32 opCount, System.UInt32 dataSize, System.UInt32 maxOpSize, System.Int32& historyByteOffset) : Colossal.Rendering.ThreadedSparseUploader`  

```csharp
public ThreadedSparseUploader BeginUpload(int opCount, uint dataSize, uint maxOpSize, out int historyByteOffset)
	{
		m_ThreadedSparseUploader = m_SparseUploader.Begin((int)dataSize, (int)maxOpSize, opCount);
		m_IsUploading = true;
		historyByteOffset = m_HeapAllocatorByteSize;
		return m_ThreadedSparseUploader;
	}
```

- `public CompleteUpload() : System.Void`  

```csharp
public void CompleteUpload()
	{
		if (m_IsUploading)
		{
			m_UploadDeps.Complete();
			m_IsUploading = false;
			m_SparseUploader.EndAndCommit(m_ThreadedSparseUploader);
		}
	}
```

- `public GetHeapAllocator(Unity.Collections.NativeReference`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationInfo, Unity.Collections.NativeQueue`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationRemove, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationRemoves, System.Int32& currentTime, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeHeapAllocator`  

```csharp
public NativeHeapAllocator GetHeapAllocator(out NativeReference<AllocationInfo> allocationInfo, out NativeQueue<AllocationRemove> allocationRemoves, out int currentTime, out JobHandle dependencies)
	{
		dependencies = m_HeapDeps;
		allocationInfo = m_AllocationInfo;
		allocationRemoves = m_AllocationRemoves;
		currentTime = m_CurrentTime;
		m_IsAllocating = true;
		return m_HeapAllocator;
	}
```

- `public GetMemoryStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& currentUpload, System.UInt32& uploadSize, System.Int32& allocationCount) : System.Void`  

```csharp
public unsafe void GetMemoryStats(out uint allocatedSize, out uint bufferSize, out uint currentUpload, out uint uploadSize, out int allocationCount)
	{
		m_HeapDeps.Complete();
		int num = ((!m_RenderingSystem.motionVectors) ? 1 : 2);
		allocatedSize = (uint)((int)m_HeapAllocator.UsedSpace * sizeof(float4x4) * num);
		bufferSize = (uint)((int)m_HeapAllocator.Size * sizeof(float4x4) * num);
		allocationCount = (int)m_AllocationInfo.Value.m_AllocationCount;
		SparseUploaderStats sparseUploaderStats = m_SparseUploader.ComputeStats();
		currentUpload = (uint)sparseUploaderStats.BytesGPUMemoryUploadedCurr;
		uploadSize = (uint)sparseUploaderStats.BytesGPUMemoryUsed;
	}
```

- `public static GetSkinMatrices(Game.Rendering.Skeleton skeleton, Unity.Entities.DynamicBuffer`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBones, Unity.Entities.DynamicBuffer`1[[Game.Rendering.Bone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bones, Unity.Collections.NativeList<Unity.Mathematics.float4x4> tempMatrices) : System.Void`  

```csharp
public static void GetSkinMatrices(Skeleton skeleton, in DynamicBuffer<ProceduralBone> proceduralBones, in DynamicBuffer<Bone> bones, NativeList<float4x4> tempMatrices)
	{
		for (int i = 0; i < proceduralBones.Length; i++)
		{
			ProceduralBone proceduralBone = proceduralBones[i];
			Bone bone = bones[skeleton.m_BoneOffset + i];
			float4x4 float4x = float4x4.TRS(bone.m_Position, bone.m_Rotation, bone.m_Scale);
			if (proceduralBone.m_ParentIndex >= 0)
			{
				float4x = math.mul(tempMatrices[proceduralBone.m_ParentIndex], float4x);
			}
			tempMatrices[i] = float4x;
			tempMatrices[proceduralBones.Length + proceduralBone.m_BindIndex] = math.mul(float4x, proceduralBone.m_BindPose);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected unsafe override void OnCreate()
	{
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_HeapAllocator = new NativeHeapAllocator(4194304u / (uint)sizeof(float4x4), 1u, Allocator.Persistent);
		m_SparseUploader = new SparseUploader("Procedural skeleton uploader", null, 524288);
		m_AllocationInfo = new NativeReference<AllocationInfo>(Allocator.Persistent);
		m_AllocationRemoves = new NativeQueue<AllocationRemove>(Allocator.Persistent);
		AllocateIdentityEntry();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		CompleteUpload();
		m_HeapDeps.Complete();
		if (m_HeapAllocator.IsCreated)
		{
			m_HeapAllocator.Dispose();
			m_SparseUploader.Dispose();
			m_AllocationInfo.Dispose();
			m_AllocationRemoves.Dispose();
		}
		if (m_ComputeBuffer != null)
		{
			m_ComputeBuffer.Release();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected unsafe override void OnUpdate()
	{
		bool motionVectors = m_RenderingSystem.motionVectors;
		int num = ((!motionVectors) ? 1 : 2);
		m_ForceHistoryUpdate = m_AreMotionVectorsEnabled != motionVectors;
		CompleteUpload();
		m_HeapDeps.Complete();
		if (m_IsAllocating || m_ForceHistoryUpdate)
		{
			m_IsAllocating = false;
			m_AreMotionVectorsEnabled = motionVectors;
			m_HeapAllocatorByteSize = (int)m_HeapAllocator.Size * sizeof(float4x4);
			int num2 = m_HeapAllocatorByteSize * num;
			int num3 = ((m_ComputeBuffer != null) ? (m_ComputeBuffer.count * m_ComputeBuffer.stride) : 0);
			if (num2 != num3)
			{
				GraphicsBuffer graphicsBuffer = new GraphicsBuffer(GraphicsBuffer.Target.Raw, num2 / 4, 4);
				graphicsBuffer.name = "Procedural bone buffer";
				Shader.SetGlobalBuffer("_BoneTransforms", graphicsBuffer);
				if (motionVectors && !m_ForceHistoryUpdate)
				{
					m_SparseUploader.ReplaceBuffer(graphicsBuffer, copyFromPrevious: true, num3 / 2);
				}
				else
				{
					m_SparseUploader.ReplaceBuffer(graphicsBuffer, copyFromPrevious: true);
				}
				if (m_ComputeBuffer == null)
				{
					graphicsBuffer.SetData(new List<float4x4> { float4x4.identity }, 0, 0, 1);
				}
				if (motionVectors && (m_ComputeBuffer == null || m_ForceHistoryUpdate))
				{
					graphicsBuffer.SetData(new List<float4x4> { float4x4.identity }, 0, (int)m_HeapAllocator.Size, 1);
				}
				if (m_ComputeBuffer != null)
				{
					m_ComputeBuffer.Release();
				}
				m_ComputeBuffer = graphicsBuffer;
			}
			Shader.SetGlobalInt("_BonePreviousTransformsByteOffset", m_HeapAllocatorByteSize);
		}
		if (!m_AllocationRemoves.IsEmpty())
		{
			m_CurrentTime = (m_CurrentTime + m_RenderingSystem.lodTimerDelta) & 0xFFFF;
			RemoveAllocationsJob jobData = new RemoveAllocationsJob
			{
				m_HeapAllocator = m_HeapAllocator,
				m_AllocationInfo = m_AllocationInfo,
				m_AllocationRemoves = m_AllocationRemoves,
				m_CurrentTime = m_CurrentTime
			};
			m_HeapDeps = IJobExtensions.Schedule(jobData);
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_HeapDeps.Complete();
		m_HeapAllocator.Clear();
		m_AllocationRemoves.Clear();
		AllocateIdentityEntry();
	}
```


## Nested types

- `Game.Rendering.ProceduralSkeletonSystem+AllocationInfo`  
- `Game.Rendering.ProceduralSkeletonSystem+AllocationRemove`  
- `Game.Rendering.ProceduralSkeletonSystem+RemoveAllocationsJob`  

