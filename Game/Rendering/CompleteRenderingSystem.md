# Game.Rendering.CompleteRenderingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class CompleteRenderingSystem : Game.GameSystemBase
{
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
    private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
    private Game.Rendering.WindTextureSystem m_WindTextureSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem;

    public CompleteRenderingSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem`  

```csharp
private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
```

- `private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem`  

```csharp
private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
```

- `private Game.Rendering.WindTextureSystem m_WindTextureSystem`  

```csharp
private Game.Rendering.WindTextureSystem m_WindTextureSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem`  

```csharp
private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem;
```


## Constructors

- `public CompleteRenderingSystem()`  

```csharp
[Preserve]
	public CompleteRenderingSystem()
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
		m_ManagedBatchSystem = base.World.GetOrCreateSystemManaged<ManagedBatchSystem>();
		m_ProceduralSkeletonSystem = base.World.GetOrCreateSystemManaged<ProceduralSkeletonSystem>();
		m_ProceduralEmissiveSystem = base.World.GetOrCreateSystemManaged<ProceduralEmissiveSystem>();
		m_WindTextureSystem = base.World.GetOrCreateSystemManaged<WindTextureSystem>();
		m_BatchMeshSystem = base.World.GetOrCreateSystemManaged<BatchMeshSystem>();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
		m_OverlayInfomodeSystem = base.World.GetOrCreateSystemManaged<OverlayInfomodeSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependencies;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = m_BatchManagerSystem.GetNativeBatchInstances(readOnly: false, out dependencies);
		ManagedBatches<OptionalProperties> managedBatches = m_BatchManagerSystem.GetManagedBatches();
		dependencies.Complete();
		managedBatches.EndUpload(nativeBatchInstances);
		m_ProceduralSkeletonSystem.CompleteUpload();
		m_ProceduralEmissiveSystem.CompleteUpload();
		m_WindTextureSystem.CompleteUpdate();
		m_ManagedBatchSystem.CompleteVTRequests();
		m_BatchMeshSystem.CompleteMeshes();
		m_OverlayInfomodeSystem.ApplyOverlay();
		m_UpdateSystem.Update(SystemUpdatePhase.CompleteRendering);
	}
```


