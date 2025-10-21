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
public ProceduralSkeletonSystem();
```


## Methods

- `public AddHeapWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddHeapWriter(Unity.Jobs.JobHandle handle);
```

- `public AddUploadWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddUploadWriter(Unity.Jobs.JobHandle handle);
```

- `private AllocateIdentityEntry() : System.Void`  

```csharp
private System.Void AllocateIdentityEntry();
```

- `public BeginUpload(System.Int32 opCount, System.UInt32 dataSize, System.UInt32 maxOpSize, System.Int32& historyByteOffset) : Colossal.Rendering.ThreadedSparseUploader`  

```csharp
public Colossal.Rendering.ThreadedSparseUploader BeginUpload(System.Int32 opCount, System.UInt32 dataSize, System.UInt32 maxOpSize, System.Int32& historyByteOffset);
```

- `public CompleteUpload() : System.Void`  

```csharp
public System.Void CompleteUpload();
```

- `public GetHeapAllocator(Unity.Collections.NativeReference`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationInfo, Unity.Collections.NativeQueue`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationRemove, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationRemoves, System.Int32& currentTime, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeHeapAllocator`  

```csharp
public Colossal.Collections.NativeHeapAllocator GetHeapAllocator(Unity.Collections.NativeReference`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationInfo, Unity.Collections.NativeQueue`1[[Game.Rendering.ProceduralSkeletonSystem+AllocationRemove, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationRemoves, System.Int32& currentTime, Unity.Jobs.JobHandle& dependencies);
```

- `public GetMemoryStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& currentUpload, System.UInt32& uploadSize, System.Int32& allocationCount) : System.Void`  

```csharp
public System.Void GetMemoryStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& currentUpload, System.UInt32& uploadSize, System.Int32& allocationCount);
```

- `public static GetSkinMatrices(Game.Rendering.Skeleton skeleton, Unity.Entities.DynamicBuffer`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBones, Unity.Entities.DynamicBuffer`1[[Game.Rendering.Bone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bones, Unity.Collections.NativeList<Unity.Mathematics.float4x4> tempMatrices) : System.Void`  

```csharp
public static System.Void GetSkinMatrices(Game.Rendering.Skeleton skeleton, Unity.Entities.DynamicBuffer`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBones, Unity.Entities.DynamicBuffer`1[[Game.Rendering.Bone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bones, Unity.Collections.NativeList<Unity.Mathematics.float4x4> tempMatrices);
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

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Rendering.ProceduralSkeletonSystem+AllocationInfo`  
- `Game.Rendering.ProceduralSkeletonSystem+AllocationRemove`  
- `Game.Rendering.ProceduralSkeletonSystem+RemoveAllocationsJob`  

