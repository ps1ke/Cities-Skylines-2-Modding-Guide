# Game.Rendering.BatchUploadSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class BatchUploadSystem : Game.GameSystemBase
{
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;

    public BatchUploadSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```


## Constructors

- `public BatchUploadSystem()`  

```csharp
[Preserve]
	public BatchUploadSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_BatchManagerSystem = base.World.GetOrCreateSystemManaged<BatchManagerSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependencies;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = m_BatchManagerSystem.GetNativeBatchInstances(readOnly: false, out dependencies);
		JobHandle dependencies2;
		NativeSubBatches<CullingData, GroupData, BatchData, InstanceData> nativeSubBatches = m_BatchManagerSystem.GetNativeSubBatches(readOnly: true, out dependencies2);
		ManagedBatches<OptionalProperties> managedBatches = m_BatchManagerSystem.GetManagedBatches();
		dependencies.Complete();
		dependencies2.Complete();
		managedBatches.StartUpload(nativeBatchInstances, nativeSubBatches);
		int activeGroupCount = nativeBatchInstances.GetActiveGroupCount();
		BatchUploadJob jobData = new BatchUploadJob
		{
			m_NativeBatchInstances = nativeBatchInstances.BeginParallelUpload()
		};
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(jobData, activeGroupCount, 1);
		JobHandle jobHandle2 = nativeBatchInstances.EndParallelUpload(jobData.m_NativeBatchInstances, jobHandle);
		m_BatchManagerSystem.AddNativeSubBatchesReader(jobHandle);
		m_BatchManagerSystem.AddNativeBatchInstancesWriter(jobHandle2);
	}
```


## Nested types

- `Game.Rendering.BatchUploadSystem+BatchUploadJob`  

