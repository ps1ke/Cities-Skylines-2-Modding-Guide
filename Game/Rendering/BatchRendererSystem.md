# Game.Rendering.BatchRendererSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class BatchRendererSystem : Game.GameSystemBase
{
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;

    public BatchRendererSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```


## Constructors

- `public BatchRendererSystem()`  

```csharp
[Preserve]
	public BatchRendererSystem()
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
		m_BatchMeshSystem = base.World.GetOrCreateSystemManaged<BatchMeshSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: true, out dependencies);
		JobHandle dependencies2;
		NativeSubBatches<CullingData, GroupData, BatchData, InstanceData> nativeSubBatches = m_BatchManagerSystem.GetNativeSubBatches(readOnly: false, out dependencies2);
		ManagedBatches<OptionalProperties> managedBatches = m_BatchManagerSystem.GetManagedBatches();
		dependencies.Complete();
		dependencies2.Complete();
		ObsoleteManagedBatchEnumerator obsoleteManagedBatches = nativeBatchGroups.GetObsoleteManagedBatches();
		int managedBatchIndex;
		while (obsoleteManagedBatches.GetNextObsoleteBatch(out managedBatchIndex))
		{
			CustomBatch customBatch = (CustomBatch)managedBatches.GetBatch(managedBatchIndex);
			m_BatchMeshSystem.RemoveBatch(customBatch, managedBatchIndex);
			managedBatches.RemoveBatch(managedBatchIndex);
			customBatch.Dispose();
		}
		UpdatedMetaDataEnumerator updatedMetaDatas = nativeBatchGroups.GetUpdatedMetaDatas();
		int groupIndex;
		while (updatedMetaDatas.GetNextUpdatedGroup(out groupIndex))
		{
			nativeSubBatches.RecreateRenderers(groupIndex);
		}
		ObsoleteBatchRendererEnumerator obsoleteBatchRenderers = nativeSubBatches.GetObsoleteBatchRenderers();
		BatchID rendererIndex;
		while (obsoleteBatchRenderers.GetNextObsoleteRenderer(out rendererIndex))
		{
			managedBatches.RemoveRenderer(rendererIndex);
		}
		nativeSubBatches.ClearObsoleteBatchRenderers();
		UpdatedBatchRendererEnumerator updatedBatchRenderers = nativeSubBatches.GetUpdatedBatchRenderers();
		int groupIndex2;
		while (updatedBatchRenderers.GetNextUpdatedGroup(out groupIndex2))
		{
			NativeSubBatchAccessor<BatchData> subBatchAccessor = nativeSubBatches.GetSubBatchAccessor(groupIndex2);
			for (int i = 0; i < subBatchAccessor.Length; i++)
			{
				NativeBatchPropertyAccessor batchPropertyAccessor = nativeBatchGroups.GetBatchPropertyAccessor(groupIndex2, i);
				if (subBatchAccessor.GetBatchID(i) == BatchID.Null)
				{
					BatchID batchID = managedBatches.AddBatchRenderer(batchPropertyAccessor);
					nativeSubBatches.SetBatchID(groupIndex2, i, batchID);
				}
			}
		}
		nativeSubBatches.ClearUpdatedBatchRenderers();
		JobHandle jobHandle = new ClearUpdatedMetaDatasJob
		{
			m_NativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: false, out dependencies)
		}.Schedule(dependencies);
		m_BatchManagerSystem.AddNativeBatchGroupsWriter(jobHandle);
	}
```


## Nested types

- `Game.Rendering.BatchRendererSystem+ClearUpdatedMetaDatasJob`  

