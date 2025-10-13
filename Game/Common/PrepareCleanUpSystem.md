# Game.Common.PrepareCleanUpSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class PrepareCleanUpSystem : Game.GameSystemBase
{
    private Game.Common.CleanUpSystem m_CleanUpSystem;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Unity.Entities.EntityQuery m_UpdatedQuery;

    public PrepareCleanUpSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.CleanUpSystem m_CleanUpSystem`  

```csharp
private Game.Common.CleanUpSystem m_CleanUpSystem;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```


## Constructors

- `public PrepareCleanUpSystem()`  

```csharp
[Preserve]
	public PrepareCleanUpSystem()
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
		m_CleanUpSystem = base.World.GetOrCreateSystemManaged<CleanUpSystem>();
		m_DeletedQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Event>()
			}
		});
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[6]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Applied>(),
				ComponentType.ReadOnly<EffectsUpdated>(),
				ComponentType.ReadOnly<BatchesUpdated>(),
				ComponentType.ReadOnly<PathfindUpdated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle outJobHandle;
		NativeList<Entity> deletedEntities = m_DeletedQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle outJobHandle2;
		NativeList<Entity> updatedEntities = m_UpdatedQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle2);
		m_CleanUpSystem.AddDeleted(deletedEntities, outJobHandle);
		m_CleanUpSystem.AddUpdated(updatedEntities, outJobHandle2);
		base.Dependency = JobHandle.CombineDependencies(outJobHandle, outJobHandle2);
	}
```


