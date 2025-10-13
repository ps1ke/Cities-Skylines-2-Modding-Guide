# Game.Prefabs.UnlockAllSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UnlockAllSystem : Game.GameSystemBase
{
    private Game.Simulation.MilestoneSystem m_MilestoneSystem;
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Game.UI.InGame.UIHighlightSystem m_UIHighlightSystem;
    private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem;
    private Unity.Entities.EntityQuery m_LockedQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;

    public UnlockAllSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void UnlockAllImpl();
}
```


## Fields

- `private Game.Simulation.MilestoneSystem m_MilestoneSystem`  

```csharp
private Game.Simulation.MilestoneSystem m_MilestoneSystem;
```

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Game.UI.InGame.UIHighlightSystem m_UIHighlightSystem`  

```csharp
private Game.UI.InGame.UIHighlightSystem m_UIHighlightSystem;
```

- `private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem`  

```csharp
private Game.UI.InGame.SignatureBuildingUISystem m_SignatureBuildingUISystem;
```

- `private Unity.Entities.EntityQuery m_LockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```


## Constructors

- `public UnlockAllSystem()`  

```csharp
[Preserve]
	public UnlockAllSystem()
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
		m_MilestoneSystem = base.World.GetOrCreateSystemManaged<MilestoneSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier1>();
		m_UIHighlightSystem = base.World.GetOrCreateSystemManaged<UIHighlightSystem>();
		m_SignatureBuildingUISystem = base.World.GetOrCreateSystemManaged<SignatureBuildingUISystem>();
		m_LockedQuery = GetEntityQuery(ComponentType.ReadOnly<Locked>(), ComponentType.Exclude<MilestoneData>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		RequireForUpdate(m_LockedQuery);
		base.Enabled = false;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		UnlockAllImpl();
		base.Enabled = false;
	}
```

- `private UnlockAllImpl() : System.Void`  

```csharp
private void UnlockAllImpl()
	{
		EntityCommandBuffer entityCommandBuffer = m_ModificationBarrier.CreateCommandBuffer();
		NativeArray<Entity> nativeArray = m_LockedQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity prefab = nativeArray[i];
			Entity e = entityCommandBuffer.CreateEntity(m_UnlockEventArchetype);
			entityCommandBuffer.SetComponent(e, new Unlock(prefab));
		}
		nativeArray.Dispose();
		m_MilestoneSystem.UnlockAllMilestones();
		m_UIHighlightSystem.SkipUpdate();
		m_SignatureBuildingUISystem.SkipUpdate();
	}
```


