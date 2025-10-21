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
public ProceduralEmissiveSystem();
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

- `public BeginUpload(System.Int32 opCount, System.UInt32 dataSize, System.UInt32 maxOpSize) : Colossal.Rendering.ThreadedSparseUploader`  

```csharp
public Colossal.Rendering.ThreadedSparseUploader BeginUpload(System.Int32 opCount, System.UInt32 dataSize, System.UInt32 maxOpSize);
```

- `public CompleteUpload() : System.Void`  

```csharp
public System.Void CompleteUpload();
```

- `public static GetGpuLights(Game.Rendering.Emissive emissive, Unity.Entities.DynamicBuffer`1[[Game.Prefabs.ProceduralLight, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralLights, Unity.Entities.DynamicBuffer`1[[Game.Rendering.LightState, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lights, Unity.Collections.NativeList<Unity.Mathematics.float4> gpuLights) : System.Void`  

```csharp
public static System.Void GetGpuLights(Game.Rendering.Emissive emissive, Unity.Entities.DynamicBuffer`1[[Game.Prefabs.ProceduralLight, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralLights, Unity.Entities.DynamicBuffer`1[[Game.Rendering.LightState, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lights, Unity.Collections.NativeList<Unity.Mathematics.float4> gpuLights);
```

- `public GetHeapAllocator(Unity.Collections.NativeReference`1[[Game.Rendering.ProceduralEmissiveSystem+AllocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationInfo, Unity.Collections.NativeQueue`1[[Game.Rendering.ProceduralEmissiveSystem+AllocationRemove, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationRemoves, System.Int32& currentTime, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeHeapAllocator`  

```csharp
public Colossal.Collections.NativeHeapAllocator GetHeapAllocator(Unity.Collections.NativeReference`1[[Game.Rendering.ProceduralEmissiveSystem+AllocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationInfo, Unity.Collections.NativeQueue`1[[Game.Rendering.ProceduralEmissiveSystem+AllocationRemove, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& allocationRemoves, System.Int32& currentTime, Unity.Jobs.JobHandle& dependencies);
```

- `public GetMemoryStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& currentUpload, System.UInt32& uploadSize, System.Int32& allocationCount) : System.Void`  

```csharp
public System.Void GetMemoryStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& currentUpload, System.UInt32& uploadSize, System.Int32& allocationCount);
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

- `Game.Rendering.ProceduralEmissiveSystem+AllocationInfo`  
- `Game.Rendering.ProceduralEmissiveSystem+AllocationRemove`  
- `Game.Rendering.ProceduralEmissiveSystem+RemoveAllocationsJob`  

