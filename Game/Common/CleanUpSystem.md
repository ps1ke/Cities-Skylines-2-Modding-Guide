# Game.Common.CleanUpSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class CleanUpSystem : Game.GameSystemBase
{
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_DeletedEntities;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_UpdatedEntities;
    private Unity.Jobs.JobHandle m_DeletedDeps;
    private Unity.Jobs.JobHandle m_UpdatedDeps;
    private Unity.Entities.ComponentTypeSet m_UpdateTypes;

    public CleanUpSystem();

    public System.Void AddDeleted(Unity.Collections.NativeList<Unity.Entities.Entity> deletedEntities, Unity.Jobs.JobHandle deletedDeps);
    public System.Void AddUpdated(Unity.Collections.NativeList<Unity.Entities.Entity> updatedEntities, Unity.Jobs.JobHandle updatedDeps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_DeletedEntities`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_DeletedEntities;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_UpdatedEntities`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_UpdatedEntities;
```

- `private Unity.Jobs.JobHandle m_DeletedDeps`  

```csharp
private Unity.Jobs.JobHandle m_DeletedDeps;
```

- `private Unity.Jobs.JobHandle m_UpdatedDeps`  

```csharp
private Unity.Jobs.JobHandle m_UpdatedDeps;
```

- `private Unity.Entities.ComponentTypeSet m_UpdateTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_UpdateTypes;
```


## Constructors

- `public CleanUpSystem()`  

```csharp
[Preserve]
	public CleanUpSystem()
	{
	}
```


## Methods

- `public AddDeleted(Unity.Collections.NativeList<Unity.Entities.Entity> deletedEntities, Unity.Jobs.JobHandle deletedDeps) : System.Void`  

```csharp
public void AddDeleted(NativeList<Entity> deletedEntities, JobHandle deletedDeps)
	{
		m_DeletedEntities = deletedEntities;
		m_DeletedDeps = deletedDeps;
	}
```

- `public AddUpdated(Unity.Collections.NativeList<Unity.Entities.Entity> updatedEntities, Unity.Jobs.JobHandle updatedDeps) : System.Void`  

```csharp
public void AddUpdated(NativeList<Entity> updatedEntities, JobHandle updatedDeps)
	{
		m_UpdatedEntities = updatedEntities;
		m_UpdatedDeps = updatedDeps;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdateTypes = new ComponentTypeSet(new ComponentType[6]
		{
			ComponentType.ReadWrite<Created>(),
			ComponentType.ReadWrite<Updated>(),
			ComponentType.ReadWrite<Applied>(),
			ComponentType.ReadWrite<EffectsUpdated>(),
			ComponentType.ReadWrite<BatchesUpdated>(),
			ComponentType.ReadWrite<PathfindUpdated>()
		});
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_DeletedDeps.Complete();
		m_UpdatedDeps.Complete();
		base.EntityManager.DestroyEntity(m_DeletedEntities.AsArray());
		base.EntityManager.RemoveComponent(m_UpdatedEntities.AsArray(), in m_UpdateTypes);
		m_DeletedEntities.Dispose();
		m_UpdatedEntities.Dispose();
	}
```


