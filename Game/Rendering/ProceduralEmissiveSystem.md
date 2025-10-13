# Game.Rendering.ProceduralEmissiveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class ProceduralEmissiveSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Colossal.Collections.NativeHeapAllocator m_HeapAllocator;
    private Colossal.Rendering.SparseUploader m_SparseUploader;
    private Colossal.Rendering.ThreadedSparseUploader m_ThreadedSparseUploader;
    private Unity.Collections.NativeReference<Game.Rendering.ProceduralEmissiveSystem+AllocationInfo> m_AllocationInfo;
    private Unity.Collections.NativeQueue<Game.Rendering.ProceduralEmissiveSystem+AllocationRemove> m_AllocationRemoves;
    private System.Boolean m_IsAllocating;
    private System.Boolean m_IsUploading;
    private UnityEngine.GraphicsBuffer m_ComputeBuffer;
    private Unity.Jobs.JobHandle m_HeapDeps;
    private Unity.Jobs.JobHandle m_UploadDeps;
    private System.Int32 m_HeapAllocatorByteSize;
    private System.Int32 m_CurrentTime;
    public static const System.UInt32 EMISSIVE_MEMORY_DEFAULT;
    public static const System.UInt32 EMISSIVE_MEMORY_INCREMENT;
    public static const System.UInt32 UPLOADER_CHUNK_SIZE;

    public ProceduralEmissiveSystem();

    public System.Void AddHeapWriter(Unity.Jobs.JobHandle handle);
    public System.Void AddUploadWriter(Unity.Jobs.JobHandle handle);
    private System.Void AllocateIdentityEntry();
    public Colossal.Rendering.ThreadedSparseUploader BeginUpload(System.Int32 opCount, System.UInt32 dataSize, System.UInt32 maxOpSize);
    public System.Void CompleteUpload();
    public static System.Void GetGpuLights(Game.Rendering.Emissive emissive, Unity.Entities.DynamicBuffer`1[[Game.Prefabs.ProceduralLight, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralLights, Unity.Entities.DynamicBuffer`1[[Game.Rendering.LightState, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lights, Unity.Collections.NativeList<Unity.Mathematics.float4> gpuLights);
    public Colossal.Collections.NativeHeapAllocator GetHeapAllocator(Unity.Collections.NativeReference`1[[Game.Rendering.ProceduralEmissiveSystem+AllocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationInfo, Unity.Collections.NativeQueue`1[[Game.Rendering.ProceduralEmissiveSystem+AllocationRemove, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationRemoves, System.Int32& currentTime, Unity.Jobs.JobHandle& dependencies);
    public System.Void GetMemoryStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& currentUpload, System.UInt32& uploadSize, System.Int32& allocationCount);
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

- `private Unity.Collections.NativeReference<Game.Rendering.ProceduralEmissiveSystem+AllocationInfo> m_AllocationInfo`  

```csharp
private Unity.Collections.NativeReference<Game.Rendering.ProceduralEmissiveSystem+AllocationInfo> m_AllocationInfo;
```

- `private Unity.Collections.NativeQueue<Game.Rendering.ProceduralEmissiveSystem+AllocationRemove> m_AllocationRemoves`  

```csharp
private Unity.Collections.NativeQueue<Game.Rendering.ProceduralEmissiveSystem+AllocationRemove> m_AllocationRemoves;
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

- `public static const System.UInt32 EMISSIVE_MEMORY_DEFAULT`  

```csharp
public static const System.UInt32 EMISSIVE_MEMORY_DEFAULT;
```

- `public static const System.UInt32 EMISSIVE_MEMORY_INCREMENT`  

```csharp
public static const System.UInt32 EMISSIVE_MEMORY_INCREMENT;
```

- `public static const System.UInt32 UPLOADER_CHUNK_SIZE`  

```csharp
public static const System.UInt32 UPLOADER_CHUNK_SIZE;
```


## Constructors

- `public ProceduralEmissiveSystem()`  

```csharp
[Preserve]
	public ProceduralEmissiveSystem()
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

- `public BeginUpload(System.Int32 opCount, System.UInt32 dataSize, System.UInt32 maxOpSize) : Colossal.Rendering.ThreadedSparseUploader`  

```csharp
public ThreadedSparseUploader BeginUpload(int opCount, uint dataSize, uint maxOpSize)
	{
		m_ThreadedSparseUploader = m_SparseUploader.Begin((int)dataSize, (int)maxOpSize, opCount);
		m_IsUploading = true;
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

- `public static GetGpuLights(Game.Rendering.Emissive emissive, Unity.Entities.DynamicBuffer`1[[Game.Prefabs.ProceduralLight, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralLights, Unity.Entities.DynamicBuffer`1[[Game.Rendering.LightState, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lights, Unity.Collections.NativeList<Unity.Mathematics.float4> gpuLights) : System.Void`  

```csharp
public static void GetGpuLights(Emissive emissive, in DynamicBuffer<ProceduralLight> proceduralLights, in DynamicBuffer<LightState> lights, NativeList<float4> gpuLights)
	{
		gpuLights[0] = default(float4);
		for (int i = 0; i < proceduralLights.Length; i++)
		{
			ProceduralLight proceduralLight = proceduralLights[i];
			LightState lightState = lights[emissive.m_LightOffset + i];
			float4 value = math.lerp(proceduralLight.m_Color, proceduralLight.m_Color2, lightState.m_Color);
			value.w *= lightState.m_Intensity;
			gpuLights[i + 1] = value;
		}
	}
```

- `public GetHeapAllocator(Unity.Collections.NativeReference`1[[Game.Rendering.ProceduralEmissiveSystem+AllocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationInfo, Unity.Collections.NativeQueue`1[[Game.Rendering.ProceduralEmissiveSystem+AllocationRemove, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationRemoves, System.Int32& currentTime, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeHeapAllocator`  

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
		allocatedSize = m_HeapAllocator.UsedSpace * (uint)sizeof(float4);
		bufferSize = m_HeapAllocator.Size * (uint)sizeof(float4);
		allocationCount = (int)m_AllocationInfo.Value.m_AllocationCount;
		SparseUploaderStats sparseUploaderStats = m_SparseUploader.ComputeStats();
		currentUpload = (uint)sparseUploaderStats.BytesGPUMemoryUploadedCurr;
		uploadSize = (uint)sparseUploaderStats.BytesGPUMemoryUsed;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected unsafe override void OnCreate()
	{
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_HeapAllocator = new NativeHeapAllocator(2097152u / (uint)sizeof(float4), 1u, Allocator.Persistent);
		m_SparseUploader = new SparseUploader("Procedural emissive uploader", null, 131072);
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
		CompleteUpload();
		m_HeapDeps.Complete();
		if (m_IsAllocating)
		{
			m_IsAllocating = false;
			m_HeapAllocatorByteSize = (int)m_HeapAllocator.Size * sizeof(float4);
			int heapAllocatorByteSize = m_HeapAllocatorByteSize;
			int num = ((m_ComputeBuffer != null) ? (m_ComputeBuffer.count * m_ComputeBuffer.stride) : 0);
			if (heapAllocatorByteSize != num)
			{
				GraphicsBuffer graphicsBuffer = new GraphicsBuffer(GraphicsBuffer.Target.Raw, heapAllocatorByteSize / 4, 4);
				graphicsBuffer.name = "Procedural emissive buffer";
				Shader.SetGlobalBuffer("_LightInfo", graphicsBuffer);
				m_SparseUploader.ReplaceBuffer(graphicsBuffer, copyFromPrevious: true);
				if (m_ComputeBuffer != null)
				{
					m_ComputeBuffer.Release();
				}
				else
				{
					graphicsBuffer.SetData(new List<float4> { float4.zero }, 0, 0, 1);
				}
				m_ComputeBuffer = graphicsBuffer;
			}
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

- `Game.Rendering.ProceduralEmissiveSystem+AllocationInfo`  
- `Game.Rendering.ProceduralEmissiveSystem+AllocationRemove`  
- `Game.Rendering.ProceduralEmissiveSystem+RemoveAllocationsJob`  

